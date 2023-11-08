# Entity Framework Core

## ORM'nin Kod Açısından SQL İzolasyonunu İnceleyelim



### Giriş

ORM yaklaşımının kodun içerisindeki SQL izolasyonunu nasıl sağladığını, SQL kod yerine ORM arkaplanda neler oluşturuyor bunları inceliyor olacağız.

Kullanacağımız EF tool'unun arkaplanda bizim aslında düşündüğümüz davranışı nasıl oluşturduğunu öğrenmiş olacağız.

> "Hangi personel, hangi üründen kaç adet satmıştır?"
>
> Sorusuna hem ORM'siz, hem de ORM'li bir yaklaşımıyla çözüm getireceğiz.



### ORM'siz Yaklaşım (SQL + Kod İzolasyonsuz)

Normalde "Hangi **personel**, hangi **ürün**den kaç adet **satmış**tır?" sorgusunu gerçekleştirebilmek için, tabloları ve aralarındaki ilişkileri bilmemiz gerekir.
Haliyle SQL Management Studio'yu açıp ilgili veritabanında tüm tabloların ilişkilerini diyagram üzerinden inceliyoruz.

<img src=https://i.imgur.com/ipqX4EI.png align=left />

Görüldüğü üzere personelden ürünlere kadar olan ilişkiler sırasıyla;

Employees > Orders > OrderDetails > Products

Yine aynı şekilde SQL Management Studio üzerinden bu işlemi gerçekleştirecek sorguyu yazmaya başlıyoruz.

<img src=https://i.imgur.com/Mp6g7OE.png align=left />

Sorgumuzu test ettikten sonra artık kodlarımıza dönüp bu işlemleri aşağıdaki gibi gerçekleştiriyoruz.

```csharp
//#region ORMsiz Yaklaşım (SQL + Kod)
SqlConnection connection = new($"Server=localhost, 1433;Database=Northwind;User Id=trukafatsum;Password=1234");
await connection.OpenAsync();
SqlCommand command = new(@"
SELECT employee.FirstName, product.ProductName, COUNT(*) FROM Employees employee
INNER JOIN Orders orders
	ON employee.EmployeeID = orders.EmployeeID
INNER JOIN [Order Details] orderDetail
	ON orders.OrderID = orderDetail.OrderID
INNER JOIN Products product
	ON orderDetail.ProductID = product.ProductID
GROUP By employee.FirstName, product.ProductID
ORDER By COUNT(*) DESC
",connection);

SqlDataReader dr = command.ExecuteReader();
while (await dr.ReadAsync())
{
    Console.WriteLine($"{dr["FirstName"]} {dr["ProductName"]} {dr["Count"]}");
}

await connection.CloseAsync();
//#endregion
```

Bir önceki konuda da ele aldığımız gibi, buradaki metinsel ifadelerin sayısı fazla haliyle kod kirliliği var, ayrıca veritabanı üzerinde olabilecek herhangi bir değişiklik kodumuzun tekrar düzenlenmesini gerektirmektedir.



### ORM'li Yaklaşım (SQL - Kod İzolasyonu)

#### Extension Func

```csharp
//#region ORM'li Yaklaşım (SQL - Kod)
using Microsoft.EntityFrameworkCore;
using ORM_SQL_İzolasyonu.Models;

NorthwindContext context = new();
context.Employees
    .Include(employe => employee.Orders)
    	.ThenInclude(order => order.OrderDetails)
    	.ThenInclude(orderDetail => orderDetail.Product)
    .SelectMany(employee => employee.Orders, (employee,order) => new{ employee.FirstName, order.OrderDetails})
    .SelectMany(data => data.OrderDetails, (data, orderDetail) => new {data.FirstName, orderDetail.Product.ProductName})
    .GroupBy(data => new 
    {
    	data.ProductName,
        data.FirstName
    })
    .Select(data => new
    {
        data.Key.FirstName,
        data.Key.ProductName,
        Count = data.Count()
    });
var data = await query.ToListAsync();

Console.WriteLine();
//#endregion
```

ORM yaklaşımıyla yazılmış olan bu kodda, gördüğünüz üzere herhangi bir SQL cümleciği geçmemektedir.
Kodlar derlendikten ve çalıştırıldıktan sonra MSSQL'de gerçekleştirilen sorgu aşağıdaki gibidir.

<img src=https://i.imgur.com/RwfOIPV.png align=left />

Başka bir veritabanı olsaydı, kodlarımız yine aynı olacak ve bu sefer ilgili veritabanına göre bir sorgu oluşturulacaktı.



#### LINQ ile

```csharp
//#region ORM'li Yaklaşım (SQL - Kod)
using Microsoft.EntityFrameworkCore;
using ORM_SQL_İzolasyonu.Models;

NorthwindContext context = new();
var query = from employee in context.Employees
  				join order in context.Orders
    				on employee.EmployeeId equals order.EmployeeId
    			join orderDetail in context.OrderDetails
    				on order.OrderId equals orderDetail.OrderId
    			join product in context.Products
    				on orderDetail.ProductId equals product.ProductId
    			select new { employee.FirstName, product.ProductName } into data
    			group data by new { data.FirstName, data.ProductName } into result
    			select new
				{
    				result.Key.FirstName,
    				result.Key.ProductName,
    				Count = result.Count()
				};
var datas = await query.ToListAsync();

Console.WriteLine();
//#endregion
```

LinQ ve ORM yaklaşımıyla yazılmış bu kodda yukarıdaki Extension Func ile yaptığımız işlemin aynısını gerçekleştirmiş olduk.