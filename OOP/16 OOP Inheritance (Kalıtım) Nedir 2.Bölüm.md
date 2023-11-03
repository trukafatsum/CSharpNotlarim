# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Inheritance (Kalıtım) - Chapter 2

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/16-QR.png width=10% alt="İlgili Video İçeriği QR" />

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

