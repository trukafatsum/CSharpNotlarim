# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Inheritance (Kalıtım) - Chapter 1

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/15-QR.png width=10% alt="İlgili Video İçeriği QR" />

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

