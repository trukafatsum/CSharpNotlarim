# Entity Framework Core



## ORM Nedir?

> ORM Yaklaşımını anlayabilmek için öncelikle olmadığı durumları aşağıda inceleyelim.

### Yazılım ve Veritabanı Arasında Temel İlişki Hakkında

> Yazılım uygulamalarında veriler fiziksel olarak veritabanlarında tutulmaktadır!
>
> Haliyle yazılım ile veritabanı arasında sürekli bir bağlantı üzerinden iletişim sağlanmaktadır!
> Ki yazılım dış dünyadan elde ettiği verileri veritabanına işleyebilsin yada veritabanındaki verileri istediği zaman elde edebilsin.
>
> İşte böyle bir durumda yazılım ile veritabanı arasında biraz önce bahsedildiği üzere bir bağlantı kurularak tüm verisel trafik gerçekleştirilmektedir.
> Yazılım, bu bağlantı üzerinden veritabnına anlayacağı dilden sorgular gönderir ve veritabanı da bu sorgulara istinaden gerekli verisel işlemleri gerçekleştirir.
> Bu sorgular genellikle SQL dilindedir.



### Yazılım ve Veritabanı arasında Temel İlişki Modeli

<img src=https://i.imgur.com/gXowSnN.png width=75% align=left />

> MS SQL örnektir, farklı bir veritabanı da olabilir.



### Kodun İçerisine Gömülü SQL Cümleciği

```csharp
using System.Data.SqlClient;
await using SqlConnection connection = new("Server=localhost, 1234;Database=Northwind;User Id=sa;Pasword=...");//Sql Bağlantı cümleciği ve sql bağlantı nesnesi oluşturma
await connection.OpenAsync(); //Sql bağlantısını açma

SqlCommand command = new("Select * from Employees", connection); //Açılan bağlantıda sorgu gönderme
SqlDataReader dr = await command.ExecuteReaderAsync(); //Gelen sorguyu dr referansına çekme
while (await dr.ReadAsync())//Tüm içerikler okunana kadar şartı ile döngü
{
    Console.WriteLine($"{dr["FirstName"]} {dr["LastName"]}"); //Okunan içerikteki satırları tek tek işleme
}

await connection.CloseAsync(); //Sql bağlantısı kapatma
```

> Dikkat ederseniz kod içerisinde SQL sorguları yazılmaktadır.

**Peki bu durum nelere sebep olmaktadır?**

* Kodun içerisinde SQL sorguları ve SQL ile ilgili farklı cümleciklerin olması genel anlamda kodun kirlenmesine sebep olmaktadır!

  Bir kod metinsel ifadelere çok fazla boğuluyorsa ister istemez kirlenmektedir. Bunun dışında farklı bir dilin,yapınn , servisin, veritabanı gibi sunucuların anlayacağı bir semantikte olması gerekiyorsa bu daha da kirlenmiştir. Bugün `Employess`olan yarın farklı bir tablo olabilir. Dolayısıyla bu kod bağlayıcılık sağlayacaktır.

* Bunun dışında geliştiricinin SQL hakkında olan bilgisinin endişe verici olmaması gerekmektedir!

  Kodun içerisine SQL cümlesi yazan kişinin veya geliştiren ekibin SQL veritabanı hakkında bilgisi olması gerekmektedir.

* Ayrıca veritabanına gönderilen SQL neticesinde gelen datalar manuel parse edilmek zorunda bu da kodun SQL'e olan bağlılığını arttırdığı gibi yönetilebilirliğini de oldukça kısıtlamaktadır.

  Sorgu neticesinde dönecek olan sütunlar, `FirstName` mi `LastName`mi yoksa başka bir isimde mi bilinmeyeceği için yönetilebilirlik açısından kısıtlanmaktadır.

> Yani uzun lafın kısası kodun içerisinde SQL cümleleri yazmanın ve veritabanından gelen sonuçların manuel bir şekilde parse edilmesinin büyük projelerde büyük problemler doğrurabileceği aşikardır.
>
> Günün birinde x veritabanından y veritabanına geçiş yapılacak olduğu taktirde, kodun içerisindeki bütün sorguları refactoring etmek gerekmektedir.



### Kod İçerisinde SQL Yazmanın Dezavantajları

* Kodun kirlenmesini sağlar!
* Geliştirme ve bakım maliyeti yüksek kod inşasına sebep olur.
* *Veritabanı bağımlılığı yaratır.*
* Kompleks sorgular manuel bir şekilde oluşturulması gerekir.
* Geliştirici açısından SQL sorumluluğu beklenir.
* Veritabanı sorgulama neticesinde gelen datalar manuel olarak dönüştürülür. Sorgu sürecinde tablo, kolon vs. gibi bağımlılıklar olduğu gibi gelen datalarda da aynı bağımlılıklar söz konusu olacaktır.
* Veritabanında olan değişikliklere uygun bir şekilde kodun tekrar review edilmesi gerekir!
  Misal bir kolon adı değiştiğinde ya da bir kolonun herhangi bir kuralı (constraint, validation vs.) değiştiğindee bu durumdan kodun haberdar olması için bilinçli bir review gerekmektedir.
* Kodu aşırı derecede veritabanı seviyesine indirger. Bu durum tüm gelişmelerin veritabanıyla uyumlu bir şekilde seyretmesi zorundalığı doğurur.
* Geliştirilen yazılımın sürecinde tüm veritabanı işlemleri, o anki kullanılan programlama dili ve OOP'nin nimetlerinden istifade etmeksizin icra edilir.

* *Gün gelir veritabanını değiştirmeniz gerekebilir. İşte böyle bir durumda tüm SQL kodlarını yeni veritabanına göre Refactoring etmemiz gerekecektir!*



### Sonuç  olarak : ORM

> Yazılım ve veritabanı arasındaki bağlantı üzerinden sorgular eşliğinde veri transferini OOP nimetlerinden istifade ederek sağlayabileceği ve böylece kodun da, geliştiricinin de SQL'e bağlılığı olmaksızın hızlı ve kolayca operasyonları gerçekleştirebileceği bir yaklaşım ortaya konmuştur.
>
> Bu yaklaşımın adı ORM'dir.
>
> ORM : Object Relational Mapping yani (Nesne İlişkisel Eşleme) şeklinde bir açılıma sahiptir.



### Object Relational Mapping

> Geliştirilen yazılım içerisinde OOP yapısına uygun olmayan, katı ve kompleks veritabanı sorguları yerine veritabanı objelerinin, bir OOP nesnesi gibi düşünülerek yazılım tarafından kullanılabilmesine olanak sağlayan bir yaklaşımdır!
>
> Bu yaklaşıma göre veritabanı, tablolar ve veriler yazılım tarafında birer nesneye karşılık gelmektedirler. Böylece tüm veritabanı süreçlerini OOP kavramlarıyla rahatlıkla yönetilebilir ve kodu SQL'den arındırabiliriz.

> Simülasyon :
>
> <img src=https://i.imgur.com/laT7k6c.png align=left />
>
> **Karşılaştırma :**
>
> <img src=https://i.imgur.com/0wFn14F.png width=75% align=left />



### ORM Avantajları

* Veritabanı bağımsızlığı sağlar!
* Kullanılan veritabanına göre uygun sorgu oluşturur.
* OOP nimetlerinden faydalanarak SQL mantığı işlenmesini sağlar.
* Geliştiricinin kullanılan veritabanına dair SQL yeteneklerinin olması beklenmez!
* Sorgular otomatik generate edileceğinden dolayı kodu SQL bağımlılığından soyutlar.