# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Class Members

[TOC]



### Field Nedir?

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



### Property Nedir?

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



### Encapsulation (Kapsülleme/Sarmalama) Nedir?

Encapsulation, bir nesne içerisindeki dataların(field'lardaki verilerin) dışarıya kontrollü bir şekilde açılması ve kontrollü bir şekilde veri almasıdır.

İşte bu şekilde field'lardaki verilern erişim kontrolünü yapmamız için geliştirilmiş olan yapılara Property denmektedir.



### Property İmzaları

Property yapısı oluşturabilmenin yapısal olarak birkaç farklı yolu/farklı imzası vardır.

* Full Property
* Prop
* Auto Property Initializers (C# 6.0)
* Ref Readonly Returns
* Computed (Hesaplanmış) Properties
* Expression-Bodied Property
  * Read Only Property
* Init-Only Properties & Init Accessor (C# 9.0)



#### Property İmzaları - Full Property

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



#### Property İmzaları - Prop Property

Bir property her ne kadar encapsulation yapsa da temsil ettiği field'daki dataya hiç müdahale etmeden erişilmesini ve veri atanmasını sağlıyorsa böyle bir durumda kullanılan property imzasıdır.

> Prop property'ler compile edildiklerinde arkaplanda kendi field'larını oluştururlar. Dolayısıyla bir field tanımlamaya gerek yoktur!

```csharp
// PROP property
// [erişim belirleyicisi][değişken türü][property adi]{ get; set; }
```

Prop imzalarda ilgili property read only olabilir lakin write only olamaz!



#### Property İmzaları - Auto Property Initializers (C# 6.0)

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



#### Property İmzaları - Ref Readonly Returns (C# 7.2)

ref readyonly returns, bir sınıf (class) içerisindeki field'ı referansıyla döndürmemizi sağlayan ve bir yandan bu değişkenin değerini read only yapan özelliktir.

```csharp
class MyClass
{
    string adi = "Mustafa Kurt";
    public ref readonly string Adi => ref adi;
}
```



#### Property İmzaları - Computed(Hesaplanmış) Property

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



#### Property İmzaları - Expression-Bodied Property

Tanımlanan property'de Lambda Expression kullanmamızı sağlayan söz dizimidir.

```csharp
public string Cinsiyet => "Erkek";
```

> Bu şekilde expression-bodied ile imzalanan propertyler read only olarak oluşturulacaktır.



#### Property İmzaları - Init-Only Properties - Init Accessor (C# 9.0)

Init-Only Properties, nesnenin sadece ilk yaratılış anında propertylerine değer atamaktadır.

Böylece iş kuralı gereği runtime'da değeri değişmemesi gereken nesneler için bir önlem alınmaktadır.

> Init-Only Properties, developer açısından süreç esnasında değiştirilmemesi gereken property değerlerinin "yanlışlıkla" değiştirilmesinin önüne geçmekte ve böylece olası hata ve bug'lardan yazılımı arındırmaktadır.



### Metod Nedir?

Nesne üzerinde, field'larda ki yahut dışarıdan parametreler eşliğinde gelen değerler üzerinde işlemler yapmamızı sağlayan temel programatik parçalardır.



### Indexer Nedir?

Nesneye indexer özelliği kazandıran, fıtrat olarak property ile birebir aynı olan elemanlardır.

```csharp
// [erişim belirleyici][değişken türü]this[parametreler]
{
    get {}
    set {}
}
```

