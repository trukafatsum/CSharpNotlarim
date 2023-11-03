# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)



[TOC]

------



## Giriş

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/00-QR.png alt="İlgili ders içeriği" width=10% align=left />

Günümüzde nesne tabanlı programlama birçok modern dil tarafından desteklenir haldedir.

Nesne tabanlı programlama;

> Yazılım geliştirme süreçlerini oldukça kısaltan ve sistematik hale getiren bir tekniktir, bir yaklaşımdır.

> Gerçek hayatı, programlama için simüle eden nesneleri baz alan bir programlama tekniğidir.
>
> Herşey bir nesnedir,
>
> • Sen		• Ben		• Personel
>
> • Ürün		• Satış		• Araba    gibi...
>
> Gerçek bir sistem, nesnel parçalara ayrılır ve bu parçalar (nesneler) arasında ilişkiler kurulur.
>
> Nesneler kendi aralarında haberleşebilirler.
>
> 

### Nesnenin Anatomisi

![https://i.imgur.com/VnMFdf0.png](https://i.imgur.com/VnMFdf0.png)

### Nesne Kavramı

Nesne, nesnellik felsefesine dayanan bir kavramdır. Kainattaki her bir şeyi 
nesne olarak görmek ve o şekilde yorumlamak fikrine dayanır.

Nesne, gerçek hayatta elle tutulur, gözle görülür objelerdir.Dolayısıyla 
programlamada da nesnelerimiz günlük hayattaki nesnelerin muadilidir. 

Gerçek hayattaki herhangi bir olguyu, nesneyi, objeyi, programlama dünyasında 
tarif ederkende onu bir nesne olarak tarif edecek ve o şekilde modelleyeceğiz.



### Nesne Modellemesi

Nesnelerin oluşturulabilmesi için modellenmesi gerekmektedir.

Nesne modeli class ile gerçekleştirilir.

<img src="https://i.imgur.com/hvbZdvb.png" alt="class-car" align="left"/>

Nesne Modeli

	Oluşturulan bu Car modeli sayesinde ;
	bizler istediğimiz araba verilerini 
	taşıyan nesneler üretebiliriz...



<img src="https://i.imgur.com/Vx8GHwg.png" alt="modelden-üretilen-nesneler" align="left"/>

Nesne modellemesinden üretilen nesneler


### Nesneler Hangi Türdendir?

Nesneler referans türlü değerlerdir..

#### Referans Türlü Değerler

<img src="https://i.imgur.com/CqzDHpD.png" alt="referans" align="left"/>



------



## Class Kavramı

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/01-QR.png alt="İlgili ders içeriği" width=10% align=left />

#### Sınıf Nedir? Neden Sınıf  Yapısı Kullanılır?

Sınıf nesne modelidir.

OOP'de bir object oluşturabilmek için öncelikle o objectin modellenmesi tanımlanması gerekmektedir.

Bir objenin modelini/tanımını oluşturabilmek için class yapısı kullanılır.



#### Sınıf ile Nesne Arasındaki İlişki Nedir?

Sınıf ile nesne arasındaki ilişki, sınıflarda nesnelerdeki ortak alan tanımları yapılır.

Sadece bir modele karşı bir sınıf tanımlarız ve nesneler sınıftan çoğul olarak türer, bire çok bir ilişki vardır.



#### Sınıf Nasıl ve Nerede Oluşturulur?

Bir sınıf oluşturmak istiyorsak şu şekilde oluştururuz:

```csharp
/*Prototip 
class Isim
{
    
}
*/
// class'lar bir referans türüdür.
```



Sınıflar 3 farklı yerde oluşturulabilir;

* Namespace İçerisinde
* Namespace Dışarısında
* Class İçerisinde (Nested Type)

```csharp
namespace oop_sinif
{
    class MyClass1 //Namespace İçerisinde
    {
        
    }
    class MyClass3
    {
        class MyClass4 // Class İçerisinde (Nested Type)
        {
            
        }
    }
}
class MyClass2 //Namespace Dışarısında, diğer tüm sınıflardan erişilebilir.
```

Bir class tanımlamasında tanımlanan yerde (namespace/dışı, class) aynı isimde birden fazla class tanımlanamaz.



#### Sınıf ile Nesne Modeli Tasarlama

```csharp
class Program
{
    OrnekModel model = new OrnekModel; // Referans noktası OrnekModel model; Referans alarak nesne oluşturma OrnekModel model = new OrnekModel;
    static void Main (string[] args)
    {
        Console.WriteLine(model.Y(5,10));
        Console.WriteLine(model.Y(20,2));
    }
}
public class OrnekModel
{
    //Fields
    int a;
    int b;
    //Functions
    public void X()
    {
        Console.WriteLine(a + " " + b);
    }
    public int Y()
    {
        return a * b;
    }
}
```



#### Sınıf Modelinden Referans Noktası Oluşturma

Bir class tanımlandığında o class adı bir türdür. Haliyle o türü kullanabilmek için direkt olarak class adını kullanmamız yeterlidir.

Eğer ki bir referans noktasında herhangi bir nesne referans edilmiyorsa, o referans noktasi/referans null değere sahiptir.

**Referans türlü değişkenler özünde nullable değişkenlerdir.**



------



### Class Members

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/02-QR.png alt="İlgili ders içeriği" width=10% align=left />

#### Field Nedir?

Nesne içerisinde veri depoladığımız/tuttuğumuz alanlardır.

Class içerisindeki değişkenlerdir.

> Field sadece class'ın scope'nda tanımlanmış olan değişkenlerdir. Metotta tanımlanmış değişken field değildir!

```csharp
class MyClass
{
    //Fields
    string ad,soyad,meslek;
    int yas;
}
```

Herhangi bir türden olabilir.

> Field'lar türüne özgü varsayılan değer alırlar.



#### Property Nedir?

Nesne içerisinde özellik/property sağlar.

Property esasında, özünde bir metottur. Yani programatik/algoritmik kodlarımızı inşa ettiğimiz bir metot.

Lakin fiziksel olarak metottan farkı parametre almamakta ve içerisinde get ve set olmak üzere iki adet blok almaktadır.

```csharp
class PropertyNedir
{
    public int X //Property
    {
        get
        {
            return 0;
        }
        set
        {
            //Atanan veri buradan yakalanır.
        }
    }
    public int X() //Metot!
    {
        return 0;
    }
}
```

> Metotta parantez vardır, propertyde parantez yoktur!

Property'e bir değer atamak istediğimizde set bloğunu kullanırız.

Değeri okunmak/çağırılmak istediğinde ise get bloğunu tetiklenir ve return eder.

>  Property'nin işlevsel açıdan metottan farkı yoktur, lakin davranışsal olarak nesne üzerinde bir değer okuma ve değer atama işlemlerinde kullanılır.

Bu bloklar compile neticesinde get ve set isimli metotlar olarak karşımıza çıkmaktadır.

---

Biz yazılımcılar nesnelerimiz içerisindeki field'lara direkt erişilmesini istemeyiz.

Dolayısıyla feild'lardaki verileri kontrollü bir şekilde dışarıya açmak isteriz.

İşte böyle bir durumda metotları kullanabiliriz.

> Böyle bir durumda C# programlama dilinde metot yerine property yapıları geliştirilmiştir.

Yani property yapıları özünde nesne içerisindeki bir field'ın dışarıya kontrollü açılmasını ve kontrollü bir şekilde dışarıdan değer alınmasını sağlayan yapılardır.

İşte biz property'lerin bu işlevine Encapsulation (Kapsülleme/Sarmalama) diyeceğiz..



#### Encapsulation (Kapsülleme/Sarmalama) Nedir?

Encapsulation, bir nesne içerisindeki dataların(field'lardaki verilerin) dışarıya kontrollü bir şekilde açılması ve kontrollü bir şekilde veri almasıdır.

İşte bu şekilde field'lardaki verilern erişim kontrolünü yapmamız için geliştirilmiş olan yapılara Property denmektedir.



#### Property İmzaları

Property yapısı oluşturabilmenin yapısal olarak birkaç farklı yolu/farklı imzası vardır.

* Full Property
* Prop
* Auto Property Initializers (C# 6.0)
* Ref Readonly Returns
* Computed (Hesaplanmış) Properties
* Expression-Bodied Property
  * Read Only Property
* Init-Only Properties & Init Accessor (C# 9.0)



##### Property İmzaları - Full Property

En sade property yapılanmasıdır.

İçerisinde get ve set blokları tanımlanmalıdır.

```csharp
//[erişim belirleyicisi][değişken türü][property adi]
public int Sayi
{
    get { } //--> Property'den veri istendiğinde tetiklenir.
    set { } //--> Property'e veri gönderildiğinde tetiklenir. Gönderilen veriyi value keywordüyle yakalar.
}
```

> Full propertylerde set bloğu tanımlanmazsa sadece okunabilir (read only), get bloğu tanımlanmazsa da sadece yazılabilir (write only) olacaktır.

```csharp
class MyClass
{
    int yasi;
    string adi;
    
    public int Yasi
    {
        get
        {
            // Property üzerinden değer talep edildiğinde bu blok tetiklenir. Yani değer buradan gönderilir.
            return yasi;
        }
        set
        {
            yasi = value;
        }
    }
}
```

> Kontrollü dememizin sebebine gelecek olursak aşağıdaki örnek üzerinden inceleyelim.

```csharp
class Banka
{
    int bakiye;
    public int Bakiye
    {
        get
        {
            if (bakiye > 0)
                return bakiye * 10/100; //bakiyenin %10'unu döndürür
            return 5;
        }
        set
        {
            if (value < 10)
                bakiye = value; //bakiyeye atanacak değer 10'dan küçükse değeri direk atar.
            else
                bakiye = value * 95/100; //Atanacak değerden %5 kesinti yaparak değer atar.
        }
    }
}
```



##### Property İmzaları - Prop Property

Bir property her ne kadar encapsulation yapsa da temsil ettiği field'daki dataya hiç müdahale etmeden erişilmesini ve veri atanmasını sağlıyorsa böyle bir durumda kullanılan property imzasıdır.

> Prop property'ler compile edildiklerinde arkaplanda kendi field'larını oluştururlar. Dolayısıyla bir field tanımlamaya gerek yoktur!

```csharp
// PROP property
// [erişim belirleyicisi][değişken türü][property adi]{ get; set; }
```

Prop imzalarda ilgili property read only olabilir lakin write only olamaz!



##### Property İmzaları - Auto Property Initializers (C# 6.0)

Bir property'nin ilk değerini nesne ayağa kaldırılır kaldırılmaz aşağıdaki gibi verebiliriz.

```csharp
class InsanEntity
{
    public string Adi {get; set;} = "Mustafa";
    public string Soyadi {get; set;} = "Kurt";
    public string Yasi {get; set;} = 26;
}
```

> Auto property initializers özelliği sayesinde read only olan prop'lara hızlıca değer atanabilmektedir.



##### Property İmzaları - Ref Readonly Returns (C# 7.2)

ref readyonly returns, bir sınıf (class) içerisindeki field'ı referansıyla döndürmemizi sağlayan ve bir yandan bu değişkenin değerini read only yapan özelliktir.

```csharp
class MyClass
{
    string adi = "Mustafa Kurt";
    public ref readonly string Adi => ref adi;
}
```



##### Property İmzaları - Computed(Hesaplanmış) Property

İçerisinde türetilmiş bir bağlantı taşıyan property'lerdir.

```csharp
int s1 = 5;
int s2 = 10;
public int Topla
{
    get
    {
        return s1 + s2;
    }
}
```



##### Property İmzaları - Expression-Bodied Property

Tanımlanan property'de Lambda Expression kullanmamızı sağlayan söz dizimidir.

```csharp
public string Cinsiyet => "Erkek";
```

> Bu şekilde expression-bodied ile imzalanan propertyler read only olarak oluşturulacaktır.



##### Property İmzaları - Init-Only Properties - Init Accessor (C# 9.0)

Init-Only Properties, nesnenin sadece ilk yaratılış anında propertylerine değer atamaktadır.

Böylece iş kuralı gereği runtime'da değeri değişmemesi gereken nesneler için bir önlem alınmaktadır.

> Init-Only Properties, developer açısından süreç esnasında değiştirilmemesi gereken property değerlerinin "yanlışlıkla" değiştirilmesinin önüne geçmekte ve böylece olası hata ve bug'lardan yazılımı arındırmaktadır.



#### Metod Nedir?

Nesne üzerinde, field'larda ki yahut dışarıdan parametreler eşliğinde gelen değerler üzerinde işlemler yapmamızı sağlayan temel programatik parçalardır.



#### Indexer Nedir?

Nesneye indexer özelliği kazandıran, fıtrat olarak property ile birebir aynı olan elemanlardır.

```csharp
// [erişim belirleyici][değişken türü]this[parametreler]
{
    get {}
    set {}
}
```



------



### Class Yapısına Dair Son Dokunuşlar

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/03-QR.png alt="İlgili ders içeriği" width=10% align=left />

#### Class İçerisinde Tanımlanan Class Sınıf Elemanı mıdır?

Sınıf elemanları;

* Feild
* Property
* Metot
* Indexer

> Nested-Type olan sınıflar bir sınıf elemanı değildir!



#### Class Elemanlarına Açıklama Satırı Nasıl Eklenir?

```csharp
//Sınıfımıza veya sınıfın altındaki herhangi bir member'a açıklama eklemek için kullanılır.

/// <summary>
/// Bu bir örnek classtır.
/// </summary>
class Ornek
{
    /// <summary>
    /// Bu bir field'tir.
    /// </summary>
    int sayi;
    
    /// <summary>
    /// Bu bir property'dir.
    /// </summary>
    public string Metin {get; set;}
    
    /// <summary>
    /// Bu bir metottur.
    /// </summary>
    public void Topla ()
    {
        sayi += 10;
    }
    
    /// <summary>
    /// Bu bir örnek metot overloadıdır.
    /// </summary>
    /// <param name="a">a parametresi..</param>
    public void Topla (int a)
    {
        sayi += a;
    }
    
    /// <summary>
    /// Bu bir Indexerdır.
    /// </summary>
    public int this[int a]
    {
        get {return 0;}
    }
}
```



------



## this Keyword'ü

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/04-QR.png alt="İlgili ders içeriği" width=10% align=left />

1. ### Sınıfın Nesnesini Temsil Eder

```csharp
MyClass m1 = new MyClass();
MyClass m2 = new MyClass();

// m1.X  --> m1 nesnesi üzerindeki X'i temsil eder
// m2.X  --> m2 nesnesi üzerindeki X'i temsil eder

class MyClass
{
    public void X()
    {
        //this
    }
}
```



2. ### Aynı İsimde Field ile Metot Parametrelerini Ayırmak İçin Kullanılır

```csharp
class MyClass
{
    int a;
    public void X(int a)
    {
        //a dediğimiz zaman parametreye erişir
        //this.a dedğimiz zaman o anki nesnenin üzerindeki field'ı temsil edecektir.
    }
}
```



3. ### Bir Constructer'dan Başka Bir Constructer'ı Çağırmak İçin Kullanılır

Constructer konusuna geldiğimiz zaman inceleyeceğiz.



------



## Nesne Kavramı

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/05-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Nesne Nedir?

Nesneler içerisinde bir veya birden fazla, anlamlı değerleri barındıran (complex) değerlerdir.

Nesneleri modellememizi sağlayan class'lar ise Complex Type'lardır.



### Bir Sınıftan Nesne Üretme/Türetme/Oluşturma

```csharp
class MyClass
{
    public int A {get; set;}
    public void X()
    {
        
    }
}
```

C#'ta nesne üretimi için new operatörü kullanılmaktadır.

```csharp
// new Type();
// Type --> Nesnesini talep ettiğimiz sınıf
// ()   --> Constructor metot
```

```csharp
class Program
{
    new Entity1();
}
class Entity1
{
    
}
```



### Target-Type New Expression (C# 9.0)

Nesne oluşum sürecinde, oluşturulacak olan nesne eğer ki direkt bir referansa atılıyorsa, burada hangi nesnenin oluşturulduğu referans sayesinde bilinebilmektedir.

Dolayısıyla ilgili nesnenin oluşturulması için

```csharp
// Type x = new Type()
```

semantiğinden ziyade

```csharp
// Type x = new()
```

şeklinde de oluşturmamızı sağlayan bir özelliktir.



------



### Referans Nesne İlişkisi

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/06-QR.png alt="İlgili ders içeriği" width=10% align=left />

#### Referans Nedir?

Ram'in Stack bölgesinde tanımlanan ve Heap bölgesindeki nesneleri işaretleyen/referans eden değişkenlerdir/noktalardır.

<img src= https://i.imgur.com/oGAa5ew.png width=700 align=left>

Referanslar illa bir nesne referans etmek zorunda değildirler.

> Eğer ki referans herhangi bir nesne işaretlemiyorsa null değerini alır.



#### Stack - Heap İlişkisi

<img src=https://i.imgur.com/nrJsDzC.png width=700 align=left>

```csharp
// MyClass m : MyClass türünde m isminde bir referans noktası oluşturur.
// '='operatörü : Assign operatörü olarak bildiğimiz bu operatör, referans türlü değişkenlerde referans/refere etme operatörü olarak işlev gösterir.
// new MyClass() : Heap üzerinde bir nesne oluşturur.
```

* Nesneler neden referansla işaretleniyor? Neden referans kullanıyoruz?

  * Bunun sebebi, nesnelerin referans türlü olmasıdır. Referans türlü değer/değişkenler Heap üzerinde oluşturulmakta olup, buna doğrudan erişim olmamasından dolayı referansla işaretleyip, dolaylı yoldan erişim sağlayabilmekteyiz.

* Referans üzerinden nesneye nasıl erişilir? Nesne üzerindeki elemanlara nasıl erişilir?

  * Öncelikle referans noktası oluşturulur ve referans etme operatörü '=' ile nesne çağırılır.

    ```csharp
    //Örnek
    MyClass m = new MyClass();
    ```

    Nesne oluşturulduktan sonra bu nesneye 'm' üzerinden erişim sağlayabilmekteyiz.

    ```csharp
    //Nesne üzerindeki elemanlara erişebilmek için '.' yani access member operatörünü kullanmaktayız.
    MyClass m = new MyClass();
    //Nesnemizin içerisinde public/erişilebilir Topla metodu olduğunu varsayarsak şu şekilde kullanım sağlayabilmekteyiz.
    m.Topla();
    ```

* Null olan (yani nesnesi olmayan) referanslar üzerinden herhangi bir member'i çağırıp işlemeye çalıştığımızda bu durumda NullReference hatası almaktayız.

  ```csharp
  //NullReference Hatası için örnek
  MyClass m2 = null;
  m2.Topla();
  ```



#### Referanssız Nesneler

<img src=https://i.imgur.com/TJ3kbhF.png width=700, align=left>

Bir nesne oluşturulduğu an herhangi bir referansla işaretlenmezse eğer Heap'e yerleştirilir.

```csharp
//Referanssız nesne oluşturabilmekteyiz, lakin bu nesne sistemde/memory de lüzumsuz yer kaplayacağından dolayı belirsiz bir süre sonra Garbage Collecter dediğimiz çöp toplayıcısı tarafından temizlenecektir.

//GC; heap'de referanssız olan nesneleri imha etmekten/temizlemekten sorumlu bir yapılanmadır.
```

Lakin bu nesneye tarafımızca bir daha erişemeyiz. Haliyle ilgili nesneyle aramızdaki tek diyalog oluşturma anıdır.

```csharp
new MyClass().MyProperty = 10; // Sadece oluşturma anında erişebilmekteyiz.
```



#### Referans Türüne Göre Nesne Elemanlarına Erişim

Her bir referans bir nesneyi temsil edebilecek yapıya sahiptir.

<img src=https://i.imgur.com/uPNFlr4.png width=700, align=left />

İleride Polimorfizm ve Abstraction konularında daha detaylı ele alacağız.



#### Object Initializer İle Nesne Oluşturma Esnasında Propertylere İlk Değer Atama

Bir sınıftan nesne oluştururken ilgili sınıfın elemanlarına şu şekilde değer atayabilmekteyiz.

```csharp
MyClass m = new MyClass();
m.MyProperty = 10;
```

Birde **object initializer** ile şu şekilde değer atayabilmekteyiz.

```csharp
//Object Initializer Semantiği
MyClass m = new MyClass()
{
  MyProperty = 10,
  MyProperty2 = 30,
  MyProperty3 = 40 //Nesnenin default değeri olarak düşünebilirsiniz.
      
  //Metot işlevsel bir yapı olduğu için değer atama işlemi yapılmaz. Dolayısıyla Object Init ile sadece field ve propertylere erişim sağlayabilmekteyiz.
};
```



------



### Nesne Kopyalama Davranışları | Shallow Copy | Deep Copy

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/07-QR.png alt="İlgili ders içeriği" width=10% align=left />

#### Nesne&Değer Kopyalamadan Kastedilen Nedir?

Temel progralmamada görmüş olduğumuz değer türlü değişkenleri ele alarak başlayalım.

```csharp
int a = 5; // int türünde a değişkeni oluşturulur ve 5 değeri atanır.
int b = a; // int türünde b değişkeni oluşturulur ve *a'nın değeri* atanır.
a = 10; // a değişkenine 10 değeri atanır.
```

Burada yapmış olduğumuz davranışı incelediğimizde sonuç olarak a değişkeni 10, b değişkeni 5 olacaktır.

a veya b üzerinde yapmış olduğumuz herhangi bir operasyonel işlem, birbirini etkilemeyecektir.

> Değer türlü değişkenlerde default olarak Deep Copy uygulanır.



#### Nesne&Değer Kopyalama Özünde İki Davranış Üzerinden Seyreder

##### 1)Shallow Copy

* Var olan bir nesnenin, değerin, referansının kopyalanmasıdır.

  Shallow copy neticesinde eldeki değer çoğaltılmaz. Sadece birden fazla referansla işaretlenmiş olur.

<img src=https://i.imgur.com/maobWLA.png width=700, align=left />

<img src=https://i.imgur.com/KbXgze9.png width=700, align=left />

<img src=https://i.imgur.com/tKvxsbs.png width=700, align=left />

> Referans türlü değişkenlerde default olarak Shallow Copy uygulanır.



##### 2)Deep Copy

* Var olan bir nesne, deep copy ile kopyalanıyorsa eğer ilgili nesne miktarı çoğalır. 

  Aynı özelliklere ve değerlere sahip olan bellekte farklı bir nesne daha oluşur.

**Klonlama işlemini manuel, kendi imkanlarımızla nasıl yapabiliriz?**

```csharp
class Program
{
    static void Main(string[]args)
    {
        MyClass m1 = new MyClass();
        MyClass m2 = m1; // Shallow Copy
        MyClass m3 = m1.Clone(); // Deep Copy
    }
}
class MyClass
{
    public MyClass Clone()
    {
        return (MyClass)this.MemberwiseClone();
        // MemberwiseClone bir sınıfın içerisinde o sınıftan üretilmiş olan o anki nesneyi klonlamamızı sağlayan bir fonksiyondur.
        // Object türünde geriye değer döndürdüğü için metodun geriye dönüş türüne cast etmemiz gerekir.
    }
}
```



------



## Encapsulation

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/08-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Encapsulation Nedir? Bir Veriyi Neden Kapsülleriz?

* Encapsulation, nesnelerimizde ki field'ların kontrollü bir şekilde dışarıya açılmasıdır.

* Bir başka deyişle, nesnelerimizi başkalarının yanlış kullanımlarından korumak için kontrolsüz değişime kapatmaktır.

<img src=https://i.imgur.com/i2BGM3V.png width=700, align=left />

<img src=https://i.imgur.com/R4frORb.png width=700, align=left />

> Field'larımıza direkt erişilmesini istemeyiz dolayısıyla encapsulation uygularız.



### Encapsulation Nasıl Uygulanır?

C#'da Encapsulation iki türlü uygulanmaktadır;

* Metot ile Encapsulation
* Property ile Encapsulation



### Eskiden Encapsulation'ı Nasıl Yapılıyordu?

C#'da property dediğimiz yapılanma gelmeden önce metotlar üzerinden encapsulation uygulanıyordu.

```csharp
class MyClass
{
    private int a;
    public int AGet ()
    {
        return this.a;
    }
    public void ASet (int value)
    {
        this.a = value;
    }
}
```



### Property ile Encapsulation

Class Members başlığı altında ele aldığımız üzere property yapılanması ile encapsulation işlemi gerçekleştirmiş oluyoruz.

Var olan bir field ile encapsulation gerçekleştirebilmek için full property kullanmamız gerekir.

```csharp
class MyClass
{
    private int a;
    public int A //Full Property
    {
        get { return a; }
        set { a = value; }
    }
}
```



------



## Record Nedir? OOP'de ki Yeri Neresidir? (C# 9.0)

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/09-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Record'ı Anlayabilmek İçin Ön Hazırlık (Init-Only Properties)

* C# 9.0'da, herhangi bir nesnenin propertylerine ilk değerlerinin verilmesi ve sonraki süreçte bu değerlerin

  değiştirilmemesini garanti altına almamızı sağlayan **Init - Only Properties** özelliği gelmiştir.

* Bu özellik sayesinde nesnenin sadece ilk yaratılış anında propertylerine değer atanmakta ve böylece iş kuralları

  gereği runtime'da değeri değişmemesi gereken nesneler için ideal bir önlem alınmaktadır.

  

Init-Only properties, developer açısından süreç esnasında değiştirilmemesi gereken property değerlerinin -yanlışlıkla- değiştirilmesinin önüne geçmekte ve böylece olası hata ve bug'lardan yazılımı arındırmaktadır.

<img src=https://i.imgur.com/cM80dHt.png width=75%, align= left />

<img src=https://i.imgur.com/wH2jjGI.png width=75%, align=left />

### Init-Only Properties

<img src=https://i.imgur.com/fMmrjDb.png width=75%, align=left />

<img src=https://i.imgur.com/fShhpuy.png width=75%, align=left />

## Records Nedir?

<img src= https://i.imgur.com/GDbIxze.png width=75%, align=left />

<img src=https://i.imgur.com/2yjONWF.png width=75%, align=left />

<img src=https://i.imgur.com/0JFbG9p.png width=75%, align=left />

### Record Tanımlama

<img src=https://i.imgur.com/Kx3zYdn.png width=75%, align=left />

### Record ile Class Arasındaki Fark

<img src=https://i.imgur.com/8ZGx9eg.png width=75%, align=left />

<img src=https://i.imgur.com/ouGDVlH.png width=75%, align=left />

### With Expressions

<img src=https://i.imgur.com/6blWyAn.png width=75%, align=left />

<img src=https://i.imgur.com/Ok29rFU.png width=75%, align=left />



------



## Constructor

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/10-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Constructor Metot Nedir?

Constructor bir nesne üretimi sürecinde ilk tetiklenen metottur.

```csharp
// new T (); () : Constructor
```

Parantez semantik açıdan metotlarda vardır. Bir metodu tetiklerken açmış olduğumuz parantez Constructor'dır.

Bir nesne üretilirken belirli konfigürasyonlarla nesnenin gelmesini istiyorsak, bu konfigürasyonları Constructor metod içerisinde tanımlarız.

Yani nesne üretim esnasında nesneye dair konfigürasyon yapmamızı sağlayan ve nesne üretilirken ilk tetiklenen fonksiyondur.

> Constructor, nesne oluşturma sürecinde tetiklenmek zorundadır!



### Constructor Davranış Modeli

<img src=https://i.imgur.com/pNw8A0p.png width=75%, align=left />

> Nesneye dair konfigürasyonları yapmayıp, başka işlemlerde yapabilmekteyiz.
> Sadece nesne içerisindeki field'lara property'lere değer atamakla yükümlü değildir.
>
> Ama genellikle nesneye dair konfigürasyonları yapmak için kullanırız.



### Constructor Metot Nasıl Oluşturulur?

* Constructor, özel bir sınıf elemanıdır.

  Özel olsada fıtrat olarak bir metottur.

  Lakin bildiğimiz metot imzalarından bir nebze farka sahiptir.

* Constructor'ların;

  * Metod adı sınıf adıyla aynı olmalıdır! (Özel sınıf elemanlarının dışında hiçbir member sınıf adıyla aynı olamaz!)
  * Geri dönüş değeri olmaz/belirtilmez!
  * Erişim belirleyicisi public olmalıdır! (private olduğu durum ayriyetten incelenecektir)

```csharp
class MyClass
{
    public MyClass() //Constructor : Geri dönüş değeri yok, sınıf ile aynı isimde
    {
        
    }
    public void X() //Metot : Geri dönüş değeri void, sınıf ile aynı isimde olsa dahi compiler hata verecektir.
    {
        
    }
}
```

> Normal bir member sınıf ismiyle aynı olamaz, oluyorsa da bu constructor metottur.

> Hatırlatma : C# 9.0'da gelen Target Type özelliğinde dahi biz construtor'ı tetiklemekteyiz.
>
> ```csharp
> class Program
> {
>  static void Main(string[]args)
>  {
>      MyClass m = new(); //C# 9.0 Target Type'da tetiklenen construtor örneği
>  }
> }
> class MyClass
> {
>  public MyClass()
>  {
>      Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur.");
>  }
> }
> ```
>
> 

### Default Constructor

Herhangi bir class'ı içi boş bir şekilde ele alalım;

```csharp
class MyClass
{
    // Bu sınıf içerisinde herhangi bir construtor tanımlanmamış olabilir.
}
```

```csharp
new MyClass(); // Lakin nesne üretirken de constructor tetiklenmektedir!
```

> Her sınıfın içerisinde tanımlamasak dahi default bir constructor mevcuttur.
>
> Çünkü her class'ın default bir constructor'ı mevcuttur.
>
> Eğer ki bir class'a constructor eklersek default constructor'ı ezmiş oluruz!



### Parametreli Constructor

Herhangi bir class'da constructor metot oluştururken bunu parametre alacak şekilde de oluşturabiliriz.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(5);
        new MyClass(10);
        
        MyClass m = new(15);
    }
}
class MyClass
{
    public MyClass(int a)
    {
        Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur." + a);
    }
}
```

> Constructor parametre alabildiğine göre overloading yapılabilir fonksiyonlardır.
>
> > Hatırlatma:
> >
> > Bir sınıf içerisinde aynı isimde birden fazla member tanımlayamayız. Lakin member'ların imzalarında farklılık olması durumunda çoklu yükleme (overloading) işlemi yapabilmekteyiz ve tanımlayabilmekteyiz.

```csharp
class MyClass
{
    public MyClass() //Overload
    {
        
    }
    public MyClass(int a) //Overload #1
    {
        Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur." + a);
    }
    public MyClass(string a) //Overload #2
    {
        Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur." + a);
    }
    public MyClass(string a, int b) //Overload #3
    {
        
    }
}
```



### Constructor'ın Erişim Belirleyicisini Private Yaparsak Sorunsalı?

> Constructor tanımlamadığımız durumda biz bir nesne oluştururken new MyClass(); olarak tanımlayabildiğimize göre,
>
> default constructor'ın erişim belirleyicisi de public durumdadır.
>
> Kendimiz bir constructor tanımlayarak bunun erişim belirleyicisini private yaparsak, ilgili sınıfın private yapılan constructor'ı dışarıdan erişilemeyeceğinden dolayı, haliyle bu sınıfa dair nesne üretiminde hata alacağız.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(); // Constructor'a erişilemeyeceği için nesne üretimi engellenir.
    }
}
class MyClass
{
    private MyClass() // Private
    {
        
    }
    void X()
    {
        new MyClass(); //-> Constructor içeriden erişilebilir bir yapıda olduğu için bu şekilde nesne üretimi gerçekleştirilebilmektedir.
    }
}
```

> [Singleton Design Pattern](https://metinalniacik.medium.com/singleton-design-pattern-tasar%C4%B1m-%C3%B6r%C3%BCnt%C3%BCs%C3%BC-b7221929dc26)'ı incelemeniz önerilir.



### this Keywordüyle Constructor'lar Arası Geçiş

> Hatırlatma:
>
> this Keyword'ü bir sınıfın içerisinde, o sınıfın o anki nesnesini temsil eder.
>
> Ayrıca this Keyword'ü bir sınıfın nesnesinin içerisinde tanımlanmış olan farklı constructor'lar arasında geçiş yapabilme sorumluluğunu da üstlenebilmektedir.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(5,10);
    }
}
class MyClass
{
    public MyClass()
    {
        Console.WriteLine("1. Constructor");
    }
    public MyClass(int a) : this() // Herhangi bir constructor'ın yanına this keyword'ünü getirdiğimiz durumda, o anki constructor'ın dışındaki diğer constructor'lara erişmemizi sağlayacaktır.
    {
        Console.WriteLine($"2. Constructor : a = {a}");
    }
    public MyClass(int a, int b) : this(a) //this(a) ile bir üstte tanımamış olduğumuz constructor'ı tetiklemiş oluyoruz.
    {
        Console.WriteLine($"3. Constructor : a = {a} | b = {b}");
    }
}
```

> this () 'dediğimizde erişebileceğimiz parametreler sadece tanımlanmış olan constructor'ların parametrelerindeki değerlere erişebilmektedir.
>
> Ayriyetten o parametre değeri dışında kendi vereceğimiz değerleri alabilmektedir.



### Record'larda Constructor

Record'lar özünde sınıf oldukları için class üzerinde anlatılmış olan kurallar record'larda da geçerli olacaktır.

* Parametre alabilecekler
* Overloading işlemlerine tabii tutulabilecekler
* this ile aynı şekilde yine temsil edilebilecek ve overloadlar arası geçiş yapabilecektir



------



## Desctructor/Finalizer Functions

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/11-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Desctructor/Finalizer Metot Nedir?

Bir class'tan üretilmiş olan nesne imha edilirken otomatik çağrılan metottur.

C# programlama dilinde Desctructor sadece class yapılanmasında kullanılabilir ve bir class sade ve sadece bir adet Destructor içerebilir.



Peki bir nesne hangi şartlarda kim tarafından imha edilir?

* Bir nesnenin imha edilmesi için;

  * İlgili nesne herhangi bir referans tarafından işaretlenmemelidir,
  * Yahut nesnenin oluşturulduğu ve kullanıldığı scope sona ermiş olmalıdır.
  * Yani anlaşılan ilgili nesneye bir daha erişilemez hale gelinmelidir.

  işte o zaman nesne imha edilir.

Peki kim tarafından?

### Garbage Collector

* Uygulamada lüzumsuz olan nesneleri toplamak için Garbage Collector isimli bir mekanizma devreye girer.

* Esasında Garbage Collector C#'da bellek optimizasyonunu üstlenen bir yapılanmadır.

* C#'da Garbage Collector'ın ne zaman iş göreceği tahmin edilemez. Kafasına göre takılır :)

* Dolayısıyla biz geliştiricilerin bu mekanizmaya müdahale etmesi pek önerilmez.



### Desctructor Tanımlama Kuralları

```csharp
class MyClass
{
    ~MyClass()
    {
        //..İşlemler..
    }
}
```

> ~MyClass() : Bir sınıf içerisinde sade ve sadece bir adet desctructor tanımlanabilir.
>
> ~ : Desctructor tanımlayabilmek için ~(tilde) işareti kullanılır.
>
> MyClass : Ve her özel sınıf elemanlarında olduğu gibi destructor'da sınıf ismiyle aynı isimde olan bir fonksiyondur.
>
> İşte bu fonksiyon, bu sınıftan üretilen nesne imha edilirken otomatik olarak son kez "selametle" demek için (yani son işlemleri yapabilmek için) tetiklenecek olan fonksiyondur.

```csharp
class MyClass
{
    public MyClass() // Constructor
    {
        Console.WriteLine("Selamın aleyküm..");
    }
    ~MyClass()   // Destructor
    {
        Console.WriteLine("Selametle..");
    }
}
```



### Garbage Collector Kullanımına Örnek

Her ne kadar manuel olarak çağırılması önerilmese de, destructor'ı gözlemleyebilmemiz açısından buradaki örnekler üzerinden inceleyelim.

#### Örnek 1 - Referanssız nesneler üzerinden garbage kullanımı

```csharp
class Program
{
    static void Main(string[]args)
    {
        int sayi = 100;
        while (sayi >= 1)
        {
            new MyClass(sayi--);
        }
        Console.WriteLine("*******************************");
        GC.Collect(); // Burada garbage collector'ı çağırarak o anki boşta olan tüm nesnelerin temizlenmesini sağlamaktayız.
        Console.ReadLine();
    }
}
class MyClass
{
    int no;
    public MyClass(int no) // Constructor
    {
        this.no = no;
        Console.WriteLine($"{no} numaralı nesne oluşturuldu.");
    }
    ~MyClass() // Destructor
    {
        Console.WriteLine($"{no} numaralı nesne destructorda tetiklendi ve silindi.");
    }
}
```

#### Örnek 2- Metot ile nesne oluşturulması, metodun sonlanması neticesinde garbage kullanımı.

```csharp
class Program
{
    static void Main(string[]args)
    {
        NesneOlustur();
        GC.Collect(); // Burada garbage collector'ı çağırarak o anki boşta olan tüm nesnelerin temizlenmesini sağlamaktayız.
        Console.ReadLine();
    }
    static void NesneOlustur() // Metot
    {
        MyClass m = new MyClass(); // MyClass sınıfından m referansı ile işaretlenmiş bir nesne üretilmesini sağlar.
    }
}
class MyClass
{
    public MyClass() // Constructor
    {
        Console.WriteLine("Nesne oluşturuldu.");
    }
    ~MyClass() // Destructor
    {
        Console.WriteLine("Nesne silindi. Son çalışan metot!")
    }
}
```



------



## Deconstruct Metodu

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/12-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Deconstruct Metodu Nedir?

* Bir sınıf içerisinde "Deconstruct" ismiyle tanımlanan metot, compiler tarafından özel olarak algılanmakta ve sınıfın nesnesi üzerinden geriye hızlıca Tuple bir değer döndürmemizi sağlamaktadır.

  > Tüm özel sınıfların isimleri sınıf ismiyle aynı olmak zorundaydı. Bunların arasında bir istisna var o da 'deconstruct'.
  > Deconstruct bir fonksiyondur. Sınıf ismiyle aynı ismi barındırmaz. İsmi Deconstruct olmalıdır!

### Prototip

```csharp
class MyClass
{
    public string x {get; set;}
    public string y { get; set;}
    public void Deconstruct(out string a, out string b)
    {
        a = x;
        b = y;
    }
}
```

> 1. Deconstruct fonksiyon tanımlamak için öncelikle public olması gerekmektedir.
>
> 2. Geriye değer döndürmemelidir.
> 3. Bu özel bir metottur ve özel olduğunu tanımlamak için 'Deconstruct' ismiyle tanımlanması gerekmektedir.
> 4. İmzasındaki değişkenler out olarak tanımlanması gerekmektedir.
>
> out olarak aldığı bu parametreleri Tuple olarak döndürecektir.
>
> Compiler bu metodun özel bir yapılanma olduğunu isminden algılayacaktır.



### Pratikte İnceleyelim

Person isminde bir sınıf oluşturalım ve Name (isim) ve Age (yaş) tutacak 2 property oluşturalım.

```csharp
class Program
{
    static void Main(string[]args)
    {
        Person person = new Person
        {
            Name = "Mustafa",
            Age = 25
        };
        var (x,y) = person; // Burada bizlere x ve y olarak Name ve Age değerlerini alır.
    }
}
class Person
{
    public string Name {get; set;}
    public int Age {get; set;}
    
    public void Deconstruct(out string name, out int age) // Deconstruct
    {
        name = Name;
        age = Age;
    }
}
```



------



## Static Constructor

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/13-QR.png alt="İlgili ders içeriği" width=10% align=left />

> Static yapılanmasını ilerleyen konularda inceleyeceğiz, lakin burada özel sınıf elemanları başlığı altında belirli kavramlardan bahsedeceğiz.

### Bir sınıftan nesne üretilirken ilk tetiklenen fonksiyon hangisidir?

MyClass isminde bir sınıfımız olsun ve new MyClass(); diyerek bu sınıftan bir nesne üretildiğini varsayalım.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass();
    }
}
class MyClass
{
    public MyClass() // Constructor : İlgili sınıftan nesne üretilirken ilk tetiklenen fonksiyondur.
    {
        
    }
    static MyClass() // Static Constructor : İlgili sınıftan ilk nesne üretilirken ilk tetiklenen fonksiyondur.
    {
        // Üretilen ilk nesne dışında bir daha tetiklenmez!
    }
}
```

Mülakattayız ve karşımızda bu şekilde bir kod ekranı mevcut ve bize ilk tetiklenen fonksiyon soruldu.

Bu durumda aklımıza direkt 'constructor' gelecektir. Halbu ki cevap Static Constructor olması gerekmektedir.

> Bir sınıftan nesne üretilirken ilk tetiklenen fonksiyon Static Constructor'dır...
>
> Amma velakin belirli bir duruma istinaden!!!

Eğer ki bir sınıftan **ilk kez bir nesne üretiliyorsa** burada **static constructor** devreye girecektir, ardından üretilen her nesnede constructor fonksiyonu ile devam edecektir.

> Ön bilgi:
>
> Statik yapılanmalar uygulama bazlı datalarımızı yerleştirdiğimiz alandır.
>
> Statik yapılanması nesnelerden bağımsızdır diyerek aklımızda tutalım.

* Static Constructor'da geri dönüş değeri ve erişim belirleyicisi bildirilmez!

* Bir sınıf içerisinde sade ve sadece bir tane tanımlanabilir. Yani parametre almaz!!
* Özel sınıf elemanı olduğu için ismi sınıf ismiyle aynı olmak zorundadır.



### Pratikte inceleyelim

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(); // Static constructor ve ardından constructor tetiklenir.
        new MyClass(); // Constructor tetiklenir.
    }
}
class MyClass
{
    public MyClass()
    {
        Console.WriteLine("MyClass constructor'ı tetiklenmiştir.");
    }
    static MyClass()
    {
        Console.WriteLine("MyClass static constructor'ı tetiklenmiştir.");
    }
}
```

> Not: 
>
> Static constructor'ın tetiklenebilmesi için illa ilk nesne üretimi yapılmasına gerek yoktur. İlgili sınıf içerisinde herhangi bir static yapılanmanın da tetiklenmesi, static constructor'ın tetiklenmesini sağlayacaktır.

#### Sigleton Design Pattern'da Static Constructor Kullanımına Örnek

```csharp
class Program
{
    static void Main(string[]args)
    {
        var database1 = Database.GetInstance;
        var database2 = Database.GetInstance; 
        var database3 = Database.GetInstance; //Her çağırdığımızda bize üretilen aynı nesneyi getirecektir.
        
        database1.ConnectionString = "assaffqwfwqfwfa";
    }
}
#region Singleton Design Pattern
    // Bir sınıftan uygulama bazında sade ve sadece tek bir nesne oluşturulmasını istiyorsan kullanabileceğin bir design pattern.
