# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Static Yapılar

> Static yapılar, bir uygulamanın uygulama seviyesinde işlem yapmamızı sağlayan tekil yapılardır.



### Programlamada Static Ne Demek?

> Static terimi farklı bağlamlarda farklı anlamlara gelebilen önemli bir terimdir.
> Bu terim varlık nedenini anlayabilmek için öncelikle static yapılanmanın, programlama sürecinde nasıl bir davranış kazandırdığına odaklanmamız gerekir.



### Uygulama Bazında Evrensel Nokta 'Static'

> Static, uygulama bazında evrensel çalışmalar yapabilmemizi sağlayan yapıları ifade eden bir kavramdır.
> Bu kavramı daha net anlayabilmek için RAM'in yapısına tekrar odaklanmamız gerekmektedir.

* Static'te değer türlü değişkenler ve değerler barındırırız ve bunlara tanımlandıkları scope aralığında erişim göstermekteyiz.
* Heap'te ise instance'larımız barındırılır ve bu instance'lara refere edildikleri yerlerden erişilebilmektedir.

<img src=https://i.imgur.com/D4wdQiB.png align=left />

* Programın çalışma süresi boyunca aynı kalan, uygulama açısından evrensel nokta olan; sabit verilerin, metotların ve sınıf düzeyindeki değişkenlerin(field) bulunabildiği bellek alanıdır.
* Bu alandaki yapılara ya da verilere ulaşabilmek için bir sınıf örneğine ihtiyaç duyulmaktadır, çünkü bu alanda tanımlanan yapılar static yani sabit olarak tanımlanmakta ve her yerden erişilebilir olarak tanımlanmaktadır.
* Dolayısıyla her yerden erişilebilir yapılar olacaklarından ve yerine göre değişen yapılar olmayacaklarından dolayı bu, static alandaki yapılara erişim için sınıf örneğine ihtiyaç duyulmamaktadır. (Değerin kendisi değil, erişimi tekildir)

> Ayrıca genel kültür olarak bilmenizde fayda var ki; RAM'de ki static alan esasında Heap içerisinde High Frequency Heap olarak bilinen özel bir alana karşılık gelmektedir.



### Neden Static Yapılanmayı Tercih Etmeliyiz?

> Static yapılanma, uygulama bazında tanımlanan yapılar olduğu için uygulama açısından veri paylaşımını kolaylaştırabilmektedir.

* Misal olarak; uygulamanın herhangi bir noktasında yapılandırma ayarlarına ihtiyacımız olabilir. Bu ayarları static yapıp, uygulama bazında tek seferde tanımlayabilirsiniz.
  Ya da benzer mantıkla uygulamanın state(durum) bilgisini tutmanız gerekebilir. Bunun için de yine static bellekten istifade edebilirsiniz.

Yani anlayacağınız, uygulamanın herhangi bir noktasında değişmeyecek bir şekilde kullanılacak olan verileri bizler static bellekte tutmayı tercih edebiliyoruz.

Bu bizlere bellek optimizasyonu ve yönetimi açısından oldukça avantaj sağlayabilmektedir.

Düşürseniz, uygulama için her yerde aynı olan yapılandırma ya da state değerlerini Heap'te bir instance olarak tutmak lüzumsuz bir maliyet olacaktır.

Tüm bunların dışında static yapılanmalara, sınıf örneğine ihtiyaç kalmaksızın doğrudan erişilebileceğinden dolayı Global Erişim süreçlerinde static yapılanmalar tercih edilebilmektedir.

Ayrıca bu sınıf örneğine ihtiyaç duyulmadığından dolayı nesne bağımsızlığının söz konusu olduğu davranışları static yapılanmalarla gerçekleştirmek oldukça ideal olacaktır.

Static yapılar, uygulama seviyesinde verileri saklamak için kullanılmaktadırlar.



### Static Bellekte Neler, Nasıl Tanımlanır?

> Static bellekte, static field'lar, metotlar, property'ler, constant'lar ve static iç sınıflar(inner classes) tutulabilmektedir.
>
> static keywordü access modifier (erişim belirleyici) öncesinde veya sonrasında bildirilmelidir.



#### Static Fields

> Bir field static olarak tanımlanabilmekte ve böylece uygulama seviyesinde merkezi olarak erişilip, kullanılabilmektedir.

Bir field'ı static belleğe koyabilmek için aşağıdaki gibi static keyword'ü ile işaretlenmesi gerekmektedir.

```csharp
static public int staticField;
```

