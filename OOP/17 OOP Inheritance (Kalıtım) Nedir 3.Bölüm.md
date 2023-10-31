# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Inheritance (Kalıtım) - Chapter 3

[TOC]



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
> >     public int X{get; set;}
> > }
> > class B : A
> > {
> >     public new int X {get; set;}
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