#endregion
class Database
{
    Database() // Private olacağı için dışarıdan nesne üretimini engellemiş olacağız.
    {
    }
    public string ConnectionString {get; set;}
    static Database database; // Field : İlgili sınıfın kendi referansında bir field oluşturuyoruz -> Statik bellekte duran bir referans
    public static Database GetInstance // Property : İlgili sınıftan getinstance isminde statik bir property oluşturuyoruz ve sadece get işlemini kullanıyoruz
    {
        get
        {
            return database;
        }
    }
    static Database()
    {
        database = new Database();
    }
}
```



------



## Positional Record

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/14-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Positional Record Nedir?

* Norminal Record'lar Object Initializer'lar ile ilk değerleri verilerek üretilebilen readonly datalardı.
* Positional Record'lar ise esasında Record'lar içerisinde tanımlama yapabildiğimiz constructor ve deconstructor kullanımlarını daha da özelleştirerek kullanılmasını sağlamaktadırlar.

```csharp
class Program
{
    static void Main(string[]args)
    {
        MyRecord m = new MyRecord("asfasfasf","oıwoqjwrıqw");
        var (n,s) = m;
    }
}
record MyRecord(string name, string surname)// Positional Record : Hem constructor hem deconstruct'a karşılık gelmektedir.
{
    
}
```

> Bu özellik record'a has bir özelliktir. Record yerine Class kullanmaya çalışırsak compiler hata verecektir.
>
> ```csharp
> class Program
> {
>  static void Main(string[]args)
>  {
>      MyRecord m = new MyRecord("asasfasf","qwerqwrqwr");
>      var (n,s) = m;
>  }
> }
> class MyRecord(string name, string surname)
> {
> 
> }
> ```

#### Prototip

```csharp
// record name(...,...) : Bu semantik C# 9.0 ile positional record'a gelmiştir.
```

* Bir record üzerinde constructor ve desconstruct yapılanmasını hızlı bir şekilde oluşturmamızı sağlayan bir semantik sağlamaktadır.
* Positional Record kullanılırken parametrelerin karşılıkları olan propertyleri manuel oluşturmak zorunda değiliz.
* Bu parametrelerin karşılığı olarak compiler seviyesinde propertyler otomatik oluşturulacaktır.
* Bu propertyler oluşturulurken **init** olacak şekilde oluşturulur.



### Positional Record Kullanırken Kendimiz Constructor Tanımlayabilir Miyiz?

* Positional Record tanımlanmışsa eğer nesne üretiminde tetiklenmesi / kullanılması zorunludur!!

```csharp
class Program
{
    static void Main(string[]args)
    {
        MyRecord m = new MyRecord();
        var (n,s) = m;
    }
}
record MyRecord(string name, string surname)
{
    public MyRecord() : this("asdf","qwerty") // Yeni bir constructor tanımlayabilmek için this ile positional record'un constructor'ına değer göndermek zorundayız.
    {
        
    }
}
```



### Positional Record Kullanırken Property Oluşturma

```csharp
record MyRecord(string name, string surname)
{
    public string Name => name;
    public string Surname => surname;
}
```



------



## Inheritance (Kalıtım) - Chapter 1

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/15-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Bir Programcı Açısından Kalıtım Nedir?

* Kalıtım OOP'nin en önemli özelliğidir.

* Üretilen nesneler farklı nesnelere özelliklerini aktarabilmekte ve böylece hiyerarşik bir düzenleme yapılabilmektedir.

* Bir programcı açısından bu özellik;

  * Aynı aile grubundan gelen nesnelerin ya da yatayda eşit seviyede olan tüm

    olguların benzer özelliklerini tekrar tekrar her birinde tanımlamaktansa bir

    üst sınıfta tanımlanması ve her bir sınıfın bu özellikleri üst sınıftan kalıtımsal olarak

    almasını sağlamaktadır.

  * Böylece hem kod maliyeti düşmekte, hem de mimarisel tasarım açısından avantaj sağlamaktadır.

<img src = https://i.imgur.com/i9OwyUd.png width=60%, align=left />



### Her Sınıfı Kalıtımsal Operasyona Tabi Tutmalı mıyım? Sorunsalı..

İhtiyaç doğrultusunda kullanılacak olan bir yapılanmadır. Dolayısıyla her sınıfta kalıtımsal operasyona tabi tutmamız gerekmemektedir.

* Olgusal olarak aynı kategoriye girebilecek nesnelerde, memberlarda bunları tekrar tekrar yazmak yerine bir üst sınıfta tanımlamamız gerekir.

#### Kalıtımın Kullanılmadığı Durum Örneği-1

```csharp
class Erkek
{
    //--Tekrar eden yapılanma
    public string Adi {get; set;}
    public string Soyadi {get; set;}
    public int Yasi {get; set;}
    //---- Erkeğe has özellikler
    public bool Sakal {get; set;}
    public bool Biyik {get; set;}
    public bool Tesbih {get; set;}
}
class Kadin
{
    //--Tekrar eden yapılanma
    public string Adi {get; set;}
    public string Soyadi {get; set;}
    public int Yasi {get; set;}
    //---- Kadına has özellikler
    public bool Makyaj {get; set;}
    public bool Ruj {get; set;}
    public bool Kupe {get; set;}
}
```

> Nesne tabanlı programlamada, benzer/aynı durumdaki nesnelerin aynı olan memberları/özellikleri/içerikleri 
>
> eğer ki bu şekilde her sınıf içinde tekrar tekrar tanımlanmışsa bu aykırı bir durumdur!
>
> Aynı olguda olan sınıfların tekrar eden memberları bir başka sınıfta toplansın ve oradan ilgili sınıflara kalıtımsal olarak aktarılsın...

```csharp
class Insan
{
    public string Adi {get; set;}
    public string Soyadi {get; set;}
    public int Yasi {get; set;}
}
class Erkek
{
    public bool Sakal {get; set;}
    public bool Biyik {get; set;}
    public bool Tesbih {get; set;}
}
class Kadin
{
    public bool Makyaj {get; set;}
    public bool Ruj {get; set;}
    public bool Kupe {get; set;}
}
// Erkek ve Kadin sınıfları Insan sınıfından kalıtım alırsa/türetilirse/miras alırsa, Insan sınıfındaki tüm memberlar(erişimine izin verilen/miras olarak aktarılmasına izin verilen memberlar) kalıtımsal olarak aktarılacaktır...
// Genellenemeyen, diğerlerinde olmayan ve sadece o sınıfa ait olan özellikler direkt ilgili sınıfta tanımlanmalıdır.
```



#### Kalıtımın Kullanılmadığı Durum Örneği-2

```csharp
class Opel
{
    public string Marka {get; set;}
    public string Model {get; set;}
    public int KM {get; set;}
}
class Mercedes
{   
    public string Marka {get; set;}
    public string Model {get; set;}
    public int KM {get; set;}
}
class Fiat
{
    public string Marka {get; set;}
    public string Model {get; set;}
    public int KM {get; set;}
}
```



##### Kalıtımın Kullanıldığı Durum (İdeal Durum)

<img src= https://i.imgur.com/XneTqmQ.png width=75%, align=left />

> Kalıtım lalettayin bir şekilde tasarlanmamalıdır. Ortak olguda olan nesneleri temsil edecek olan bir üst ve daha evrensel nitelikte olgu olmalıdır.
>
> Opel, Mercedes ve Fiat ortak olgudur. Yani üçüde bir arabadır. Haliyle bunların daha evrensel üst niteliği Araba olarak nitelendirilebilir.

> Kalıtım operasyonunda, kalıtım veren sınıfın erişilebilen tüm memberları kalıtım alan sınıfa kalıtsal olarak aktarılacaktır.



### Bir Programcı Açısından Kalıtım Nedir?

1. OOP'de kalıtım özünde nesnelerin birbirlerinden türemesini sağlayan bir özelliktir.

2. Bu özellik yanında da birçok özellik ve stratejik yapılanma getirmektedir. // virtual yapılanmalar, polimorfizm, abstraction,...
3. Bu eğitim sürecinde OOP'deki kalıtımı ve kalıtımın getirisi olan tüm stratejik yapılanmaları tam teferruatlı ele alacağız!



### C# Programlama Dilinde Hangi Yapılar Kalıtım Alabilirler?

* C# programlama dilinde kalıtım sınıflara özel bir niteliktir.

* Yani bir sınıf sade ve sadece bir sınıftan kalıtım alabilir.

  * Peki record'lara özünde sınıf demiştik, onlar kalıtım alabiliyor mu?
    Evet, record'lar da kalıtım alabilmekte, lakin sadece kendi aralarında. Kalıtım alabildikleri tek istisnai sınıf ise ileride göreceğimiz Object sınıfıdır.

* Object kalıtımda önemli bir rol oynayan özel bir sınıftır.

* Ayrıca sonraki derslerimizde göreceğimiz abstract class, interface ve struct gibi yapılarında kendilerine göre kalıtımsal operasyonları mevcuttur. Bu yapılardaki

  kalıtımsal detaylar ilgili derslerde ele alınacaktır.



### C#'ta Kalıtım Nasıl Alınır?

: Operatörü

* C#'ta iki sınıf arasında kalıtımsal ilişki kurabilmek için : operatörü kullanılmaktadır.
* Hatta bilsekte bilmesekte kalıtımsam tüm ilişkiler : operatörü tarafından yapılmaktadır.



#### Örnek

```csharp
class Araba
{
    public string Marka {get; set;}
    public string Model {get; set;}
    private int KM {get; set;}
}
class Opel:Araba //Soldaki, sağdakinden kalıtım alsın. Yani; Opel sınıfı, Araba sınıfından kalıtım alsın demiş oluyoruz.
{
    
}
```

* Kalıtım, operasyonel olarak gerçekleştirildikten sonra compiler seviyesinde member aktarımı sağlanır!
* Yani artık Opel sınıfından bir nesne ürettiğimizde içerisinde Marka ve Model propertyleri kalıtımsal olarak aktarıldığı için erişilebilir olacaktır.



### Pratik

```csharp
class Program
{
    static void Main(string[]args)
    {
        Muhasebeci muhasebeci = new Muhasebeci();
        Mudur mudur = new Mudur();
        Yazilimci yazilimci = new Yazilimci();
        muhasebeci.Musavir;
        mudur.Adi;
        yazilimci.KullandigiDiller;
    }
}
class Personel
{
    public string Adi {get; set;}
    public string Soyadi {get; set;}
    public bool MedeniHal {get; set;}
}
class Muhasebeci : Personel
{
    public bool Musavir {get; set;}
}
class Yazilimci : Personel
{
    public string[] KullandigiDiller {get; set;}
}
class Mudur : Personel
{
    
}
```



------



## Inheritance (Kalıtım) - Chapter 2

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/16-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Base Class ve Derived Class Nedir?

**Kalıtım veren** sınıfa **Base / Parent Class** denir.

**Kalıtım alan** sınıfa **Derived / Child Class** denir.

```csharp
class Araba // Base/Parent Class
{
    public string Marka {get; set;}
    public string Model {get; set;}
    public int KM {get; set;}
}
class Opel : Araba // Opel : Derived/Child Class
{
    
}
```

#### Kritik

```csharp
class A
{

}
// Base Class: A
// Derived Class: B
class B:A
{
    
}
// Base Class: B
// Derived Class: C
class C:B
{
    
}
// Base Class: C
// Derived Class: D
class D:C
{
    
}
```

> Peki, atalar tüm torunların Base Class'ı mıdır?
>
> Yani A, B'nin olduğu gibi bir yandan da C ve D'nin de Base Class'ı mıdır?
>
> Hayır!

> Unutma!
>
> Bir sınıfın sade ve sadece tek bir Base Class'ı olabilir!
>
> Yani bir sınıfın Base Class'ı direkt türediği sınıftır.
>
> Lakin atalarındaki tüm sınıflar Base Class'ı değildir!

> Örneğin; C'nin Base Class'ı B'dir. A ise atasıdır. Base Class'ı değildir.
>
> Peki, bir class'ın birden fazla Derived Class'ı olabilir mi?
>
> Evet olabilir.

#### Bir sınıfın birden fazla derived class'ı olmasına Örnek

```csharp
class A
{
    
}
class B:A
{
    
}
class C:A
{
    
}
class D:C
{
    
}
```

A : Hem B'nin hem de C'nin Base Class'ıdır.

B: A'nın Derived Class'ıdır.

C: Hem A'nın Derived Class'ı hem de D'nın Base Class'ıdır.

D: C'nin Derived Class'ıdır.

Yani bir sınıf hem base class hem de derived class olabilmektedir.



### Kalıtımın Altın Kuralı

* Bir class'ın sade ve sadece bir Base Class'ı olur dedik.
* Bunun nedeni, C# programlama dilinde bir class'ın sade ve sadece tek bir class'tan türetilmesine izin verilmektedir! Aynı anda birden fazla class'tan türeme işlemi gerçekleştirilemez!

```csharp
class Y: X,Z,W,...
{
    ...
}
```

> İleride bu şekilde birden fazla kalıtım tanımlamasının yapılabildiğini göreceksiniz..
>
> Lakin orada da göreceksiniz ki Z ve W bir sınıf olmayacaktır!
>
> (İpucu : Interface)



### Kalıtımda Nesne Üretim Sırası

* Bir sınıftan nesne üretimi yapılırken, kalıtım aldığı üst sınıflar varsa eğer önce o sınıflardan SIRAYLA nesne üretilir.

<img src=https://i.imgur.com/eOcKf9J.png width=75%, align=left />

#### İnceleyelim

```csharp
class Program
{
    static void Main(string[]args)
    {
        new D(); // D'den nesne ürettiğimiz taktirde tüm constructorlar tetiklenecektir. Böylece sadece D sınıfından değil, üst sınıflardan da nesne üretildiğini gözlemleyebileceğiz.
    }
}
class A
{
    public A()
    {
        Console.WriteLine($"{nameof(A)} sınıfından bir nesne üretildi!");
    }
}
class B : A
{
    public B()
    {
        Console.WriteLine($"{nameof(B)} sınıfından bir nesne üretildi!");
    }
}
class C : B
{
    public C()
    {
        Console.WriteLine($"{nameof(C)} sınıfından bir nesne üretildi!");
    }
}
class D : C
{
    public D()
    {
        Console.WriteLine($"{nameof(D)} sınıfından bir nesne üretildi!");
    }
}
```



### Bir Sınıftan Base Class Constructor'ına Ulaşım

* Madem ki, herhangi bir sınıftan nesne üretimi gerçekleştirilirken öncelikle base class'ından nesne üretiliyor, bu demektir ki önce base class'ın constructor'ı tetikleniyor.
* Haliyle bizler nesne üretimi esnasında base class'ta üretilecek olan nesnenin istedğimiz constructor'larını tetikleyebilmeli yahut varsa parametre bu değerleri verebilmeliyiz.
* İşte bunun için **base Keyword**'ü nü kullanmaktayız.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass2();
    }
}
class MyClass
{
    public MyClass()
    {
        
    }
    public MyClass(int a)
    {
        
    }
}
class MyClass2 : MyClass 
{
    public MyClass2() // Eğer ki bir base class'ta boş bir constructor varsa derived classta base ile ilgili bir bildirimde bulunmak zorunda değiliz.. Çünkü varsayılan olarak kalıtımsal durumda base classtaki parametreleri boş constructor tetiklenir..
    {
        
    }
    public MyClass2(int a) :base(a) // Eğer ki base class'ın constructor'ı sadece parametre alan constructor ise derived class'larda o constructor'a bir değer göndermek ZORUNDAYIZ! Bunu da base keywordüyle sağlayabiliriz..
    {
        
    }
}
```