Bu şekilde static keyword'ü ile işaretlenmiş olan field, compiler tarafından static bellek üzerinde tanımlanmış olacaktır.



#### Static Methods

> Metotlar da static olarak tanımlanarak, uygulama seviyesinde merkezi işlevler olarak erişilip, kullanılabilmektedir.

Metotları static belleğe koyabilmek için imzalarının aşağıdaki gibi static keyword'ü ile işaretlenmesi yeterlidir.

```csharp
static public int StaticMethod() {...}
```

Bu static keyword'ü ister access modifier'dan önce, isterse de sonra belirtilebilmektedir.



#### Static Properties

> Property'ler de aynı şekilde static bellekte tanımlanabiliyorlar.

Yapılması gereken ilgili property'nin imzasını tıpkı metotlarda olduğu gibi static keyword'ü ile işaretlemektir.

```csharp
public static int StaticProperty {get; set;}
```



#### Constants

> Constant'lar özünde static yapılanmalardır. Bundan temel programlama da bahsetmiştik Haliyle bir sınıf içerisinde tanımlanmış olan constant otomatik olarak static bellekte oluşturulur. Bundan dolayı constant tanımlarken static keywordü ile işaretlemek mecburiyetinde değiliz, zaten işaretleyemeyiz.

### Static Yapılanmalar Nasıl Kullanılır?

> Static bellekte tutulan yapılar, hangi sınıfta tanımlandılarsa, o sınıf adına karşılık tutulmaktadırlar.
> Bundan dolayı static bellekteki herhangi bir yapıya erişim göstermemiz gerekiyorsa eğer sınıf isimleri kullanılmaktadır.

```csharp
class MyClass
{
    static public int staticField;
    static public int StaticMethod() {...}
    static public int StaticProperty {get; set;}
    public const int constant = 0;
}
MyClass.staticField = 3;
MyClass.StaticMethod();
MyClass.StaticProperty = 123;
MyClass constant = 123;
```

> Görüldüğü üzere sınıf ismi üzerinden .(nokta) operatörü aracılığıyla, o sınıfta tanımlanmış olan tüm static yapılanmalara erişebilir ve istediğiniz gibi kullanabilirsiniz.



### Static Elemanların Genel Kuralları

* <u>Static Anahtar Kelimesi :</u>
  Bir yapıyı (field, metot, property veya class) static yapmak için 'static' keywordü ile işaretlemek gerekmektedir.
* <u>Genel Erişim :</u>
  Static yapılara sınıfların nesneleri üzerinden erişilemez! Doğrudan sınıfların adlarından erişim sağlanabilir.
* <u>Static Elemanlarda Static Olanlara Erişim :</u>
  Static yapılar içerisinde sade ve sadece static elemanlara erişim gösterebilir. Ama bu durumun tam tersi geçerli değildir, yani static olmayan bir eleman, static olan eleman(lar)a erişebilmektedir.
* <u>Static Class'lar :</u>
  Eğer ki bir class static keyword'ü ile işaretleniyorsa o class içerisindeki tüm member'lar static olmak zorundadır! Ayrıca o sınıfta constructor tanımlanamaz ve o sınıftan nesne oluşturulamaz!
* <u>Overload Edilebilir ve Override Edilemez :</u>
  Static metotlar overload edilebilir lakin override edilemez! virtual ile işaretlenemez!
* <u>Lifetime :</u>
  Static yapıların ömrü, uygulamanın ayakta kaldığı süre, yani uygulamanın ömrü kadardır.



### Static Sınıfların Kalıtımsal İlişkisi Nasıldır?

> Kalıtımsal ilişki, sınıfların instance'ları üzerinde davranış gerçekleştirdiği için Static Class'lar da inheritance davranışı mümkün değildir!



### Static Member'lar protected İle İşaretlenebilir mi?

> C# programlama dilinde, 'protected' ile işaretlenmiş hernhangi bir member'a, sade ve sadece o member'ın tanımlandığı class'tan türetilmiş olan alt sınıflardan erişim gösterilebilmektedir. Dolayısıyla 'protected' kalıtımsal ilişki gerektiren bir access modifier'dır.
>
> .Net'te miras olayları yalnız instance tabanında çalıştığından dolayı herhangi bir static member'ı protected ile işaretlemek bu açıdan manasız olacaktır. Amma velakin, normal sınıflarda tanımlanmış olan static member'ları protected olarak işaretlersek, bu durumda, o static member'lara, sadece ilgili sınıftan türeyen alt sınıflar üzerinden erişim gösterebileceğimiz lakin sınıf türleri üzerinden erişemeyeceğimiz anlamına gelmektedir..

