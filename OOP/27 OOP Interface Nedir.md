# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Interface-1



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