### base Keyword vs this Keyword

* this, bir sınıftaki constructor'lar arasında geçiş yapmamızı sağlar.
* base, bir sınıfın base class'ının constructor'larından hangisinin tetikleneceğini belirlememizi ve varsa parametrelerinin değerlerinin derived class'tan verilmesini sağlar.

> Ayrıca nasıl ki this, ilgili sınıfta o anki nesnenin memberlarına erişebilmemizi sağlıyor, aynı şekilde base'de base class'da ki memberlara erişebilmemizi sağlamaktadır.



------



## Inheritance (Kalıtım) - Chapter 3

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/17-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Nesnelerdeki ToString, Equals, GetHashCode ve GetType Metotları Nereden Gelmektedir?

#### Nesnelerin Atası/Ademi Object Türü

* C# Programlama dilinde tüm sınıflar Object sınıfından türetilir.

  

  ```csharp
  class Canli
  {
      
  }
  ```

  

* Bir sınıf kalıtım alsa da almasa da, default olarak object sınıfından türetilecektir.

  ```csharp
  class Insan : Canli
  {
      
  }
  ```

* Yok eğer bu şekilde herhangi bir sınıftan kalıtım alıyorsa, bir sınıfın aynı anda birden fazla sınıftan 

  kalıtım almama prensibinden yola çıkarak bir yandan da Object sınıfından türemeyecek sadece kalıtım aldığı sınıftan türeyecektir.