```csharp
class MyClass
{
    protected static int MyProperty {get; set;}
}
class MyClass2 : MyClass
{
    public MyClass2()
    {
        MyProperty = 123;
    }
}
```

> Eğer ki bu static elemanı protected ile işaretlememiş olsaydık, buradaki kalıtımsal ilişki neticesinde MyProperty'e MyClass2'den erişebiliyor ve bir yandan da hem MyClass hem de MyClass2 türleri üzerinden de erişim gösterebiliyor olurduk. İşte, protected sayesinde static bir member'a sadece kalıtımsal durumdaki alt sınıf içerisinde erişim sınırı getirmiş oluyoruz.



### this Keyword'ünün Static Metotlarla İlişkisi

> Bir instance içerisinde, o instance'ı temsil eden this Keywordüne, static metotlardan erişilemez!



### Static Yapılar ile Nesneler Arasındaki Farklar Nelerdir?

Static yapılar ile nesneler arasında önemli farklar mevcuttur ve bu farklar C# ve diğer nesne yönelimli programlama dillerinde sıkça karşılaşılan kavramlardır.



#### İlk Oluşturma Zamanı

Static Yapılar : Sınıf uygulamada yüklendiği an ve ilgili sınıfları herhangi bir nesne oluşturulmadan önce oluşturulurlar.

Nesneler : Developer tarafından bir instance talebi geldiğinde oluşturulurlar.



#### Ömür

Static Yapılar : Uygulamaların yaşam ömrüyle doğru orantılıdır.
Uygulama başladığında oluşturulur ve sonlandırıldığında yok olurlar.

Nesneler : Oluşturulduktarı scope'la ya da kendilerini işaretleyen referansın varlığıyla sınırlıdırlar. Aksi taktirde bir müddet sonra imha edilirler.



#### Erişim

Static Yapılar : Tanımlandıkları sınıfın adından, uygulamanın herhangi bir noktasında erişim gösterebilir.

Nesneler : Sınıfın instance'ının oluşturulmasıyla ve referansını elde tuttukça erişilebilir.



#### Verisel Paylaşım

Static Yapılar : Sınıfın kendisi veri olarak değerlendirilir ve bu veriler uygulama çapında tekil olarak tutulmaktadır.

Nesneler : Her nesne kendi özel verisini tutmaktadır ve tanımlandıkları yahut referanslı oldukları faaliyet alanları çapında erişilebilir.



#### Faaliyet Alanı

Static Yapılar : Uygulama çapındadır.

Nesneler : Tanımlandıkları veya referans edilebildikleri metotlarla sınırlıdır.



### Static Constructor

Static constructor ile, ilgili sınıfta tanımlanmış olan bir static yapının ilk kullanılması ya da o sınıftan ilk nesne oluşturulması sürecinde bir kereye mahsus tetiklenmesiyle belli işlemler gerçekleştirebilmekteyiz.

Static constructor, yapısal olarak otomatik çalıştırıldıklarından dolayı developer tarafından doğrudan çağırılıp, çalıştırılamaz.

Tanımlandıkları sınıftan nesne oluşturma ya da o sınıftaki herhangi bir static yapıyı tetikleme sürecinde bir kereye mahsus çalışacağı için parametrik bir yapılanma da değildir!

Ve genellikle static constructor, sınıf içerisinde tanımlanmış olan static elemanların başlangıç değerlerini atayabilmek ve bunu bir kereye mahsus yapabilmek için kullanılmaktadır.



### Static Local Functions

C# 7.0 ile gelen Local Function özelliği C# 8.0 ile static özellik kazanmış vaziyettedir.

Bizler bir metodun içerisinde Non Static Local Function tanımlayabildiğimiz gibi Static Local Function'da tanımlayabilmekte ve işlemlerimizi yürütebilmekteyiz.

```csharp
MyClass m = new();
m.X();

class MyClass
{
    static int a = 3;
    public void X(int b = 5)
    {
        int c = 7;
        Y();
        Z(b, c);
        void Y()
        {
            Console.WriteLine($"a : {a} | b : {b} | c : {c}");
        }
        static void Z(int b, int c)
        {
            Console.WriteLine($"a : {a} | b : {b} | c : {c}");
        }
    }
}
```

> Static Local Function'larda yerel değişkenlere erişim engellenmiştir. Lakin static yapılara erişim direkt sağlanabilmektedir. Haliyle yerel değişkenlerin değerlerini parametreler aracılığıyla Static Local Function içerisine aktarabilmekteyiz.
