# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Sanal Yapılar : Virtual & Override

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/18-QR.png width=10% alt="İlgili Video İçeriği QR" />

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
>     public void MyMethod()
>     {
>         
>     }
> }
> ```
>
> Sanal Metot:
>
> ```csharp
> class MyClass
> {
>     public virtual void MyMethod()
>     {
>         
>     }
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