* Tabi burada kalıtım veren sınıf herhangi bir sınıftan türemiyorsa eğer, en niyahetinde Object'ten

  türeyeceği için dolaylı yoldan insan sınıfı da Object'ten kalıtım almış olacaktır.



### Object Sınıfı Memberları & Yapısı

* Constructor
* Destructor
* Equals, ReferenceEquals, GetHashCode, GetType, ToString fonksiyonları

<img src=https://i.imgur.com/jYC8iFv.png width=75%, align=left />



### İsim Saklama(Name Hiding) Sorunsalı

* Kalıtım durumlarında atalardaki herhangi bir member ile aynı isimde member'a sahip olan nesneler olabilmektedir.

  ```csharp
  class A
  {
      public int X {get; set;}
  }
  class B : A
  {
      public int X {get; set;}
  }
  B b = new B();
  b.X; // Şimdi bu X A'dan mı geliyor yoksa B'den mi? B'den geliyor, A'daki X gizlenmiş oluyor, bu duruma 'Name Hiding' denmektedir.
  ```

  Çünkü şu tasarımda base class'taki/atalardaki X member'ına B üzerinden erişmek mümkün değildir! Yani base'deki üye gizlenmiştir.

  İhtiyaç yoktur lakin biz yine de Name Hiding durumlarında new operatörünün kullanımını inceleyelim.



### Name Hiding Durumlarında new Operatörünün Kullanımı

```csharp
class A
{
    public int X {get; set;}
}
class B : A
{
    public int X {get; set;}
}
```

> Yukarıda bir Name Hiding durumu söz konusudur. Günümüzde bu şekilde Name Hiding durumlarında ekstradan bir bildiride bulunmak zorunda değiliz.
>
> > Eskiden Name Hiding durumlarını derleyiciye bilinçli bir şekilde yapıyorum dememiz gerekiyordu.
> >
> > ```csharp
> > class A
> > {
> >  public int X{get; set;}
> > }
> > class B : A
> > {
> >  public new int X {get; set;}
> > }
> > ```
> >
> > Artık Name Hiding durumlarında bunu yapmak zorunda değiliz.



#### Örnek

```csharp
class Program
{
    static void Main(string[]args)
    {
        D d = new D();
        d.X();
    }
}
class A
{
    public void X()
    {
        
    }
}
class B : A
{
    
}
class C : B
{
    
}
class D : C
{
    public new void X()
    {
        
    }
}
// Atalarda aynı isimde herhangi bir member görüyorsak işte bu Name Hiding'dir.
```



### Record'larda Kalıtım

* Record'lar sade ve sadece Record'lardan kalıtım alabilmektedirler.
* Class'lardan kalıtım alamazlar yahut veremezler!
* Kalıtımın tüm temel kuralları record'lar için geçerlidir:
  * Bir record aynı anda birden fazla record'dan kalıtım alamaz!
  * Record'lar da temelde class oldukları için üretilir üretilmez otomatik Object'ten türerler.
  * base ve this keywordleri aynı amaçla kullanılabilmektedir.
  * Name Hiding söz konusu olabilmektedir.
  * Ve aklıma gelmeyen diğer tüm durumlar da record'lar için geçerlidir.



------



## Sanal Yapılar : Virtual & Override

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/18-QR.png alt="İlgili ders içeriği" width=10% align=left />

* Bir nesne üzerinde var olan tüm memberların tamamı derleme zamanında belirgindir.

* Yani, derleme aşamasında hangi nesne üzerinden hangi metotların çağrılabileceği bilinmektedir.

  ```csharp
  class MyClass
  {
      public int MyProperty {get; set;}
      public void MyMethod()
      {
          
      }
  }
  ```

  Compiler Time : "MyClass sınıfından üretilen tüm nesnelerde MyProperty ve MyMethod çağırılabilecektir."

  

* Sanal yapılar ile derleme zamaında kesin bilinen bu bilgi runtime (çalışma zamanın)da belirlenebilmektedir. Yani ilgili

  nesnenin hangi metodu kallanacağı bilgisi runtime da kararlaştırılır.



### Sanal Yapılar Nedir?

* Sanal yapılar, bir sınıf içerisinde bildirilmiş olan ve o sınıftan türeyen alt sınıflara da tekrar bildirilebilen yapılardır.

* Bu yapılar metot ya da property olabilir.

* Name Hiding ile bir sınıftaki herhangi bir member'ı ordan türeyen torunlarda oluşturabiliyoruz ve buradaki yaşanan çakışmaya da Name Hiding diyoruz.

  * Lakin sanal yapılarda olay bu şekilde değildir. Bir sınıfta bildirilen sanal yapı (metot ya da property) bu sınıftan türeyen torunlarında ezilebilmekte,

    yani devre dışı bırakılıp yeniden oluşturulabilmektedir.

  * Yani sanal yapılanmalarda Name Hiding'de olduğu gibi isimsel çakışmadan ziyade üstten gelen bir yapının işlevini iptal edip yeniden yapılandırmak vardır.

  * İşte burada bir sınıfta tasarlanmış sanal yapının işlevinin iptal edilip edilmeme durumuna göre tanımlandığı sınıftan mı yoksa bu sınıfın torunlarından mı çağırılacağının belirlenmesi runtime'da gerçekleşecektir.



### Sanal Yapıları Gözlemleyelim



### Sanal Yapılar Ne İçin Kullanılır?

Bir sınıfta tanımlanmış olan herhangi bir member'ın kendisinden türeyen alt sınıflarda Name Hiding durumuna düşmemeksizin ezilip/yeniden yazılıp yapılandırılması için kullanılır.

> Peki bu zorunlu mudur?
>
> Yani bir sanal yapı illa ki kendisinden türeyen torunlarda ezilmek/yeniden yazılmak zorunda mıdır?
>
> Tabi ki de hayır! Yani bir member sanal yapıldı diye illa ki kendisinden türeyen alt sınıflarda ezilmek zorunda değildir!
>
> Ama ezilmek istenirse de Name Hiding'e bulaşmadan direkt ilgili sınıfın bir member'ı olacak şekilde çalışılmasını sağlamış olur.



### Bir Sınıfta Sanal Yapı Nasıl Oluşturulur?

#### Virtual Keyword'ü

Bir sınıfta sanal yapı oluşturabilmek için ilgili member'ın (metot ya da property) imzasını virtual keywordü ile işaretlemek yeterlidir.

> Normal Metot:
>
> ```csharp
> class MyClass
> {
>  public void MyMethod()
>  {
> 
>  }
> }
> ```
>
> Sanal Metot:
>
> ```csharp
> class MyClass
> {
>  public virtual void MyMethod()
>  {
> 
>  }
> }
> ```



### Sanal Yapılar Nasıl Ezilir?

#### Override Keyword'ü

Bir class'ta virtual ile işaretlenerek sanal hale getirilmiş bir member (metot ya da property), bu class'tan miras alan torunlarında ezilmek/yeniden yazılmak isteniyorsa eğer ilgili class'ta imzası override keywordü işaretlenmiş bir vaziyette tekrardan aynı member oluşturulur.

