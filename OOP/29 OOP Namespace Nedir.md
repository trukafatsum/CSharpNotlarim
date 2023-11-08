# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Namespace



### Namespace Kavramı Nedir?

> C#'ta namespace kavramı kod organizasyonunu sağlamak için kullanılan bir yapılanmayı ifade etmektedir.

* namespace yapılanması ile program kapsamında kullanılacak olan class'ları, record'ları, struct'ları, interface'leri vs. gruplayarak kodsal açıdan düzenli ve tertipli bir inşa gerçekleştirilebilmektedir.
* Böylece namespace sayesinde kod tabanı daha organize bir hale gelmekte ve farklı bileşenler daha derli toplu bir düzende yönetilebilmektedir.

<img src=https://i.imgur.com/ckFhoQc.png width=75% align=left />

> Görüldüğü üzere bir namespace, benzer türdeki/işlevdeki/davranıştaki bileşenlerin bir arada bulunmasını sağlar ve böylece kodun okunabilirliğini arttırır.



### Namespace Nasıl ve Nerede Tanımlanır?

> namespace tanımlayabilmek için yapılması gereken namespace keyword'ünü aşağıdaki gibi kullanılmaktadır.
>
> ```csharp
> namespace MyNamespace
> {
>     
> }
> ```
>
> Görüldüğü üzere namespace ifadesinden sonra bir isim verilerek tanımlama gerçekleştirilmektedir.

* namespace tanımlamasından sonra bu scope içerisine istediğimiz bileşeni (class, record, struct, interface, abstract class) tanımlayabilirsiniz.

* namespace'i herhangi bir C# dosyasında (.cs) direkt tanımlayabilirsiniz. Bunun dışında namespace içerisinde namespace tanımlaması da gerçekleştirebilirsiniz. (Nested Namespace)



### File Scoped Namespace Declarations

* Namespace'i dosya bazlı bir şekilde de tanımlayabilmekteyiz, Şöyle ki:

```csharp
namespace MyNamespace;
class MyClass
{
    
}
struct MyStruct
{
    
}
interface IInterface
{
    
}
```

> Bu tanımalamaya dikkat ederseniz, namespace'in scope'ları oluşturulmamıştır. Bu şekilde tanımlama dosya odaklı bir namespace oluşturmakta ve bu dosyada tanımlanacak olan tüm yapıları bu namespace altında oluşturmaktadır.
>
> File Scoped Namespace kullanıldığı durumlarda nested namespace kullanılamaz!



### Namespace'lerin Dağıtık Tanımlaması

* Namespace'leri uygulama bazında dağıtık bir şekilde de kullanabilmekteyiz. Şöyle ki:

  ```csharp
  //file1.cs
  namespace X
  {
      class MyClass1
      {
          
      }
  }
  //file2.cs
  namespace X
  {
      class MyClass2
      {
          
      }
  }
  //Compiler bunu tekil bir namespace olarak değerlendirecektir.
  ```

  Yani anlayacağınız farklı dosyalarda/konumlarda/dizinlerde tanımlanmış aynı derecedeki namespace'ler compiler açısından bir bütün olarak değerlendirilmektedirler!



### Namespace İçerisinde Ne Tanımlanır?

* Namespace içerisinde tanımlanabilecek bileşenler şunlardır :
  - Class
  - Record
  - Struct
  - Abstract Class
  - Interface
  - Delegate
  - Enum
  - Nested Namespace
  - Record Struct



### Namespace İçerisindeki Bir Bileşene Nasıl Erişilir?

* Namespace içerisindeki herhangi bir bileşene erişim gösterebilmek için o namespace'in isminden istifade edilmektedir. Şöyle ki:

  ```csharp
  namespace MyNamespace1
  {
      class MyClass
      {
          
      }
  }
  ```

  ```csharp
  MyNamespace1.MyClass m = new();
  ```

  Yukarıdaki kullanıma göz atarsanız eğer 'MyClass' türüne ihtiyaç olduğu taktirde namespace adı üzerinden buna erişim gösterebilmekteyiz.

  Tabi her 'MyClass' ihtiyacına karşılık namespace'in adını yazabileceğimiz gibi bunu çalıştığımız dosya bazlı tek seferlikte tanımlayabilir ve daha pratik bir çalışma gerçekleştirebiliriz.

  ```csharp
  using MyNamespace1;
  MyClass m = new();
  ```

  Bunun için yukarıdaki gibi using keyword'ü eşliğinde dosyanın en üstünde bir tanımlama yapmamız yeterli olacaktır.

  Bu tnaımlama neticesinde using ile belirtilen namespace içerisindeki tüm bileşenler ilgili dosya içerisinde direkt erişilebilir olacaktırlar.

> using keyword'ü yaptığı bu işin dışında farklı davranışlara ve detaylara da sahip bir keyword'dür. Haliyle gelin şimdi namespace ile ilgili using keyword'ünün diğer detaylarını da masaya yatırmaya başlayalım.



