# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Polimorfizm - Chapter 1

[TOC]



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