```csharp
class MyClass
{
    public virtual void MyMethod()
    {
        
    }
}
class MyClass2 : MyClass
{
    public override void MyMethod()
    {
        
    }
}
// Aynı durum property'ler için de geçerlidir.
```

* Base class'ta ya da atalarda virtual ile işaretlenerek sanallaştırılmış herhangi bir member torunlarda illa ki override ile ezilmek zorunda değildir!

* Ama bir torun class, base class'taki herhangi bir member'ı override edecekse eğer, o member'ın kesinlikle virtual ile işaretlenmiş olması gerekmektedir.
* virtual ile işaretlenmemiş bir member kesinlikle override edilemez!

> Not : "override" keywordünü ileride Abstact Class'ların implemantasyounda da kullanacağız.



### Ara Örnek

```csharp
class Program
{
    static void Main(string[]args)
    {
        Terlik t = new Terlik();
        t.Bilgi(); //Obje'den türeyen Bilgi fonksiyonu, herhangi bir override işlemine tabii tutulmadığı için Ben bir objeyim... şeklinde çıktı verir.
        
        Kalem k = new Kalem();
        k.Bilgi(); //Obje'den türeyen Bilgi fonksiyonu sanal yapıda olduğu için, Kalem sınıfı içerisinde override edilmiştir ve "Ben bir kalemim... şeklinde çıktı verir."
    }
}
class Obje
{
    public virtual void Bilgi() // Sanal member
    {
        Console.WriteLine("Ben bir objeyim...");
    }
}
class Terlik : Obje
{
    
}
class Kalem : Obje
{
    public override void Bilgi() // Override edilmiş member
    {
        Console.WriteLine("Ben bir kalemim...")
    }
}
```



### İkiden Çok Hiyerarşik Kalıtım Durumlarında Override Durumu

Bir class'ta virtual ile işaretlenmiş herhangi bir member illa ki direkt o class'tan türeyen 1. dereceden class'larda override edilmek mecburiyetinde değildir!

İhtiyaca binaen alt seviyedeki torunlardan herhangi birinde override edilebilir.

> Lakin böyle bir durumda **kritik** bir durum vardır! O da ilgili soyut member'ın en son override edildiği Object'ten sonra geçerli olduğudur.
>
> Ve o object'ten sonra hiyerarşik olarak türetilen sınıflar varsa onlar da override işlemi gerçekleştirilir.

> Her ne kadar override edilmiş olsada özünde virtual olduğu için kalıtımsal açıdan hiyerarşik olarak devamındaki class'lardan override edilebilmektedir.



#### Sanal Yapılar Örnek 1

```csharp
class Program
{
    static void Main(string[]args)
    {
        Maymun m = new Maymun();
        m.Konus();
        
        Inek i = new Inek();
        i.Konus();
    }
}
class Memeli
{
    public virtual void Konus()
    {
        Console.WriteLine("Ben konuşmuyorum");
    }
}
class Maymun : Memeli
{
    Console.WriteLine("Ben maymunum...");
}
class Inek : Memeli
{
    
}
```



#### Sanal Yapılar Örnek 2

```csharp
class Program
{
    static void Main(string[]args)
    {
        Ucgen u = new Ucgen(3,4);
        Console.WriteLine(u.AlanHesapla());
        
        Dortgen d1 = new Dortgen(3,4);
        Console.WriteLine(d1.AlanHesapla());
        
        Dikdortgen d2 = new Dikdortgen(3,4);
        Console.WriteLine(d2.AlanHesapla());
    }
}
class Sekil
{
    // Protected ile işaretlenmiş herhangi bir member sade ve sadece ilgili sınıfta yahut o sınıftan kalıtım almış olan sınıfların içerisinde erişilebilir. Amma velakin nesne üzerinden erişilemez!
    protected int _boy;
    protected int _en;
    public Sekil(int boy, int en)
    {
        _boy = boy;
        _en = en;
    }
    public virtual int AlanHesapla()
    {
        return 0;
    }
}
class Ucgen : Sekil
{
    public Ucgen(int boy, int en):base(boy,en)
    {
        
    }
    public override int AlanHesapla()
    {
        return _boy * _en /2;
    }
}
class Dortgen : Sekil
{
    public Dortgen(int boy, int en):base(boy,en)
    {
        
    }
    public override int AlanHesapla()
    {
        return _boy * _en;
    }
}
class Dikdortgen : Sekil
{
    public Dikdortgen(int boy, int en):base(boy,en)
    {
        
    }
    public override int AlanHesapla()
    {
        return _boy * _en;
    }
}
```



### Sanal Yaplar Hakkında Özet

* Sanal yapılar OOP'de Polimorfizm(Çok Biçimlilik)'i uygulayan yapılardır. (İleride göreceğiz)
* Sanal yapıların en önemli özelliği Geç Bağlam (Late Binding)'dir.
* Eğer bir member sanal olarak bildirilmemişse, derleyici nesnelerin tür bilgisinden faydalanarak derleme zamanında hangi nesneden ilgili member'ın çağrılacağını bilir.
* Eğer bir member sanal olarak bildirilmişse, ilgili member'ın hangi nesne üzerinden çağrılacağı runtime'da belirlenir.
* Hangi member'ın runtime'da belirlenmesine Geç Bağlam(Late Binding) denir.
* Sanal yapı oluşturabilmek için ilgili member'ı virtual keywordü ile işaretlemeliyiz.
* Türeyen sınıflarda sanal yapıyı ezebilmek için override keywordü kullanılır.
* Türeyen sınıflar sanal yapıları override etmek zorunda değildir.
* Static yapılanmalar sanal olarak bildirilemezler! (İleride göreceğiz)



------



## Polimorfizm - Chapter 1

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/19-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Polimorfizm Nedir?

* Polimorfizm esasında kalıtım gibi bir biyolojik terimdir.

  Polimorfizm biyolojide, iki veya daha fazla farklı fenotipin aynı tür popülasyonunda bulunmasıdır.

> Kedigillerden olan bir aslana, hem aslan denildiğinde hem de kedi denildiğinde yadırganmıyorsa, işte burada çok biçililik (polimorfizm) söz konusudur.
>
> Başka bir örnek vermek gerekirse, karga, leylek, papağan bunların hepsi bir kuş iken, karga kargadır, leylek leylektir, papağan papağandır. Biz bunları hem kuş hem de kendi cinsleri ile tarif edebilmekteyiz, çünkü burada da çok biçimlilik vardır.

* OOP'de ise polimorfizm'e:

  ​	İki ya da daha fazla nesnenin aynı tür sınıf tarafından karşılanabilmesidir/referans edilebilmesidir.

  diyebiliriz.

* Bir başka deyişle:

  ​	Bir nesnenin birden fazla farklı türdeki referans tarafından işaretlenebilmesi polimorfizm'dir.

* Polimorfizm, bir nesnenin kalıtımsal olarak ilişkisi olan diğer nesnelerin referanslarıyla işaretlenebilmesini sağlar.

* Polimorfizm, OOP tasarımlarında geliştirilen koda daha manevrasal bir şekilde nitelik kazandıran ve yaklaşım sergilememizi sağlayan bir özelliktir.

* Polimorfizm, programlamada ki temel prensip olan 'Sol/Sağ Prensibi'ni'

  <img src=https://i.imgur.com/0udBLSZ.png width=60%, align=left />

  aşıp, eldeki nesnenin birden fazla referansla işaretlenebilmesini sağlar.



#### Peki! Bir nesnenin birden fazla referansla işaretlenmesi neye yarar?

* Bir nesnenin, birden fazla referansla işaretlenmesi; o nesnenin, birden fazla türün davranışını sergilemesini sağlar.



#### Polimorfizm Felsefesi- 1

Kuş deyince aklınıza ne geliyor?

- Muhabbet kuşu mu?
- Papağan mı?
- Tavuk mu?
- Kartal mı?
- Deve kuşu mu?
- Penguen mi?

> Farkındaysanız eğer, kuş deyince bu hayvanlardan herhangi biri aklınıza gelmese de özünde bunların bir kuş olduğunu görebilmekteyiz.
>
> Yani ben bir muhabbet kuşuna da kuş diyebilmekteyim. Yahut bir kartala da...
>
> Dikkat ederseniz, burada 'Kuş' kelimesi birden fazla hayvana karşılık gelebilmektedir.
>
> Yani 'Kartal' bir yandan 'Kartal' iken, bir yandan da 'Kuş'tur!
>
> İşte bu hayvanların kendi türlerinin dışında ortak olarak 'Kuş' diye nitelendirilmeleri Polimorfizm'dir.

Özetle, bir olguyu çoklu(poli), form(morfizmos) olarak tarif edebilmektir.

Yani, 'Kuş' cinsinden olan tüm hayvanların kendi türlerinin dışında bir yandan 'Kuş' olarak tarif edilmeleri çok biçililiktir.

**Peki kuş olmayan bir hayvana 'Kuş' diyemiyoruz! Misal 'Maymun' bir 'Kuş' değildir! Buradan şöyle bir sonuca varabilir miyiz?**

> Ortak atadan gelen, kalıtımsal olarak 'Kuş'tan türeyen tüm hayvanlar kendi türleri yahut 'Kuş' türü ile referans edilebilirler.
>
> Buradan da şunu anlıyoruz ki, yazılımsal açıdan çok biçimliliğin söz konusu olabilmesi için teknik olarak 'Kalıtım' olması gerekmektedir.
>
> Bunu dersin devamında daha detaylı göreceğiz.
>
> Bizler şimdi çok biçimliliğin felsefesine bir başka örnekle devam edelim.



#### Polimorfizm Felsefesi- 2

Şimdi düşünün, ben "Yemek yiyen canlılar, yediklerini sindirirler." diye bir cümle kursam.

Bu canlılar neler olabilir?

İnsanlar... Evet, insanlar yediklerini sindirirler.

Sıçanlar... Evet, sıçanlar da adı üzerinden yediklerini sindirirler.

Hindiler... Evet, hindiler de yediklerini sindirmektedirler.

İşte, görüldüğü üzere

Burada "yemek yiyen canlılar":

İnsanlar, sıçanlar, hindiler...

kullanılabilir.

Haliyle "Yemek yiyen canlılar, yediklerini sindirirler" dediğimizde bu olguyla çoklu formları tarif etmiş oluyoruz. Burada Polimorfizm vardır.



#### Polimorfizm Felsefesi- 3

<img src=https://i.imgur.com/K6Bd6NF.png width=75% align=left />

### Peki Programlamada Polimorfizm Nerede Kullanılmaktadır?

* Programlamada polimorfizm esasında en temelden beri kullanılmaktadır.

  * Misal olarak;

    Elimizdeki herhangi bir byte türündeki veriyi ister byte istersekte byte'dan büyük olan herhangi bir türde tutmak çok biçimliliktir.

  * Ya da Object türünün herhangi bir türdeki değeri alabilmesi; bir başka deyişle, object türüne herhangi türdeki veriyi atayabilmek polimorfizm'dir.

    Misal;

    ```csharp
    object valueO = 100;
    string value1 = 100;
    //100 burada hem object türünde, hem string, hem de diğer sayısal türlerde tutulabilmektedir.
    ```

Tabii, çok biçimlilik dendiğinde temel programlamadaki bu durumlardan ziyade, esas Nesne Tabanlı Programla'daki getirileri önemlidir!

Haliyle Nesne Tabanlı Programlama'da bir nesneyi kendi türünün referansıyla birlikte farklı türdeki referanslarla işaretleyerek Polimorfizm'i uygulayabilmekteyiz.

**Peki bunu nasıl yapıyoruz?**

Normal şartlarda bir nesne kendi sınıfının dışında başka bir sınıfın referansıyla İŞARETLENEMEZ!

Evet. Bir nesnenin başka bir nesne ile işaretlenebilmesi/referans edilebilmesi için kesinlikle arada kalıtımsal bir ilişki olması gerekmektedir.

Yani başka bir deyişle, Nesne Tabanlı Programlama'da Polimorfizm uygulamak istiyorsanız türler arasında kalıtım uygulanmış olmalıdır.

Ya da bambaşka bir deyişle; Nesne Tabanlı Programlama'da Polimorfizm aralarında kalıtımsal ilişki olan sınıflarda uygulanabilir. Aksisi mümkün değildir!



### Polimorfizm Kalıtım İlişkisi

* Bir nesneyi, kendi türünün dışındaki bir tür ile/referansla işaretleyebilmek için kesinlikle ilgili nesne, o türden türemiş olması gerekmektedir.

  ```csharp
  class A
  {
      
  }
  class B
  {
      
  }
  
  B b = new B(); //Bu durum gayet doladır ve şu ana kadar ele aldığımız prensiplerin ta kendisidir.
  A a = new B(); //Şimdi asıl mesele bu durumdur. B nesnesini A referansıyla işaretlemeye çalışırsak, şu ilgili durumda hata verecektir.
  ```

  B'nin A ile işaretlenebilmesi için, B'nin A'dan türemiş olması gerekir.

  ```csharp
  class A
  {
      
  }
  class B:A //İşte bu şekilde B sınıfı A sınıfından türediği taktirde artık B sınıfı bir yandan da A sınıfı olacağı için B nesnesi A referansı tarafından işaretlenebilecektir.
  {
      
  }
  A a = new B(); //Haliyle bu durum geçerli olacaktır.
  ```

Şimdi gelin, Polimorfizm ile Kalıtım İlişkisini gerçekçi bir örnek üzerinden daha da açalım.

```csharp
class Program
{
    static void Main(string[]args)
    {
        A a = new B();
        B b = new B();
        C c = new B();
    }
}
class A : C
{
    
}
class B : A
{
    
}
class C
{
    
}
```



#### Teorik Örnek

```csharp
class Insan
{
    
}
class Erkek : Insan
{
    
}
class Kadin : Insan
{
    
}
Erkek e = new Erkek(); // Herhangi bir Erkek nesnesi, bir Erkek olduğu için, Erkek referansıyla işaretlenebilir.
Insan i = new Erkek(); // Herhangi bir Erkek nesnesi, bir yandan da İnsan olduğu için İnsan referansıyla da işaretlenebilir.
```

İşte Erkek nesnesinin Insan referansıyla işaretlenebilmesi çok biçimlilik(polimorfizm)dir.

Aynı şey Kadin için de geçerlidir.



### Peki, Polimorfizm Bir Nesne Yönetiminde Neye Yarar?

Daha önceden de söylediğimiz gibi, Bir nesnenin birden fazla referansla işaretlenebilmesi; o nesnenin, birden fazla türün davranışlarını gösterebilmesini sağlar.

Örneğin;

```csharp
class A
{
    public void X(){}
}
class B : A
{
    public void Y(){}
}
class C : B
{
    public void Z(){}
}

C c = new C();
c.//dediğimizde C tipindeki olabilecek bütün özelliklere, nesnelere erişebilmekteyiz. X(),Y(),Z()
B b = new C();
b.//dediğimizde bize sadece B'nin özellikleri gelecektir X(),Y()
A a = new A();
a.//dediğimizde bize sadece A'nın özellikleri gelecektir X()
```

Polimorfizm, bir nesnenin kendi türünün dışında bir veya birden fazla türle işaretlenebilmesidir/referans edilebilmesidir. Ve bunun bize getirmiş olduğu farklı davranışları sergileyebilme niteliğidir.



------



## Polimorfizm - Chapter 2

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/20-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Polimorfizm Türleri

* Static Polimorfizm
* Dynamic Polimorfizm



#### Static Polimorfizm (Statik Çok Biçimlilik)

* Static, ileride göreceğimiz bir kavramdır.

* Şimdilik sadece Polimorfizm çerçevesinde Static Polimorfizm'i değerlendireceğiz.

* Static polimorfizm; derleme zamanında sergilenen polimorfizm'dir.

  Hangi fonksiyonun çağırılacağına derleme zamanında karar verilir.

* C#'da static polimorfizm deyince aklımıza Metot Overloading terimi gelmelidir.

* **Metot Overloading**: Aynı isimde birbirinden farklı imzalara sahip olan metotların tanımlanmasıdır. Ya da başka deyişle bir isme

  birden fazla farklı türde metot yüklemektir. Haliyle burada bir metotun birden fazla formunun olması **polimorfizm**'ken, bunlardan

  kullanılacak olanın derleme zamanında bilinmesi **static polimorfizm** olarak nitelendirilmektedir.

```csharp
class Matematik
{
    public long Topla(int s1, int s2) => s1 + s2;
    public long Topla(int s1, int s2, int s3) => s1 + s2 + s2;
    public long Topla(int s1, int s2, int s3, int s4) => s1 + s2 + s3 + s4;
}
```



#### Dynamic Polimorfizm (Dinamik Polimorfizm)

* Dinamik polimorfizm; çalışma zamanında sergilenen polimorfizm'dir.

  Yani hangi fonksiyonun çalışacağına run time'da karar verilir.

* C#'da dinamik polimorfizm deyince akla **Metot Override** gelmektedir.

