# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Polimorfizm - Chapter 2

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/20-QR.png width=10% alt="İlgili Video İçeriği QR" />

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

