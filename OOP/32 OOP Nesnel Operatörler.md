# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Nesnel Operatörler



### Giriş

Konu içerisinde OOP'de kullanılan bazı operatörleri ele alacağız. Bunlar :

* Null Conditional Operatörü - ?.
* Null Coalescing Assignment Operatörü - ??=
* Null(?) Operatörü & Nullable<.T>
* is Operatörü



### Null Conditiional Operatörü - ?.

> Null Conditional operatörü, referanslara güvenli bir şekilde erişim yapmamızı sağlayan bir özelliktir.

* Bu operatör, bir referansla null olup olmadığını kontrol etmeksizin işlem yapabilmemizi sağlamaktadır.

```csharp
Person person = null;
if (DateTime.Now.Day == 30)
    person = new();

Console.WriteLine(person.Name)
class Person
{
    public string Name {get; set;}
}
```

Böyle bir çalışma yapacak olursak, null olan bir referansın herhangi bir property'sini veya member'ını çalışmaya çalışınca `NullReference` hatası alacağız.
Haliyle burada bir şart belirtmemiz gerekir, aşağıdaki gibi eğer ki person null değilse bu işlemi gerçekleştir dememiz gerekir.

```csharp
Person person = null;
if (DateTime.Now.Day == 30)
    person = new();
if (person != null)
    Console.WriteLine(person.Name)
class Person
{
    public string Name {get; set;}
}
```

* Bu operatör meşhur null referans hatalarını önlemek için kullanılır.

```csharp
Person person = null;
if (DateTime.Now.Day == 30)
    person = new();
Console.WriteLine(person?.Name)
class Person
{
    public string Name {get; set;}
}
```

- Null Conditional operatörü Property'lerde `set` durumunda kullanılamaz.



#### Kritik

> Bu operatör aşağıdaki gibi özellikle derinlemesine nesne zincirlerini veya metot çağırılarını işlerken oldukça faydalıdır! Eğer zincir içerisindeki herhangi bir değer null ise, operatör null dönecek ve sonraki çağrıya geçmeyecektir.

```csharp
Person person = new();
/*
if (person != null)
{
	if (person.Brach != null)
	{
		if (person.Branch.Department != null)
		{
			var departmentName = person.Branch.Department.DepartmentName;
		}
	}
}
*/
var departmentName = person?.Branch?.Department?.DepartmentName;
class Person
{
    public string Name {get; set;}
    public Branch Branch {get; set;}
}
class Branch
{
    public string BrachName {get; set;}
    public Department Department {get; set;}
}
class Department
{
    public string DepartmentName {get; set;}
}
```



### Null Coalescing Assignment Operatörü - ??=

> Null Coalescing Assignment operatörü, bir değişkenin değerini yalnızca null ise başka bir değerle değiştirmek istediğinde kullanılan bir atama operatörüdür.

```csharp
Person person = null;
person ??= new();
//---------
int? n = 15;
n ??= 3;
```

* Bu operatör bir değişkenin değerini kontrol eder, eğer değer null ise sağ taraftaki ifadeyi ilgili değişkene atar, yok eğer null değilse mevcut değeri değiştirmeksizin yoluna devam eder.
* Yani anlayacağınız bu operatör, bir değişkenin var olan değerini korumak istediğiniz durumlar için faydalı bir işleve sahiptir.



### Null(?) Operatörü & Nullable<.T>

> Null(?) operatörü veya Nullable<.T> türü, C#'ta değer türlü değişkenlerin null olabilmesini sağlayan yapılanmalardır.

* C#'ta değer türlü değişkenler normal şartlarda değer yokluğu anlamına gelen null ifadesini kabul etmezler. Ancak bazı senaryolar gereği, bir değer türlü değişkenin null olması gerekebilmektedir. Bu gibi durumlar için null(?) operatörü yahut Nullable<.T> referansı kullanılabilir.

```csharp
int? no1 = null;
Nullable<int> no2 = 3;
```

- Null(?) operatörü ile Nullable<.T> referansı arasında işlevsel olarak herhangi bir fark bulunmamaktadır.
  Her ikisi de değer türlerin null değer alabilmesi için kullanılan farklı syntax'lardır.
- Nullable<.T> referansı, Null(?) operatöründen önce kullanılmaktaydı. Haliyle Null(?) operatörü bu işlem için daha mederndir ve yaygın olarak kullanılmaktadır.



### is Operatörü

> is Operatörü, bir değerin hangi türde olduğunu kontrol etmemizi sağlayan bir operatördür.
>
> Bunun yanında bir nesnenin değerlerini kalıpsal olarakta değerlendirmemizi sağlayabilmektedir.

```csharp
if (p is {Name:"Şuayip", Age: >=30, Surname.Length: > 5})
{
    //...
}
```



#### Pratik

```csharp
Person person = new()
{
    Name = "Hilmi",
    Age = 30,
    Married = true
};
/*
if (person.Name == "Hilmi" && person.Age >= 20)
{
    //..
}
*/
if (person is {Name:"Hilmi",Age:>=20,Married:true})
{
    //..
}

class Person
{
    public  string Name {get; set;}
    public int Age {get; set;}
    public bool Married {get; set;}
}
```