* **Metot Override**: Base class'ta virtual olarak işaretlenmiş metotların derived class'ta override edilerek ezilmesi/yeniden yazılması işlemidir. Haliyle burada aynı isimde birden fazla forma sahip fonksiyonun olması **polimorfizm**'ken, bunlardan hangisinin kullanılacağının çalışma zamanında bilinmesi **dinamik polimorfizm** olarak nitelendirilmektedir.

```csharp
class Arac
{
    public virtual void Calistir()
        => Console.WriteLine("Araç çalıştı...");
}
class Taksi : Arac
{
    public override void Calistir()
        => Console.WriteLine("Taksi çalıştı...");
}
```

```csharp
class Program
{
    static void Main(string[]args)
    {
        Arac a = new Arac();
        a.Calistir();
        Arac t = new Arac();
        a.Calistir();
        Taksi t2 = new Taksi();
        t2.Calistir();
    }
}
```



### Polimorfizm Durumlarında Tür Dönüşümleri

* Polimorfizm, OOP'de bir nesnenin kalıtımsal açıdan ataları olan referanslar tarafından işaretlenebilmesidir. Haliyle

  ilgili nesne, bu ataları olan referans türlerine göre dönüştürülebilmektedir.

  ```csharp
  class A
  {
  	public string X{get; set;}
  }
  class B : A
  {
  	public string Y{get; set;}
  }
  class C : B
  {
  	public string Z{get; set;}
  }
  
  A a = new C(); //için
  //Bu nesne A referansında tutulan/işaretlenen/referans edilen bir C türünden nesnedir.
  
  //Haliyle ihtiyaç doğrultusunda A referansı üzerinden diğer kalıtımsal ilişkide olduğu referanslara yahut kendi referansına dönüştürülebilmelidir.
  
  C c = (C)a; //Misal olarak burada görüldüğü üzere A türünden olan a referansındaki özünde C türünden olan bu nesne kendi türünden bir referansla işaretlenmiştir. (Dikkat ederseniz bu işlem için Cast operatörü kullanılmaktadır.)
  //Bu durumun terside geçerlidir. Yani ilgili nesne kendi türünden kalıtımsal olarak ataları olan diğer türlere Cast edilebilir.
  ```

Dikkat edersen eğer Polimorfizm durumlarında kalıtımsal açıdan üst bir referans ile işaretlenebilmiş herhangi bir nesneyi kendi türünden işaretleyebilmek için Cast operatörünü kullanarak object türüne özel olan UnBoxing'e benzer bir hamlede bulunmuş oluyoruz.

Buradan anlıyoruz ki, object türünde gerçekleştirilen UnBoxing durumu esasında object türü ile gerçekleştirilebilen Polimorfizm'in bir sonucudur.

* Polimorfizm durumlarında tür dönüşümü gerçekleştirebilmek için **Cast** ya da **as** operatörleri kullanılabilir.

  Misal;

  Cast:

  * Üst türden alt türe kalıtımsal ilişkide dönüşüm sağlar.

    ```csharp
    A a = new C();
    C c = (C)a;
    ```

    Eğer ki, kalıtımsal ilişki olmayan herhangi bir türe dönüştürülmeye çalışılırsa derleyici hatası verecektir.

    Yok eğer kalıtımsal ilişkide olup fiziksel nesnenin hiyerarşik altında olan bir türe dönüştürülmeye çalışılırsa run time hatası verecektir.

    Misal; D türü A'dan kalıtım almıyorsa eğer hiyerarşide yer edinmeyeceğinden dolayı bu durumda derleyici hatası verecektir. Yok eğer
    kalıtımsal olarak C'nin altında A'nın torunu ise fiziksel C nesnesinin kendisinden küçük olan D referansıyla işaretlenmesi Polimorfizm mantığı 
    gereği mümkün olamayacağı için run time hatası verecektir.

  * Tersine olarak, kalıtımsal ilişkide alt türden üst türe cast operatörü ile de bir dönüşüm sağlanmaktadır.

  as:

  * Cast gibi kalıtımsal ilişki olan türler arasında referans dönüşümü yapabilmemizi sağlayan operatördür.

    ```csharp
    A a = new C();
    C c = a as C;
    ```

    Dönüşüm esnasında hiyerarşik olarak tüm türlere dönüşüm sağlar. Lakin kalıtımsal ilişkide olunmayan türlerde derleyici hatası verecektir.

    Ya da kalıtımsal ilişkide olup fiziksel nesnenin türünden daha alt hiyerarşide olan nesnelere dönüştürülmeye çalışıldığında Polimorfizm
    mantığı gereği ilgili referans o nesneyi karşılayamayacağından run time hatası VERMEYECEK! geriye null dönecektir.

  * Cast operatörünün as operatöründen farkı; biri dönüşüm sağlanamıyorsa hata fırlatırken(cast), diğeri null dönmektedir(as)

  is:

  * is operatörü kalıtımsal ilişkiye sahip nesnelerin Polimorfizm özelliğine nazaran fiziksel olarak hangi türde olduğunu veren bir operatördür.

    ```csharp
    A a = new C() {X ="1",Y="2",Z="3"};
    Console.WriteLine(a is B);//True
    Console.WriteLine(a is C);//True
    Console.WriteLine(a is A);//True
    Console.WriteLine(a is D);//False
    ```

    Haliyle dikkat ederseniz fiziksel nesnenin kalıtım hiyerarşisine uygun olan türlere 'true' olmayan türlere ise 'false' sonucunu döndürmektedir.
    Kalıtımsal ilişki olmayan sınıflarla yapılacak kontrolde de beklendiği gibi 'false' değeri dönecektir.

  

  Haliyle çok biçimlilik uygulanmış bir nesnenin ihtiyaç doğrultusunda (uygun olan) farklı bir türe dönüştürülebilmesi için işi garantiye alabilmek adına **is** kontrolü ardından **Cast** ya da **as** operasyonu sağlanması yeterlidir.



------



## Nesneler Arası İlişki Türleri

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/21-QR.png alt="İlgili ders içeriği" width=10% align=left />

### is - a İlişkisi Nedir?

* is - a ilişkisi tamamiyle kalıtımla alakalıdır. C# programlama dilinde, iki sınıf arasında

  ':' operatörü ile gerçekleştirilen kalıtım neticesinde ortaya bir is - a ilişkisi çıkmaktadır.

  Misal:

  - ```csharp
    class Araba
    {
        
    }
    class Opel : Araba
    {
        
    }
    ```

    Opel bir arabadır.

  - ```csharp
    class Hayvan
    {
        
    }
    class Inek : Hayvan
    {
        
    }
    ```

    İnek bir hayvandır.



### has - a İlişkisi Nedir?

* Bir sınıfın başka bir sınıfın nesnesine dair sahiplik ifadesinde bulunan ilişkidir. Bir yandan kompozisyon/composition ilişkisi de denmektedir.

  Misal;

  * ```csharp
    class Araba
    {
        
    }
    class Opel : Araba //is a ilişkisi
    {
        Motor motor; //has a ilişkisi
    }
    class Motor
    {
        
    }
    ```

    Opelin bir motoru vardır. Opel _has a_ Motor



### can - do İlişkisi Nedir?

* Sonraki derslerimizde göreceğimiz interface yapılanmasının getirisi olan bir ilişki türüdür.
* Tabi ki de can - do ilişkisini anlayabilmek için öncelikle interface yapılanması hakkında fikir sahibi olunması gerekmektedir.
* Kısaca interface, bir sınıfın imzasıdır. Yani bir sınıfın içerisinde olacak olan tüm member'ların şablonunu/arayüzünü oluşturduğumuz bir kontrattır.
  Herhangi bir interface'i uygulayan class o interface içerisinde tanımlanmış member imzalarını kendisinde oluşturmak zorundadır. Aksi taktirde compiler
  hata verecektir. Velhasıl tüm bunları a'dan z'ye ilgili konuya ait dersimizde tam teferruatlı incelemiş olacağız.
* Interface'ler içlerindeki member'ların imzalarını class'lara uygulattırdığından dolayı o interface'ler ilgili nesnelerin yapabilecekleri kabiliyetleri göstermektedir.
* Yani can - do ilişkisi bir nesnenin davranışlarını/kabiliyetlerini belirtmektedir.
* Bu davranış/kabiliyetler interface içerisinde tanımlanmaktadır.

```csharp
interface IAraba
{
    void Gazla();
    void Frenle();
}
class Opel : IAraba
{
    public void Gazla()
    {
        
    }
    public void Frenle()
    {
        
    }
}
```



### Association Nedir?

* Association, sınıflar arasındaki bağlantının zayıf biçimine verilen addır.

* Bu bağlantı oldukça gevşektir. Yani, sınıflar kendi aralarında ilişkilidir lakin birbirlerinden de bağımsızdırlar!

* Parça - bütün ilişkisi yoktur!

* Örneğin, bir otobüsteki yolcular ile otobüs arasındaki ilişki Association'dır.

  Nihayetinde hepsi aynı yöne gitmektedir. Lakin bir yolcu indiğinde bu durum otobüsün ve diğer yolcuların durumunu değiştirmez!



### Aggregation ve Composition Nedir?

* Nesneleri birleştirip daha büyük bir nesne yapmaya verilen isimlerdir.
* Yani her ikisi de birleştirilmiş nesnelerden bütünsel nesneler yapma durumlarını ifade eder.
* Her ikisinde de Association'da olmayan parça - bütün ilişkisi söz konusudur.
* Her ikisinde de sahiplik ilişkisi(has - a) vardır.

> O halde ikisinin arasındaki fark nedir?

<img src=https://i.imgur.com/GUcrWYe.png width=75% align= left />



### Aggregation vs Composition Örneği

<img src=https://i.imgur.com/SeG1qCt.png width=75% align=left />

<img src=https://i.imgur.com/2NmxZZ6.png width=75% align=left />



------



## Sınıf Modeline Özel Keyword'ler : this | base | readonly

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/22-QR.png alt="İlgili ders içeriği" width=10% align=left />

> Hatırlatma: 
> this kewrod'ü:
>
> 1. Bir sınıfın, uygulamanın herhangi bir noktasında üretilmiş olan instance'larını/object'lerini/nesnelerini sınıf içerisinde temsil etmemizi sağlayan bir keyword'dür.
>
> 2. Bir sınıf içerisinde bulunan birden fazla constructor overload'ı arasında zıplamamızı / atlamamızı sağlayan bir keyword'dür.

> Hatırlatma:
>
> base keyword'ü:
>
> 1. Bir instance'ın base class'ını sınıf modeli içerisinde temsil eden bir keyword'dür.
>
> 2. Base class'daki constructor'lardan seçim yapmamızı sağlar.

### readonly Keyword'ü

Bir class içerisinde tanımlanmış olan değişkenin yahut referansın sadece okunabilir olmasını sağlayan bir keyword'dür.

readonly keyword'ü ile işaretlenmiş olan referansların değerleri ya tanımlama noktasında ya da constructor'da verilebilir.

> const yapılanmalar, readyonly ile karıştırılabilir. Aralarındaki fark şöyledir:
> const tanımlandığı yerde değeri verilmelidir. Ve constructor içerisinde bile değer ataması gerçekleştirilemez!
>
> Lakin readyonly'de ister tanımlarken, isterseniz de constructor içerisinde değer ataması gerçekleştirilebilir.



------



## sealed Keyword

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/23-QR.png alt="İlgili ders içeriği" width=10% align=left />

### sealed Keyword'ü Nedir?

* Bir sınıfın miras vermesini yahut bir başka deyişle başka bir sınıf tarafından miras alınmasını engelleyen bir keyword'dür.
* Sadece sınıflarda ve sadece 'override' edilmiş metotlarda kullanılabilir.



### Class Üzerinde sealed Keyword'ünün İşlevi Nedir?

```csharp
sealed class A
{
}
class B : A //A sınıfı sealed olduğu için miras alınamaz derleyici hatası verir.
{
}
sealed record C
{
}
record D : C //Record'larda sınıf fıtratında oldukları için, aynı durum burası içinde geçerlidir.
{   
}
```



### Metot Üzerinde sealed Keyword'ünün İşlevi

* Kalıtımsal durumlarda, atalardan gelen ve birinci dereceden alt sınıf tarafından 'override' edilmiş olan 'virtual' member'ların hiyerarşideki sonraki sınıflar tarafından 'override' edilmesini ilgili member'ı sealed ile işaretleyerek engelleyebiliriz.

  ```csharp
  class A
  {
      public virtual void X()//A sınıfında virtual method tanımlandı
      {
          Console.WriteLine("Merhaba A");
      }
  }
  class B : A
  {
      sealed public override void X() // A sınıfından kalıtım alan B sınıfı içerisinde ilgili method override edildi
      {
          Console.WriteLine("Merhaba B");
      }
  }
  class C : B
  {
      public override void X() // B sınıfında sealed ile işaretlendiği için tekrar override edilemez. B sınıfındaki override haliyle devam eder.
      {
          Console.WriteLine("Merhaba C");//B'de sealed ile işaretlenmemiş olsaydı override edilebilirdi.
      }
  }
  ```

* Pratikte bu yöntem sayesinde üst sınıfın davranışını güvenli bir şekilde korumuş ve ilgili metodun değiştirilmesini önlemiş oluyoruz.



### sealed Keyword'ü Hangi Durumlarda Kullanılmalıdır?

* <u>Sınıfların Davranışlarını Korumak İstediğimizde</u>
  Kalıtımsal Hiyerarşide üst sınıfların özel metotları/davranışları varsa ve bu metotlardaki davranışların alt sınıflar tarafıdan değiştirilebilir olmasını istemediğimiz durumlarda, o metodu sealed olarak işaretleyebiliriz.
* <u>Performans İyileştirmesi İstendiğinde</u>
  Mikro seviyede yapılan bir optimizasyon neticesinde C#'ta bir sınıf sealed ile işaretlendiğinde sealed olmayan bir sınıfa göre ufak çapta bir performans artışı gösterdiği anlaşılmıştır. Bunun nedeni, derleyicinin sealed ile işaretlenmiş sınıfın miras alınamayacağını bilerek daha hızlı derleme yapmasıdır.
* <u>Singleton Design Pattern</u>
  Signleton Design Pattern'da bir sınıfın uygulama çapında tekil bir instance'ının olması amaçlanmaktadır. Haliyle ilgili sınıf sealed ile işaretlenerek, bu sınıftan herhangi bir kalıtımsal ilişkinin yaratılmasını engelleyebilir ve tek instance üretimini daha da garanti hale getirmiş oluruz.

> Ekstra bilgi : Java'da final keyword'ü C#'taki sealed keyword'ünün muadilidir.



------



## Partial Yapılanmalar

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/24-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Partial Yapılanmalar Nelerdir?

* Bir class'ın struct'ın yahut interface'in aynı veya farklı dosyalarda birden fazla parçasının tasarlanmasını, lakin bu parçaların özünde bir bütün olarak kullanılmasını sağlayan, kodun daha organize ve kolay okunabilirliğini arttıran özelliklerdir.

* Aynı namespace altında aynı isimde birden fazla sınıf tanımlayamayız, lakin bu sınıflar partial ile işaretlenirse aynı isimde tanımlanabilmesi mümkündür.

  ```csharp
  namespace Deneme
  {
      partial class X
      {
          
      }
      partial class X
      {
          
      }
  }
  ```

  Bu tanımlamalar fiziksel olarak farklı olsalarda compiler açısından bir bütünün parçalarıdır.

  `new X()`Yani yandaki gibi bu sınıftan bir nesne üretilmeye çalışıldığı zaman özünde tek bir nesne üretilecektir. 

  Bu tanımlar ister aynı ister farklı dosya içerisinde tanımlanabilir.

  > Aynı dll, aynı proje, aynı namespace içerisinde olması gerekmektedir.

  Tabi unutmamak lazımdır ki, fiziksel olarak farklı olan bu tanımların birbirlerinin parçaları olabilmesi için aynı namespace içerisinde, aynı isimde ve aynı yapıda olmaları gerekmektedir.

  

### Partial Yapılanmaların Kullanım Amaçları

* Partial yapılanmaları genellikle aşağıdaki amaçlar doğrultusunda tercih etmekteyiz:

  * Kod Bölümleme

    Büyük ve karmaşık yapıdaki sınıfları daha okunabilir ve düzenlenebilir parçalara bölmek için kullanılabilir.

    <img src = https://i.imgur.com/JiuBbcG.png width=%55 align=left />

  * İş Bölümü
    Ekiplerin, aynı sınıfın farklı kısımlarını aynı anda geliştirebilmeleri için kullanılabilir.

    <img src =https://i.imgur.com/lK38Yf4.png width=70% align=left />

  * Code Generator
    Code Generator sistemleri tarafından yazdığımız kodun ezilmemesi için kullanılabilir.



