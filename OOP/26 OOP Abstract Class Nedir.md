# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Abstract Class



### Abstract Class Nedir? Neden Kullanırız?

* Nesne Tabanlı Programlama'nın önemli kavramlarından ve davranışlarından biri inhetirance(kalıtım)'dır. Kalıtım sayesinde bizler sınıflar arasında hiyerarşik ilişkiler oluşturabilmekte ve nesneler içerisindeki elemanları miras yoluyla birbirlerine aktarabilmekteyiz.
* Böylece ortak işlevselliklere sahip olan sınıfları kalıtımsal davranışla şekillendirerek tekrarlı kod yazımını azaltmakta ve okunabilirlik ile yeniden kullanabilirliği arttırabilmekteyiz.
* Abstract Class'ı bu niyetle kullandığımız kalıtımsal davranışı daha farklı manevralarla kullanabilmek için düşünülmüş ve geliştirilmiş olan bir nesnel yapı olarak tanımlayabiliriz.

> Abstract Class, özünde kalıtımsal davranış göstererek bir sınıf üzerinde implementasyonlar yapmamızı sağlayan özel bir yapılanmadır!
>
> Burada implementasyondan kastedilen ne olduğunu dersimizin ileriki dakikalarında netleştireceğiz. Şimdilik odaklanacağımız nokta abstract class'ın varlık sebebidir. Abstract class, bizlere yarı somut bir sınıf vermektedir.
>
> Yani somut sınıftan kastedilen ise içerisinde normal member'ların barındırılabileceği gibi kendisini uygulayan sınıflara zoraki uygulattırabileceği member'ların imzalarını barındıran bir yapılanmadır.

```csharp
abstract class MyClass
{
    public void X()
    {
        //..
    }
    public void Y()
    {
        //..
    }
    public int Z{get; set;}
    //-----------------------------
    abstract public void W();
    abstract public int Q();
    abstract public int H {get; set;}
}
```

> Yukarıdaki kodda görüldüğü üzere bir abstract vlass içerisinde normal member'lar tanımlanabileceği gibi,
>
> Kalıtımsal olarak bu abstract class'ı uygulayan sınıflara zoraki olarak uygulattırılacak member imzaları da tanımlanabilmektedir.

> Merak etme daha abstract class'ın nasıl ve hangi kurallarla oluşturulduğundan bahsetmedik ☺ 
> Haliyle burada sana durumu örneklendirmek için hızlıca göstermiş bulunuyorum. 
> Tüm bu yapılanmanın detaylarına birazdan adım adım giriyor olacağız.

<img src=https://i.imgur.com/a2LA3FP.png align=left />

> Yazılım süreçlerinde abstract class'ları kullanma nedeni herhangi bir ihtiyaca istinaden değildir! Abstract class'lar tercihen kullanılan yapılardır!
>
> Genellikle abstract class'lara direkt gereklilik olduğu bir durum hiçbir zaman söz konusu olmayacaktır. Ancak belirli durumlarda iradeli bir şekilde abstract class'lar ile davranış sergilemeyi tercih edebilir ve varsa sorunlarınız daha basitleştirici unsur olarak abstract class'ları kullanabilirsiniz.
>
> Şöyle ki, bir abstract class ile kalıtımsal olarak aktarmak istediğimiz davranışlarla birlikte zoraki olarak uygulatmak istediğimiz davranışları bir bütün olarak tasarlayabilirsiniz.
>
> Ve bu tasarıyı istediğimiz sınıflara uygulatarak hem kalıtımsal aktarımda bulunabilir hem de o sınıflar içerisinde zorunlu olarak ilgili davranışları tanımlatabilirsiniz.
>
> Böyle bir davranışın gerekli olduğu bir senaryoyu söylememiz pek mümkün değildir, lakin bu tarz bir davranışı gerçekleştirebilmemiz için abstract class'lardan istifade edebilirsiniz.



### Abstract Class'ın Yapısal Özellikleri Nelerdir?

* Abstract Class'ın ilk bilinmesi gereken özelliği her ne kadar abstract olsa da özünde bir class'tır. Yani referans türlü bir yapılanmadır.

  Dolayısıyla abstract class türünden belleğin stack bölgesinde bir referans noktası edinilebilir ve bu referansla heap'teki uygun nesneler işaretlenebilir.

#### Abstract Class İle Nesne Arasındaki İlişki

Abstract Class'lar soyut yapılanmalar olduğu için yapısal olarak iradeli bir şekilde (new operatörü ile vs.) nesne üretilebilir bir tür değildir!

> `new MyClass();` Yani bu şekilde bir abstract class'tan nesne üretmeye çalışmak mümkün değildir!
>
> Ama bu abstract class türünden bir nesne hiçbir zaman olamaz anlamına gelmemektedir.

Kalıtımsal olarak bir abstract class herhangi bir sınıfa miras verdiği taktirde buradaki davranış şöyle olacaktır;

> ```csharp
> abstract class MyClass
> {
>     
> }
> class MyClass2 : MyClass
> {
>     
> }
> ```
>
> Yukarıdaki gibi kalıtımsal durumun söz konusu olduğu durumlarda, `new MyClass2();` komutu ile MyClass2 isimli sınıftan bir nesne üretilirse eğer, burada kalıtımsal hiyerarşinin gereği olarak abstract class'ın da dahil normal class'ın nesneleri üretilecektir.

#### Abstract Class'ta Constructor Tanımlama

