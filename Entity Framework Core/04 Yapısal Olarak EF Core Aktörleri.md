# Entity Framework Core



## Yapısal Olarak EF Core Aktörleri

* Bir ORM aracının veritabanını OOP nimetleriyle temsil edebilmesi için veritabanının, o veritabanı içerisindeki tabloların ve o tablolar içerisindeki kolon ve nesnelerin programatik olarak bir şekilde modellenmesi gerekmektedir.
* Bu modelleme class'lar üzerinden gerçekleşecektir.



### Veritabanı Nesnesi - DbContext

* EF Core'da veritabanını temsil edecek olan sınıf DbContext olarak nitelendirilmektedir.

<img src=https://i.imgur.com/dC6i1OQ.png width=75% align=left />



#### DbContext Nesnesinin Sorumlu Olduğu Faaliyetler Nelerdir?

* **Konfigürasyon**
  Veritabanı bağlantısı, model yapılanmaları ve veritabanı nesnesi ile tablo nesneleri arasındaki ilişkileri sağlar.
* **Sorgulama**
  Sorgulama operasyonları yürütür. Kod tarafında gerçekleştirilen sorgulama adımlarını SQL sorgusuna dönüştürür ve veritabanına gönderir.
* **Change Tracking**
  Sorgulama neticesinde elde edilen veriler üzerindeki değişiklikleri takip eder.
* **Veri Kalıcılığı**
  Verilerin kayıt edilmesi, güncellenmesi ve silinmesi operasyonlarını gerçekleştirir.
* **Caching**



### Tablo Nesnesi - Entity

* EF Core'da tabloları temsil edecek sınıflar Entity olarak nitelendirilmektedir.

  > Entity tam olarak nedir?
  > Yer yüzündeki herhangi bir olguyu/nesneyi/objeyi modelleyen sınıfa Entity(varlık) denmektedir.
  > EF Core açısından baktığımızda entity, bir veritabanı tablosunu modelleyen sınıftır.

<img src=https://i.imgur.com/O1ea7vn.png width=85% align=left />

> Burada şunu demiş oluyoruz.
> Veritabanında şu entity(DbSet<.T>) modeline karşılık bir tablo bulunmaktadır.
> İşte bu tabloyu şu property ile temsil et `public DbSet<Table> Tables{get; set;}`, demiş oluyoruz.



### Tablo Kolonları

* EF Core'da bir tabloyu temsil eden sınıfa entity demiştik. Haliyle kolonlar da entity sınıfları içerisinde property olarak tanımlanmalıdırlar.

```csharp
using Microsoft.EntityFrameworkCore;
//Bir entity içerisindeki property'ler, o entity'nin modellediği tablo içerisindeki kolonlara karşılık gelmektedir!
public class NorthwindDbContext : DbContext
{
    public DbSet<Customer> Customers{get; set;}
}
public class Customers
{
    public int CustomerId {get; set;}
    public string Name {get; set;}
    public string ContactTitle {get; set;}
}
```



### Veriler

* Veritabanındaki veriler ise entity'lerin instance'larına karşılık gelmektedir.

<img src=https://i.imgur.com/soBq5gt.png width=65% align=left />

> ```csharp
> new Customer();
> ```
>
> EF Core tablolar içerisindeki verileri, entity'lerin instance'ları olarak temsil etmektedir.



### Özetle

> DbContext veritabanını temsil eder.
> Entity veritabanının içerisindeki tabloları temsil eder.
> DbContext içerisine `public Dbset<Table> Tables {get; set;}` propertisini oluşturarak entity olan `Table` sınıfına erişim sağlanır.
> Böylelikle bu entity sınıfından instance'lar üreterek (`new Table();`) ile verileri temsil ederiz.

<img src=https://i.imgur.com/5LWRb46.png width=75% align=left />