### Partial Yapılanmalarda Kısıtlamalar Nelerdir?

* Partial yapılanmalarda aşağıdaki kısıtlama durumları söz konusu olabilir :

  * Parça olması amaçlanan tüm yapılar partial keyword'ü ile işaretlenmelidir.

    ```csharp
    namespace X
    {
        var m = new MyClass();
        //m. dediğimizde her iki metotta gelecektir.
    partial class MyClass
    {
        public void A()
        {
            
        }
    }
    partial class MyClass
    {
        public void B()
        {
            
        }
    }
    partial class MyClass
    {
        public void C()
        {
            
        }
    }
    }
    ```

  * İç içe partial türler kullanılabilir.(Nested)

    ```csharp
    namespace X
    {
        partial class MyClass
        {
            partial class MyClass2
            {
                
            }
        }
        partial class MyClass
        {
            partial class MyClass2
            {
                
            }
        }
    }
    ```

  * Tüm partial yapılar aynı namespace altında bulunmalıdır. Farklı projeler yahut modüllere yayılamaz!

  * partial olan bir yapının tüm parçalarının türleri ve isimleri aynı olmak zorundadır.

  

### Partial Olabilen Yapılar

> Partial olarak neler tasarlanabilir?
>
> - class
> - record
> - struct
> - abstract class
> - interface

```csharp
partial record X
{
    
}
partial record X
{
    
}
```

```csharp
//abstract class'larda partial kullanılırken işaretin class'tan önce olması gerekmektedir. Semantik açıdan bu şekilde geliştirilmiştir.
//partial abstract class şeklindeki tanımlama da compiler hata verecektir.
abstract partial class MyClass
{
    
}
abstract partial class MyClass
{
    
}
```

```csharp
partial struct c
{
    
}
partial struct c
{
    
}
partial struct c
{
    
}
```

```csharp
partial interface IInterface
{
    
}
partial interface IInterface
{
    
}
```



### Partial Metotlar Nelerdir?

* partial yapılar, partial metotlar barındırabilirler.

  partial metotlar ne işe yararlar?

  Partial metotlar, sınıfın bir parçasında geliştiricinin metot bildiriminde bulunmasını sağlar. Başka bir parçasında ise diğer geliştirici tarafından bu metot tanımlanabilir. Bunun yararlı olduğu iki senaryo vardır :

  1) Template Code

  - Geliştirilen kodda metotlara dair bir şablon oluşturmak için kullanılabilir.

  - Bu şablonların uygulanıp uygulanmayacağına dair geliştiricinin karar vermesine olanak tanınır.

  - Eğer şablonu tanımlanan metot uygulanmazsa derleyici tarafından metodun imzası ve o metoda dair yapılan tüm çağrılar/tetiklemeler kaldırılır.

    Yani anlayacağınız, partial bir metot tanımlandığı taktirde ister uygulansın ister uygulanmasın herhangi bir farklı noktadan çağırılabilir/tetiklenebilir. Ancak uygulandığı taktirde herhangi bir derleme yahut çalışma zamanı hatası alınmayacaktır.

  ```csharp
  new MyClass();
  partial class MyClass
  {
      public MyClass()
      {
          X();
          Y();
          Z();
      }
      partial void X(); //tanım-declaration/beyanname
      partial void Y(); //tanım-declaration/beyanname
      partial void Z(); //tanım-declaration/beyanname
  
      partial void Y() //gövde-implementation/uygulama
      {
          Console.WriteLine("Y tetiklendi...");
      }
  }
  ```

  2. Source Generator

  - Source generator sistemleri ile sınıflarda tanımlanmış olan partial metot imzalarına karşılık gövdeler oluşturulabilir.

  - Geliştirici, uygulanacak metodun partial bir şekilde şablonunu ekledikten sonra source generator derleme sırasında bu metodun uygulamasını sağlar.

    Tabi geliştirici isterse, bu metotların gövdeleri source generator tarafından üretilmeden önce ya da başka deyişle bu metotlar uygulanmadan önce başka bir noktada çağırılabilir/tetikleyebilir.



### Partial Metot Kuralları

* Partial metotlarla ilgili aşağıdaki ekstra bilgileri bilmekte fayda vardır :

  * partial metotların runtime'da var olacağı kesin değildir. Eğer implementation edilmedilerse partial metotlar derleme sırasında yok sayılırlar.

  * Yukarıdaki durumdan dolayı partial metotlar delegate'ler ile temsil edilemezler.

  * partial metotlar :

    * ancak partial yapılar içerisinde tanımlanabilirler.
    * geri dönüş tipleri her daim void olmak zorundadır.
    * static veya generic olabilirler.
    * out parametresi alamazlar lakin ref parametresi alabilirler.
    * extern ve virtual olamazlar.

  * Aynı class'lar da olduğu gibi partial metodun hem tanımı hem de gövdesi partial ile işaretlenmelidir.

  * Bir metot imzasına karşılık tanım ve gövde olabilir.

  * Eğer ki partial metotlar başka bir metot tarafından çağırılırlarsa compiler tarafından var oldukları bilinecektir,

    yok eğer çağırılmazlarsa compiler derleme aşamasında ilgili metodu hiç görmeyecektir.

  * partial metotlar gövdeleri tanımlanıp public olarak işaretlenebilmektedir. Lakin gövdeleri tanımlanmadıysa imzaları public olarak işaretlenemezler.



------



## Abstraction (Soyutlama)

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/25-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Abstraction Kavramı Nedir?

> Abstraction bir mantıktır! Bir davranıştır.

> Düşünsel süreç:
>
> * Kullanıcı işlemlerinden sorumlu olan bir sınıf düşünelim.
>
> ```csharp
> class UserService
> {
>     public void CreateUser(UserInfo userInfo)
>     {
>         //...
>     }
>     public void RemoveUser(int userId)
>     {
>         //...
>     }
>     public List<User> Users{get; set;}
>     public bool ValidateUser(UserInfo userInfo)
>     {
>         //...
>     }
> }
> ```
>
> * Bu sınıfı kullanarak bir kullanıcı doğrulaması gerçekleştirmek istediğimizi varsayalım.
> * Bu işlem için ilgili sınıftan üretilen instance'a ihtiyacımız olduğu aşikar.
> * Kullanıcı doğrulaması yapmak istiyoruz ama doğrulama işleminin dışında bu sınıftaki kullanıcı işlemlerine dair tüm member'lar karşımızda...
>
> <img src =https://i.imgur.com/4ZY25Ez.png width=30% align=left />
>
> * Sizce, kullanıcı doğrulaması yapmak istediğimiz bir anda doğrulama işleminin dışındaki member'ların gelmesi ne kadar sağlıklıdır?
> * Ne de olsa kullanıcı burada doğrulama işlemi yapacaksa, sadece doğrulamaya dair member'lara erişebilmesi en ideali olsa gerek...
>
> - Yani bu durumu şöyle de düşünebiliriz. Bir tesisatçının iş yaparken o anda ihtiyacı olan aletlerin dışındakileri gözünün önünden kaldırması işini kolaylaştıracaktır.
>
>   İngiliz anahtarı ve penseyle çalışacağı yerlerde, elinin altında türlü türlü aletlerin olması iş konsantrasyonunu negatif etkileyecektir.
>
> * Aynı mantık yazılımcılar için de söz konusudur. O anda ihtiyaç dışı member'ların arasından yapılacak işe odaklı member'ları ayırt etmek yazılımcılar açısından sıkıntılı bir durumdur.
>
>   Ki yazılımcı ister istemez yanlış metodu seçebilir yahut konuyla alakasız member'lar konsantrasyonunu bozabilir.
>
> İşte bu tarz durumlara karşın, kodun daha idealize olması için göstereceğimiz davranışa Abstraction denmektedir.



### Abstraction'ın Özeti Nedir?

> Gerekli olanları göster, gereksiz olanları gösterme!

Abstraction, bir sınıfın member'larından ihtiyaç doğrultusunda alakalı olanları gösterip, alakalı olmayanları göstermemek demek oluyor.



### Abstraction Nasıl Uygulanır?

> Abstraction'ın interface'ler yahut abstract class'larla doğrudan hiçbir ilgilisi alakası yoktur!

* Bir operasyon anında, kullanılacak sınıfın sadece o anki operasyona uygun member'larını getirebilmek için (yani abstraction'ı uygulayabilmek için) ilgili member'ları temsil edebilecek bir referansa ihtiyacımız olacaktır.
* Bunu normal sınıflarla öyle ya da böyle gerçekleştirebiliriz, lakin bu davranışı uygularken sadece interface'ler yahut abstract class'lar diğer yapılara göre daha elverişli olabilmektedirler.
* Hele hele sınıfların birden fazla interface ile implement edebilmeleri, ilgili sınıfın birden fazla referansla refere edilebilmesi anlamına geleceğinden dolayı, interface'lerin abstraction işlemi için oldukça yaygın olarak kullanılan yapılar olduğunu düşünebiliriz.

```csharp
interface IUserValidateService
{
    Bool ValidateUser(UserInfo userInfo);
}
interface IUserProcessService
{
    void CreateUser(UserInfo userInfo);
    void RemoveUser(int userId);
    List<User> Users{get; set;}
}
class UserService : IUserValidate,IUserProcessService
{
    public void CreateUser(UserInfo userInfo)
    {
        //..
    }
    public void RemoveUser(int userId)
    {
        //..
    }
    public List<User> Users {get; set;}
    public bool ValidateUser(UserInfo userInfo)
    {
        //..
    }
}
```

<img src=https://i.imgur.com/HA2e7hV.png width=65% align=left />

* Görüldüğü üzere 'UserService' sınıfı içerisindeki member'lar ihtiyaca binaen interface referansları aracılığıyla ayrıştırılabilmekte ve abstraction davranışı böylece gerçekleştirilebilmektedir.
* İşte bu mantıkta olayı değerlendirdiğimizde abstraction davranışı için interface'leri veya abstract class'ları kullanıyoruz. Aksi taktirde bu davranış akla direkt interface ve abstract class getirmektedir ki, yanlıştır!
* *Bir de dikkat ederseniz eğer abstraction davranışı; member'ları ayıkladığı/gizlediği için 'encapsulation', kalıtımsal işlem gerektirdiği için 'inheritance' ve farklı referanslar kullandırdığı için 'polimorfizm' kavramlarıyla doğrudan bağlantılı bir davranıştır.*



### Abstraction'ın Etkisi Nedir?

> Nasıl yaptı bilmiyorum, sadece yapabildiğini biliyorum...

* Abstraction davranışının uygulandığı noktalarda, ilgili nesnenin işlevi nasıl yaptığından öte, ne yaptığıyla ilgilendiğimizi ifade etmiş oluyoruz.
* Bunu da genellikle interface'ler kullanılarak bu davranışı gerçekleştirdiğimizden dolayı söyleyebiliriz.
* İlgili interface, bizlere refere ettiği instance'daki o niteliği imza olarak söylemekte ama nasıl bir işlevsellik gösterdiğine dair bilgi vermemektedir.
* Dolayısıyla abstraction, nesnenin işleri nasıl yaptığını değil, hangi görevleri yapabileceğini söylememizi sağlamaktadır.

> Yani; X, Y ve Z davranışlarına sahip olan bir sınıfın, abstraction ile sadece Y member'ı erişilebilir hale getiriliyorsa, bu durumda kesinlikle bu sınıfta Y davranışının olduğu garanti ediliyor anlamına gelmektedir.



### Abstraction'ın Ana Hedefi Nedir?

> Bir nesnenin yalnızca o anki duruma göre ilgili davranışları gösterilmekte, gereksiz ayrıntıları gizlenmektedir.
>
> Abstraction'ın amacı, geliştiriciden bir sınıfa karşın olabilecek gereksiz ayrıntıları gizleyerek karmaşıklığın üstesinden gelmektir.
>
> O sınıftan üretilmiş bir instance'ı kullanırken o instance'ın sadece ne yapabileceğini göstermek lakin nasıl yapabileceği hakkında bilgi vermemektedir.
>
> Ayrıca yerine göre uygulama ayrıntılarını gizleyerek sadece ilgili davranışların erişilebilir olmasını sağlamakta abstraction'ın bir hedefidir diyebiliriz.



### Abstraction'a Örnek Senaryolar Verelim

> Abstraction, hayatın içinden bir davranıştır.

* Amazon hesabına giriş sürecinde kullanılacak bir nesneyi düşünürsek, eğer bu nesnenin o anda bizlerden sadece username ve password'ü alacak metoduna erişebilmemiz ve diğer konudan alakasız metotlarına erişmememiz bir abstraction davranışı neticesidir.
* Bir araba esasında birçok parçanın bir araya gelerek bütünsel olarak işlemesi neticesinde işlevsellik göstermektedir. Lakin şoför için araba sadece bir arabadır, yani şoför açısından arabanın motorunda dönen tüm fiziksel kurallar soyutlanmıştır. Şoför arabanın nasıl çalıştığını bilemeyebilir lakin çalıştığını bilir. İşte bu abstraction'dır.
* Evlerimizdeki prizler ve o prizlere takılan fişler arasında bir abstraction durumu söz konusudur. Bir prizi görevi kendisine takılan fiş üzerinden ilgili cihazlara elektrik göndermektir. Tabi bir prize birden çok fiş takılabilir, lakin priz hangi cihaza bağlı olduğunu asla bilmez. Burada priz açısından elektrik göndereceği cihazın detayları fiş sayesinde soyutlanmıştır. Priz sadece kendisine takılacak fişi bilir. Belki bu akla dependency inversion prensibini de getirebilir :)
  Doğrudur, bir yandan da bir abstraction örneğidir...
* Sabahları uyandığımızda ayılmak için genellikle kahve içeriz. Mutfağa gidip kahve makinesinin düğmesine basarız ve kahveyi yaparız. Bunu yapaabilmek için kahve makinesinin nasıl kullanılacağını bilmenin dışında su ve kahve çeğirdeği koymamız yeterli olacaktır. Bunların dışında; suyun ideal sıcaklığı, öğütülmüş kahve miktarı, makineyi çalıştırması için gerekli elektrik voltajı vs. gibi ekstradan bilgilere ihtiyacımız muhtemelen olmayacaktır.
  Bir kişi, kahve yapabilmek için gerekli olan tüm bu kaygıları ortadan kaldırabilmek için kahve makinesini yapmıştır. Böylece sizlerin kahve yapma sürecinde uygulayabileceğiniz davranışlar gereksiz detaylardan soyutlanmıştır.



------



## Abstract Class

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/26-QR.png alt="İlgili ders içeriği" width=10% align=left />

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



------



## Interface-1

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/27-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Interface Nedir?

> Programlama süreçlerinde interface yapılanması, nesnelere direkt olarak bir arayüz/şablon oluşturulmasını ve bu arayüz üzerinden geliştirici ile nesne arasındaki etkileşimin daha da kolaylaştırılmasını sağlayan bir araçtır.
>
> Hatta sadece geliştirici ile nesne arasındaki süreci kolaylaştırmamakta, ayrıca programın farklı bir programla yahut bileşenle etkileşimini de kolaylaştırmaktadır.
>
> Interface'in nesneye bir arayüz sağlaması, kullanıcı açısından, ilgili nesnenin nasıl çalıştığına dair ayrıntılı bilgiye ihtiyaç duyulmaksızın, sadece arayüzün sunduğu fonksiyonları veya property'leri kullanarak etkileşime girilmesini sağlar.



Yani anlayacağınız interface, o nesneye bir abstraction uygulayarak, belirlenmiş bir arayüz üzerinden çalışılmasını ve böylece ilgili nesne ile geliştirme sürecinin kolaylaştırılmasını sağlamaktadır.

Bu abstraction işlemini abstract class'la da gerçekleştiriyorduk! Interface'in bundan farkı nedir?

Evet, abstraction'ı abstract class ile gerçekleştirebiliyorduk. Lakin, abstract class'lar da bir nesnenin içerisindeki imzaları modellemenin dışında farklı işlemleride gerçekleştirebiliyorduk! Bu duruma istinaden dil geliştiricileri daha sade ve sadece imzalara konsantre olmuş bir yapıya olan ihtiyacı hissettiler ve interface yapısını ortaya koydular diyebiliriz.

Interface, abstraction class'ın sadece imzalara konsantre olmuş halidir! O yüzden abstraction davranışı açısından abstract class'a nazaran daha elverişlidir.



### Interface'in Genel Davranışı | Can-Do İlişkisi

<img src=https://i.imgur.com/YzPUhBL.png align=left />

**"INTERFACE, BİR SÖZLEŞMEDİR!"**



### Interface'i Neden Kullanıyoruz?

> En bariz nedeni Abstraction'dır.
>
> Bunun yanı sıra :

<img src = https://i.imgur.com/torFmNt.png width=75% align=left />



### Tanımlama ve İnşa Etme Kurallarını Toparlayalım

```csharp
interface IExample
{
    
}
```

