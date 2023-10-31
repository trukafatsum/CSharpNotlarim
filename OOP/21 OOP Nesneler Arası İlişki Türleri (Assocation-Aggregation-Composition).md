# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Nesneler Arası İlişki Türleri

[TOC]



### is - a İlişkisi Nedir?

* is - a ilişkisi tamamiyle kalıtımla alakalıdır. C# programlama dilinde, iki sınıf arasında

  ':' operatörü ile gerçekleştirilen kalıtım neticesinde ortaya bir is - a ilişkisi çıkmaktadır.

  Misal:

  -  ```csharp
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