# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Interface-2

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/28-QR.png width=10% alt="İlgili Video İçeriği QR" />

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
>     void Method1();
>     void Method2()
>     {
>         Console.WriteLine("Default implementation of Method2");
>     }
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