* Bir interface tanımlayabilmek için **interface** keyword'ünden yandaki gibi istifade etmekteyiz.
* Bu yapılan tanımlama neticesinde artık IExample adında bir interface oluşturulmuş olacaktır.
* Ve Unutmayın! Interface'ler referans türlü değişkenlerdir. Yani bir referanstırlar.
  * Ayrıca şunu da bilmemizde fayda var ki; C# programlama dilinde bir interface'e isim verirken adının 'I' ile başlaması name conventions dediğimiz gelenektendir.
  * Bu gelenek sayesinde, geliştirici açısından I ile başlayan bir referansın interface olduğu direkt IntelliSense'de anlaşılacak ve geliştiricinin işi kolaylaşacaktır.

Peki interface'i nerede tanımlayabiliriz?

* Bir class nerede tanımlanabiliyorsa interface'de orada tanımlanabilir. Herhangi bir namespace, class, struct yahut interface içerisinde interface tanımlanabilir. Ya da isterseniz namespace dışında da tanımlama yapabilirsiniz.



### Interface İçerisinde İmzaların Oluşturulması

* Tanımlanmış bir interface içerisinde imzaların oluşturulması tabi ki de belirli kurallara tabiidir!

  Şöyle ki:

  ```csharp
  interface IExample
  {
      void AMethod();
      int BMethod();
      int CProperty{ get; set; }
  }
  ```

  Görüldüğü üzere interface içerisinde metot ve property imzaları tanımlanabilmektedir.

  İmza tanımlama sürecinde Access Modifier eşliğinde metot ve property'lerin gövdeleri tanımlanmaz! Sadece imzaları tanımlanır.

  Ve ayrıca dikkat ederseniz abstract class'lar da olduğu gibi imzalar abstract keywordü eşilinde de TANIMLANMAMAKTADIR!
  Abstract class'lar içlerinde derived class'lara miras olarak aktarılacak memberların eşliğinde bir yandan da zoraki uygulatılacak member'ları barındırabildiği için bu farkı abstract keyword'ü ile ortaya koymaktadırlar. Lakin interface'ler ve sadece sınıflara uygulatılacak imzaları barındırdıkları için bu şekilde bir ayrıma gereksinim görülmemiştir!

> Ayrıca interface içerisinde field tanımının mümkün olmadığını bilmenizde fayda vardır!
>
> Bunun nedeni, field'ların metotlar ve property'ler tarafından operatif olarak kullanılmalarıdır. Haliyle metotların yahut property'lerin kullanacakları operatif değişkenleri tanımlamak, ihtiyaç sürecinin parçası olacağı için interface içerisinde tanımlanmaları gereksiz/saçma olacaktır.
> Bu yüzden field tanımı yasaklanmıştır!



### Interface Kullanımı

* Interface'i kullanabilmek için kalıtım sürecinde kullandığımız : operatöründen aşağıdaki gibi istiface etmekteyiz.

  ```csharp
  class MyClass : IExample
  {
      
  }
  ```

  Dikkat ederseniz, sanki kalıtım alıyormuş gibi, ':' operatörü eşliğinde interface'i kullanabiliyoruz.

  Burada : operatörü eşliğinde interface kullanıldığı için artık bu kalıtım operatörü değil, uygulama/implementation operatörü olarak nitelendirilecektir.

  <img src=https://i.imgur.com/DWV1Vji.png align=left />

* Ya da bir başka deyişle : operatörüyle birlikte kullanılan yapı bir class değil de interface ise işte o zaman ilgili operatör implementation görevi görecektir.

* **Implementation:**
  Herhangi bir class'a herhangi bir interface'in ':' operatörü ile şablon/arayüz olarak sağlanmasıdır.

* Ya da başka deyişle, bir class'a başka bir class'tan kalıtım alıyorsa buna inheritance, yok eğer interface'den kalıtım alıyorsa buna implementation denir.

  * Çünkü, bir class'a interface'in uygulanması demek, o interface içerisindeki imzaların, o class'a zoraki dayatılması demektir.

    Haliyle bu eylem nihai olarak kalıtımsal bir davranıştan ziyade uygulama/'implementasyon' davranışıdır! O yüzden bu şekilde bir terminolojik betimeleme yapılmaktadır.
    Hatırlarsanız eğer, abstract class'lar içerisinde abstract ile işaretlenmiş olan member'ların derived class'lara zoraki uygulatılması da implementation diyrduk. Çünkü her iki durumda aynı mantıktan beslenmektedir.

Aşağıdaki gibi implementation neticesinde MyClass içerisine IExample interface'i içerisindeki imzalar, gövdeleriyle birlikte zoraki uygulatılacaktır.

```csharp
interface IExample
{
    void AMethod();
    int BMethod();
    int CProperty{ get; set; }
}
class MyClass : IExample
{
    public void AMethod()
    {
        //...
    }
    public void BMethod()
    {
        //...
    }
    public int CProperty { get; set; }
}
```

> Buradaki implementasyonun nasıl gerçekletşirildiğinin detaylarına birazdan gireceğiz. Bundan önce dikkatinizi çekmek istediğim bir nokta var ki; o da, interface üzerinden yapılan implementation neticesinde uygulanan member'ların imzalarında abstract class'lar dan yapılan implementation'da ki gibi <u>override</u> durumu söz konusu değildir!

**" INTERFACE'LER, SINIFLARIN İMZASIDIR! "**



### Interface Implementation Yöntemleri

<img src = https://i.imgur.com/VB5G4P3.png align=left />



### Interface'ler de Çoklu Kalıtım Durumu

* C#'ta, bir sınıf sade ve sadece tek bir sınıftan kalıtım alabilmektedir.

  Lakin bir sınıf aynı anda birden fazla interface'i uygulayabilmektedir.

  ```csharp
  class MyClass : IA, IB, IC 
  {
      public void A()
      {
          //..
      }
      public void B()
      {
          //..
      }
      public void C()
      {
          //..
      }
  }
  interface IA
  {
      void A();
  }
  interface IB
  {
      void B();
  }
  interface IC
  {
      void C();
  }
  
  ```

  Ayrıca dersimizin devamında inceleyecek olsakta tüm bu interface referansları tarafından ilgili class'ın instanc'ını refere edebileceğimizi bu noktada da söylemekte fayda görmekteyim.

  ```csharp
  //Instance new MyClass();
  IA a = new MyClass();
  IB b = new MyClass();
  IC c = new MyClass();
  // a. , b. , c. dediğimizde abstraction davranışı sergileyecek sadece ilgili interface'in memberlarına erişim sergilenecektir.
  ```



### Interface'in Interface'den Türemesi

> Interface'leri de kendi aralarında birbirlerinden türetebilmekteyiz.
>
> Eğer ki bu şekilde interface'in interface'e kalıtım vermesi durumu söz konusuysa burada : operatörü implementation değil, inheritance görevi görecektir ve bu interface'leri birbirlerinden türetecektir.

```csharp
interface IA
{
    void A();
}
interface IB : IA
{
    void B();
}
interface IC : IB
{
    void C();
}
```

> Ayrıca polimorfizm kuralalrı geçerli olacak ve misal olarak IC interface'inin implemente edileceği class, tüm üst referanslar tarafından da işaretlenebilir olacaktır.

> Unutma! C# programlama dilinde bir class sade ve sadece tek bir class'tan türeyebilirken, bir interface aynı anda birden fazla interface'den türeyebilmektedir.



### Bir Class'a Inheritance ile Birlikte Implementation Nasıl Uygulanır

* C#'ta bir class, farklı bir class'tan kalıtım alırken hem de bir yandan interface'i implement edecekse eğer önce class'tan kalıtım almalı, sonrasında da virgülle interface(ler) tanımlanmalıdır.

```csharp
class MyClass : ExampleClass, IA,IB,IC,ID
{
    
}
```



------



## Interface-2

<img src= https://raw.githubusercontent.com/trukafatsum/CSharpNotlarim/main/OOP/%C4%B0lgili%20Ders%20QR/28-QR.png alt="İlgili ders içeriği" width=10% align=left />

### Explicity Implement & Name Hiding

> Bir sınıf, aşağıdaki gibi aynı imzaya/imzalara sahip iki interface'i implement ederse eğer, bu durumda her iki interface'de ilgili member'ı ya da member'ları kendi implementasyonlarıymış gibi kullanacaktırlar.

```csharp
interface IArea
{
    double Calculate();
}
interface IPerimeter
{
    double Calculate();
}
class Calculator : IArea, IPerimeter
{
    public double Calculate()
    {
        //..
        return 0;
    }
}
```

> Ancak bu tarz bir durumda, ilgili member(lar)'ı interface'ine göre açıkça ayırmak isteyebilir ve operasyonlarınızı kullanılacak interface'e göre yürütmek isteyebilirsiniz.
> İşte bunu Explicity Implement ile gerçekleştirebiliyoruz.

```csharp
class Calculator : IArea, IPerimeter
{
    double IArea.Calculate()
    {
        //..
        return 0;
    }
    double IPerimeter.Calculate()
    {
        //..
        return 0;
    }
}
```

> Görüldüğü üzere Explicity Implement'te member'ların hangi interface'den geldiği bu şekilde belirtilmekte ve böylece fark kodsal açıdan yaratılmış olmaktadır.
> Yanlız explicity implement edilen member'lar private olarak tanımlanmak mecburiyetindedirler.
> Haliyle bu member'lara class referansı üzerinden değil, interface referansı üzerinden erişim gösterilebilir.
>
> Birden fazla interface'de aynı isimde bulunan imzaların tek bir sınıfa uygulatılmasına Name Hiding denmektedir!

```csharp
Calculator calculator = new();
IArea areaCalculator = calculator;
areaCalculator.Calculate();

IPerimeter perimeterCalculator = calculator;
perimeterCalculator.Calculate();

interface IArea
{
    int Calculate();
}
interface IPerimeter
{
    int Calculate();
}
class Calculator : IArea, IPerimeter
{
    int IArea.Calculate()
    {
        Console.WriteLine("A - X");
        return 0;
    }
    int IPerimeter.Calculate()
    {
        Console.WriteLine("B - X");
        return 1;
    }
}
```

> Tabi burada name hiding'e düşen bu member'lardan istediğinizi normal bir şekilde implement ederekte direkt ilgili sınıf instance'ı üzerinden erişilebilir hale getirebilir ve diğerlerini explicity implement edebilirsiniz.

```csharp
class Calculator : IArea, IPerimeter
{
    public double Calculate() //Default olarak IArea'ya karşılık gelecektir
    {
        //..
        return 0;
    }
    double IPerimeter.Calculate()
    {
        //..
        return 0;
    }
}
```



#### Base class'taki herhangi bir member ile Interface içerisindeki imzalar Name Hiding durumuna düşer mi?

> Hayır! Base class'ta bulunan herhangi bir member, interface içerisindeki bir imzayla uyuşuyorsa eğer, ilgili sınıfa o interface'in implementasyonu inheritance yöntemiyle gerçekleştirilecektir.

```csharp
class BaseClass
{
    public void Run()
    {
        Console.WriteLine("Base Class Run..");
    }
}
interface IRun
{
    void Run();
}
class MyClass : BaseClass, IRun
{
    
}
```

> Yani bu kod hata vermeyecektir, derlenecektir. Çünkü IRun içerisindeki 'void Run()' imzasına karşılık member 'BaseClass'tan kalıtımla 'MyClass' sınıfına aktarışmış ve böylece sözleşme gereği usul yerine getirilmiş olacaktır.



### Default Implementation (C# 8.0)

> Normal şartlarda interface yapılanması, içerisinde sade ve sadece kullanılacağı class'lara uygulatacağı member'ların imzalarını barındırmaktadır. Ancak C# 8.0 sürümüyle birlikte interface içerisinde kimi member'ların varsayılan uygulamasını gerçekleştirebileceğimiz ve imzasının eşliğinde gövdesini de tanımlayabileceğimiz, ***Default Interface Implementation*** özelliği tanıtılmıştır.
>
> Bu özellik sayesinde artık interface içerisinde istediğimiz member'ların gövdelerini tanımlayabiliyor ve böylece implementation sürecinde bir opsiyonel durum ortaya koyabiliyoruz.
>
> Şöyle ki:
>
> ```csharp
> interface IExample
> {
>  void Method1();
>  void Method2()
>  {
>      Console.WriteLine("Default implementation of Method2");
>  }
> }
> ```
>
> Yukarıdaki interface tanımına göz atarsanız eğer, içerisinde 'Method1' ve 'Method2' isimlerinde iki adet member göreceksiniz. Bu membler'lardan ilki imza halindeyken, ikincisi default implementation yani varsayılan bir uygulama içeren yapıya sahiptir.
>
> Bu durumda herhangi bir class 'IExample' interface'ini implement ettiğinde 'Method1'i uygulamak zorundadır, lakin 'Method2' uygulamayabilir.
> Böylece 'Method2'nin varsayılan uygulaması devreye girmiş olacaktır.

#### Method2'nin Uygulandığı Durumda

```csharp
class Example : IExample
{
    public void Method1()
    {
        Console.WriteLine("Implementation of Method1");
    }
    public void Method2()
    {
        Console.WriteLine("Implementation of Method2");
    }
}
```

#### Method2'nin Uygulanmadığı Durumda

```csharp
class Example : IExample
{
    public void Method1()
    {
        Console.WriteLine("Implementation of Method1");
    }
}
```

> Her iki durumda da method1 ve method2 tetiklenebilmektedir.

```csharp
IExample e = new Example();
e.Method1();
e.Method2();
```



#### Default Implementation, Interface Yapılanmasının Amacına Ayıkırı Değil Mi?

> Evet, default implementation özünde interface yapılanmasının varlık amacına aykırı olabilir. Yani bir interface varsa eğer, bu interface'i kullanacak olan sınıftan, bu interface'i uygulaması/implementation beklenir! Madem beklenmeyecek o zaman zaten interface'in varlık amacının dışında bir durum söz konusudur!

> Default implementation ise bir interface'in uygulamak istenmediği noktalarda default member'ları devreye sokmaktadır. Bu durumda 'Madem uygulamak istenmeyecek o zaman neden interface kullanalım ki?' sorusu akıllara gelebilir.

> Default implemetation ne de olsa kimi durumlarda kullanışlı bir özellikte olabilir. Özellikle, mimaride mevcut olan ve çok fazla noktada kullanılan bir interface'e yeni bir member eklemek bazen ciddi bir külfet doğurabilmektedir. İşte böyle bir durumda geriye dönük uyumluluk sağlayabilmek için default implementation özelliğinden istifade etmek, bizleri ortaya çıkabilecek maliyetten büyük ölçüde törpüleyecektir.



### Beyin Fırtınası

#### Sizce neden class'ların imzaları abstract class'lar değil de interface'lerdir?

> Interface'lerin nesnelerinin üretilmemeleridir. Böylece implementation sürecinde abstract class yerine interface seçmek kaynak tüketimi açısından daha az maliyetlidir.

#### Neden abstraction'da interface tercih edilir?

> Interface ile kullanıcıya bir sınıftaki var olan member'lardan sadece istenilenler gösterilir.
>
> Evet, bunu abstract'lar ile de gerçekleştirebiliriz, lakin interface'in tercih edilmesinin nedeni bir yandan da implementation sürecinde nesne üretip ekstradan maliyeti arttırmamasıdır.



### Interface'lerin İşaretleme Amaçlı Kullanılması

> Interface'lerin ne amaca hizmet ettiklerini ve neden kullanıldıklarını artık biliyoruz kannatindeyim. Biz yazılım geliştiriciler tarafından interface'ler tüm bu vizyonun dışında ekstradan yazılımdaki belirli instance'ları diğerlerinden ayırabilmek için işaretleme amaçlı da kullanabilmekteyiz.

> Misal olarak, bir uygulamadaki entity sınıflarını diğer sınıflardan ayırabilmek için IEntity isimli bir interface'le işaretleme davranışı gösterebiliriz. Ya da uygulamada loglama işlemi yapacak olan sınıfları diğerlerinden yine ayırabilmek için ILogger interface'i ile işaretleyebiliriz.
> Böylece yapıları davranışlarına yahut kurgudaki rolüne göre interface'ler sayesinde gruplayabilir ve daha emin ve tip güvenli bir şekilde çalışmalar gerçekleştirebiliriz.

Bu kullanıma esasında ***Marker Interface Pattern*** adı verilmektedir.



**" INTERFACE'LER, CLASS YAHUT ABSTRACT CLASS'LAR GİBİ KALITIM SÜREÇLERİNDE EKSTRADAN NESNE OLUŞTURMAZLAR! **
**BU YÜZDEN ABSTRACTION VE MARKER(İŞARETLEME) OPERASYONLARINDA CLASS VEYA ABSTRACT CLASS'LARA NAZARAN DAHA PERFORMANSLI ÇALIŞIRLAR "**