### Using Direktifi & Static Using

> using keyword'ü biraz önce de gördüğümüz gibi bir namespace altındaki bileşenleri, o namespace adını belirtmeye gerek kalmaksızın kullanmamıza izin veren bir keyworddür.

* İsterseniz using keyword'ü ile belirttiğiniz herhangi bir namespace'e alias atayarak kullanabilirsiniz.

  `using m = MyNamespace1;`

  Böylece using keyword'ü ile birden fazla namespace'in tanımlandığı çalışmalarda atanan alias'lar sayesinde daha rahat çalışma gerçekleştirebilirsiniz.

* Ayrıca using ile tanımlanmış olan namespace içerisindeki bileşenlerin static member'larına da kolayca erişim gösterebileceğimiz static using tanımı da kullanabiliriz.

  ```csharp
  using static MyNamespace1.MyClass;
  X();
  namespace MyNamespace1
  {
      class MyClass
      {
          public static void X()
          {
              //..
          }
      }
  }
  ```

  Static using tanımı sayesinde kodlama sürecinde ihtiyaç olan static member'lara erişim kolaylaştırılmakta ve sınıf isimlerinden kaynaklı kalabalığa kısmi çözüm sağlanabilmektedir.

> Namespace'in dışında using keyword'ünün C# programlama süreçlerinde farklı kullanım durumlarına karşılık farklı davranışları da söz konusudur. Zamanı geldikçe bu davranışları da inceliyor olacağız.



### Global Operatörü

> Kimi namespace'ler vardır ki uygulamanın hemen hemen her yerinde sık sık kullanıldıkları için using ile bildirilmek durumunda kalınmaktadırlar.

* Bizler bu namespace'leri her ihtiyaç doğrultusunda using ile bildirmektense global keyword'ü eşliğinde tek seferlik uygulama seviyesinde tanımlama şansına sahibiz.

* Bunun için iki farklı yaklaşım sergileyebiliriz:

  * .csproj Dosyasından Global Using

    Bu yöntemde uygulamanın .csproj dosyasında `<ItemGroup>...</ItemGroup>` etiketi arasında using bildirimleri gerçekleştirilmektedir.

    Bu tanımlama yapıldıktan sonra uygulamayı derlerseniz eğer `<<project-name>>.GlobalUsing.g.cs` şeklinde bir dosya çıktısı göreceksiniz. Bu dosyaya göz atarsanız eğer .csproj içerisine yapılan tüm namespace'lerin buraya global eklendiğini göreceksiniz.

    > Burada tanımlaması yapılmayan namespace'lerin de geldiğini görmekteyiz. Bunun nedeni 'PropertyGroup' içerisindeki 'ImplictUsing' özelliğidir. Bu özellik enable olduğu taktirde bir uygulama için genel geçer namespace'ler buradaki otomatik generate edilen global using sınıfı içerisine default olarak eklenmektedir. Bunu engellemek istiyorasnız ilgili özelliği disable olarak ayarlamanız yeterli olacaktır.

  * Herhangi bir .cs Dosyasında Global Using

    Bu yöntemde ise uygulamadaki herhangi bir .cs dosyası global tanımlama amaçlı kullanılmaktadır.

    `global using MyNamespace1;` gibi..



### :: Operatörü

> C#'ta :: operatörü kullanım durumuna bağlı olarak iki farklı şekilde davranış sergileyebilmektedir.

* Birinci olarak uygulamadaki namespace'lere global keyword'ü üzerinden erişim gösterebilmemize olanak vermektedir.

  ```csharp
  using System.Threading.Channels;
  
  global::MyClass m1 = new();
  global::MyNamespace1.MyNamespace2.MyClass m2 = new();
  
  m1.Write();
  m2.Write();
  
  class MyClass
  {
      public void Write() => Console.WriteLine("Global MyClass");
  }
  namespace MyNamespace1
  {
      namespace MyNamespace2
      {
          class MyClass
          {
              public void Write() => Console.WriteLine("Local MyClass");
          }
      }
  }
  ```

* İkinci olarak ise alias atanmış namespace'ler içerisindeki yapılara erişim gösterebilecek davranışı sergilemektedir.

  ```csharp
  using Globalization = System.Globalization;
  using MT = MassTransit;
  
  Globalization::CalenderWeekRule weekRule =
  Globalization.CalenderWeekRule.FirstDay;
  MT::ExcludeFromImplementedTypesAttribute attribute = new();
  ```

  

### Namespace'lerin Kullanılmasının Başlıca Nedenleri Nelerdir?

* Kod Organizasyonu
* Çakışmaları Önlemek
* İsim Çatışmaları Çözmek
* İsim Alanını Belirtmek
* İlişkili Kod Parçalarını Gruplandırmak
* Harici Kütüphaneleri İçe Aktarmak