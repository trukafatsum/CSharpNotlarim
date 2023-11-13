# Entity Framework Core

## Code First Yaklaşımı



<img src=https://i.imgur.com/I58aLtt.png align=left />



### Migration & Migrate Kavramları Nelerdir?

> Migration : Veritabanındaki şemayı güncellemek veya yeni bir veritabanı oluşturmak için kullanılır. Migration'lar, modelde yapılan değişiklikleri veritabanına uygular. Bu uygulama işlemi de 'migrate' olarak adlandırılır.

<img src=https://i.imgur.com/0ugKShf.png align=left />



### Migration Oluşturmak için Temel Gereksinimler Nelerdir?

* Migration oluşturmak için temelde EF Core aktörleri olan DbContext ve Entity Class'larını oluşturmak gerekir. Bunları oluşturduktan sonra migration **Package Manager Console** ve **Dotnet CLI** olmak üzere iki türlü talimatla verilebilir.
* Her iki yöntemi de kullanabilmek için `Microsoft.EntityFrameworkCore.Tools` kütüphanesini uygulamaya yüklemeniz gerekmektedir.

```csharp
using Microsoft.EntityFrameworkCore;

//DbContext
public class ECommerceDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
    public DbSet<Customer> Customers {get; set; }
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder.UseSqlServer("Server=...");
    }
}

//Entity
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Quantity { get; set; }
    public float Price { get; set; }
}
public class Customer
{
    public int Id { get; set; }
    public string FirstName { get; set; }
    public string LastName { get; set; }
}
```



### Migration Oluşturma

Package Manager Console

- `add-migration[Migration Name]`

Dotnet CLI

- `dotnet ef migrations add[Migration Name]`

> Proje'de migrations klasörü altında bir sınıf oluşturulur ve içerisinde `Up` ve `Down` fonksiyonları tanımlanır.

**Nedir bu fonksiyonlar, ne işe yarar?**

> Up fonksiyonunda, migrate sürecinde veritabanı sunucusuna gönderilecek olan bütün yapılanmaları barındırır.
>
> Down fonksiyonunda ise, veritabanı sunucusunda yapılmış olan çalışmaları geri alır.



### Migration Path'i Belirleme

Package Manager Console

- `add-migration[Migration Name] -OutputDir [Path]`

Dotnet CLI

- `dotnet ef migrations add[Migration Name] --output-dir [Path]`



### Migration Silme

Package Manager Console

- `remove-migration`

Dotnet CLI

- `dotnet ef migrations remove`



### Migration'ları Listeleme

Package Manager Console

- `get-migration`

Dotnet CLI

- `dotnet ef migrations list`



### Migration'ları Migrate Etme!

> Up Fonksiyonu devereye girer.

Package Manager Console

- `update-database`

Dotnet CLI

- `dotnet ef database update`



### Migration'ları Geri Alma!

> Down Fonksiyonu devreye girer.

Package Manager Console

- `update-database  [Migration Name]`

Dotnet CLI

- `dotnet ef database update [Migration Name]`



### Kod Üzerinden Migrate Operasyonu

* Migration'ları tool aracılığıyla migrate edebildiğimiz gibi kod üzerinden de uygulamanın ayakta olduğu süreçte (rumtime'da) veritabanını migrate edebiliyoruz.

```csharp
AppDbContext context = new();
await context.Database.MigrateAsync();
```



### Son Uyarılar!

* Veritabanı sınıfları üzerinde yapılan tüm değişiklikleri migration eşliğinde gönderiniz. Böylece her bir değişiklikleri migration'lar ile kayıt altına almış olursunuz (bu da size veritabanı gelişim sürecini verir) ve ihtiyaca binaen istediğiniz noktaya geri dönüş sağlayabilirsiniz.
* Migration'lara mümkün mertebe dokunmamak lazım. Lakin ileride ihtiyaç doğrultusunda ham sql cümlecikleri ekleyeceğimiz ve hatta Stored Procedure gibi yapıları oluşturacağımız noktalar olacaktır.

