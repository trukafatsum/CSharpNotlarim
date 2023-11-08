# Entity Framework Core



## Entity Framework Core Nedir?

> EF Core, ORM yaklaşımını benimsemiş bir araçtır.

* Kod içerisinde OOP nimetlerinden istifade ederek SQL
  sorguları oluşturmamızı sağlamaktadır.

* Açık kaynaktır (Open Source)

* Esnektir

* Geliştirilebilir

* Kod içerisinde ihtiyaca binaen geliştirilmiş olan tekrarlı SQL sorgucuklarından bizleri kurtarmaktadır.

* Code First ve Database First yaklaşımları eşliğinde veritabanı ile yazılım arasındaki koordinasyonu sağlamaktadır.

  

* Kod üzerinden;

  * Veritabanı ve tablo,
  * Constraint,
  * Sequence,
  * İlişkili sorgular,
  * View
  * Stored Procedure
  * Function
  * Temporal Table

  gibi veritabanı nesneleri oluşturmamızı ve kullanmamızı sağlamaktadır.

* Query için LINQ sorgularını desteklemektedir.



### ORM Olarak Neden EF Core Seçilmelidir?

"EF Core, her ne kadar hızlı ve performanslı bir yapıya sahip olsa da piyasadaki en hızlı ORM aracıdır." diyemeyiz.

Misal olarak; minimal özelliklere sahip olan Dapper, Raw(ham) sorgular kullandığından dolayı kelimenin tam anlamıyla EF Core'dan çok daha hızlıdır.

Lakin her bir güncellemesinde performansının arttığı gözlemlenen EF Core'un ise birçok özelliği mevcuttur.

OOP nimetlerinden istifade etmemizi sağlayan EF Core ile class oluşturma, nesne değişikliklerini izleme (Change Tracker), mapping vs. gibi türlü işlemleri gerçekleştirebiliriz.



### EF Core Nasıl Yüklenir?

İleride EF Core ile migration yapılanmalarına vs. değiniyor olacağız. İşte bu yapılanmaları sağlayabilmek ve işlevleri yürütebilmek için belirli araçları yüklememiz gerekmektedir.

<u>Yüklenecek araçlar</u>

- .Net Core command-line interface (CLI) tools

- Package Manager Console (PMC) tools

  olmak üzere iki farklı kümede değerlendirilebilir.



### .Net Core command-line interface (CLI) tools

**dotnet-ef** ile başlayan CLI komutlarını ilgili PC'de aktif olarak kullanabilmemizi sağlayan tool'dur.

​	Install => `dotnet tool install --global dotnet-ef`

​	Update => `dotnet tool update --global dotnet-ef`

​	Check => `dotnet ef`

> Tool'u yükledikten sonra belirli bir projede kullanabilmek için ilgili projede şu paketin de yüklü olması gerekmektedir.
>
> `Microsoft.EntityFrameworkCore.Design`



### Package Manager Console (PMC) tools

Visual Studio, Package Manager Console üzerinden talimatlar vermemizi sağlayan bir tool'dur.

> Haliyle Package Manager Console üzerinden talimatlar verebilmek için şu paketin ilgili projede yüklü olması gerekmektedir.
>
> `Microsoft.EntityFramework.Tools`