Kalıtımsal durumlarda abstract class'ların nesneleri oluşturuluyorsa eğer bu constructor'ları tetikleniyor demektir! Haliyle bizler irademizle her ne kadar abstract class'lardan nesne üretemesekte, içerisinde constructor tanımlayabilir ve kalıtımsal süreçlerdeki üretilecek olan nesneyi yapılandırabiliriz.

```csharp
abstract class MyClass
{
    public MyClass
    {
        //..
    }
}
```



### Tanımlama ve İnşa Etme Kurallarını Toparlayalım

* Abstract Class'lar tanımlanırken şu kurallar geçerlidir :

  * Bir abstract class tanımlayabilmek için abstract class keyword'ü kullanılır!

  * Bir abstract class içerisine member'lar bilinen kurallarıyla eklenebilir.

    * Normal metotlar ve property'ler eklenebilir,

      ya da

      * Bu abstract class'ı implement edecek olan sınıflarda zoraki tanımlanmasını isteyeceğimiz member imzaları da eklenebilir. Bu imzalar, gövdeleri ilgili alt sınıflara bırakılacak şekilde abstract keyword'ü ile işaretlenerek tanımlanmalıdır. Tabi abstract keyword'ü ile işaretlenmiş olan member'lar kendilerini uygulayan sınıflar tarafından erişileceği için zoraki public olmak zorundadır.
    
  * Bir abstract class'ı uygulayan sınıf içerisinde normal member'lar direkt miras yoluyla aktarılırken, abstract ile işaretlenmiş olan member'lar ise ilgili sınıf içerisinde override edilmek zorundadır.
  
    <img src = https://i.imgur.com/iG61P17.png align=left />
  
    Abstract Class'ı uygulayan/implemente eden sınıflara terminolojik olarak Concrete Class denir!

```csharp
//Abstract Class içerisindeki abstract yapıların concrete class içerisindeki tanımları public olmak zorundadır!
```



### Abstract Class'ı Uygulamaktan Kastettiğimiz Nedir?

* Abstract Class'ın söz konusu olduğu durumlarda implementation yani 'uygulama' fiiliyatı mevzu bahistir. Ki bu durum sonraki derste göreceğimiz interface içinde geçerlidir.

* Peki nedir implementation?

  Implementation, abstract class'ın bir sınıfa kalıtım vermesidir. Yani başka bir deyişle kalıtımsal bir ilişkinin olduğu bir durumda eğer ki base class bir abstract class ise biz oradaki durumu implementation olarak nitelendirmekteyiz.

  <img src = https://i.imgur.com/Pl5fVWH.png width=65% align=left />

  Implementasyon'dan kastedilen şudur ki, *abstract class içerisinde tanımlanmış* olan *bazı imzaların(abstract işaretli)* kalıtımsal davranış neticesinde zoraki olarak alt sınıfa uygulattırılması ya da başka deyişle oluşturulmasıdır!

<img src = https://i.imgur.com/00WXt0q.png width=65% align=left />



### Abstract Class'ın Abstract Class'tan Türemesi

* Bir abstract class, başka bir abstract class'a miras verebilir.
* Burada dikkat ederseniz bir abstract class'ın başka bir abstract class'a miras vermesi, implementation olarak nitelendirilmemektedir.
* Bu düpedüz bir kalıtımdır. Çünkü abstract class'lar içlerinde abstract olarak işaretlenmiş olan yapıları zoraki olarak sadece kendilerini uygulayan sınıflara uygulattırırlar, abstract class'lara değil!

```csharp
abstract class MyClass
{
    abstract public void W();
    abstract public int Q();
    abstract public int H {get; set;}
}
abstract class MyClass2 : MyClass //Inheritance
{
    abstract public void W();
    abstract public int Q();
    abstract public int H {get; set;}
}
class MyClass3 : MyClass2 //Implementation
{
    //..
}
```



### Abstract Class Referansı İle Nesneyi İşaretleme

> Abstract class yapısal olarak bir referans türlü değişken olduğu için polimorfizm kuralları gereği kendisini uygulayan tüm sınıfları ve bu sınıflardan kalıtım alan alt sınıfları referans edebilmektedir.

#### Abstraction Açısından Değerlendirelim

> Bir sınıf üzerinde abstraction davranışını gerçekleştirirken ihtiyaçlar ve senaryosuna göre abstract class'lardan istifade ederek elverişli bir şekilde uygulayabilirsiniz.



### Özetlersek

* Bir sınıfın uyması gereken temel yapıyı tanımlamak için abstract class yapısını kullanabilir ve gerekli modellemeyi gerçekleştirebilirsiniz.
* Abstract class'lar, bir çeşit abstraction yapılanmasıdır. Davranışların var olduğunu garanti eder, lakin davranışın implementasyonunu interface'ler de ki gibi zorunlu kılmaz!
* Abstract class'lar, interface'ler ile concrete/normal class'lar arasında bir yapıdır.
* Abstract class'lar, birçok senaryo için geçerli olabilecek genel davranışlar sağlayabileceği ancak kimi senaryolar için ise özel davranışlarda barındırabileceği bir sözleşmedir.
* Abstract class, doğrudan inheritance ve polimorfizm ile bağlantılı bir kavramdır. Özellikle inheritance olmaksızın abstract class kullanılmaz! Keza inheritance amaçlı kullanılan yapı abstract class ise o zaman oradaki ifadeye implementation denir.
* Abstract class'lar (interface'ler de aynı şekilde) loose coupling'i destekler.
