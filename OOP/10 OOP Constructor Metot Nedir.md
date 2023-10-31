# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Constructor

[TOC]



### Constructor Metot Nedir?

Constructor bir nesne üretimi sürecinde ilk tetiklenen metottur.

```csharp
// new T (); () : Constructor
```

Parantez semantik açıdan metotlarda vardır. Bir metodu tetiklerken açmış olduğumuz parantez Constructor'dır.

Bir nesne üretilirken belirli konfigürasyonlarla nesnenin gelmesini istiyorsak, bu konfigürasyonları Constructor metod içerisinde tanımlarız.

Yani nesne üretim esnasında nesneye dair konfigürasyon yapmamızı sağlayan ve nesne üretilirken ilk tetiklenen fonksiyondur.

> Constructor, nesne oluşturma sürecinde tetiklenmek zorundadır!



### Constructor Davranış Modeli

<img src=https://i.imgur.com/pNw8A0p.png width=75%, align=left />

> Nesneye dair konfigürasyonları yapmayıp, başka işlemlerde yapabilmekteyiz.
> Sadece nesne içerisindeki field'lara property'lere değer atamakla yükümlü değildir.
>
> Ama genellikle nesneye dair konfigürasyonları yapmak için kullanırız.



### Constructor Metot Nasıl Oluşturulur?

* Constructor, özel bir sınıf elemanıdır.

  Özel olsada fıtrat olarak bir metottur.

  Lakin bildiğimiz metot imzalarından bir nebze farka sahiptir.

* Constructor'ların;

  * Metod adı sınıf adıyla aynı olmalıdır! (Özel sınıf elemanlarının dışında hiçbir member sınıf adıyla aynı olamaz!)
  * Geri dönüş değeri olmaz/belirtilmez!
  * Erişim belirleyicisi public olmalıdır! (private olduğu durum ayriyetten incelenecektir)

```csharp
class MyClass
{
    public MyClass() //Constructor : Geri dönüş değeri yok, sınıf ile aynı isimde
    {
        
    }
    public void X() //Metot : Geri dönüş değeri void, sınıf ile aynı isimde olsa dahi compiler hata verecektir.
    {
        
    }
}
```

> Normal bir member sınıf ismiyle aynı olamaz, oluyorsa da bu constructor metottur.

> Hatırlatma : C# 9.0'da gelen Target Type özelliğinde dahi biz construtor'ı tetiklemekteyiz.
> ```csharp
> class Program
> {
>     static void Main(string[]args)
>     {
>         MyClass m = new(); //C# 9.0 Target Type'da tetiklenen construtor örneği
>     }
> }
> class MyClass
> {
>     public MyClass()
>     {
>         Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur.");
>     }
> }
> ```
>
> 

### Default Constructor

Herhangi bir class'ı içi boş bir şekilde ele alalım;

```csharp
class MyClass
{
    // Bu sınıf içerisinde herhangi bir construtor tanımlanmamış olabilir.
}
```

```csharp
new MyClass(); // Lakin nesne üretirken de constructor tetiklenmektedir!
```

> Her sınıfın içerisinde tanımlamasak dahi default bir constructor mevcuttur.
>
> Çünkü her class'ın default bir constructor'ı mevcuttur.
>
> Eğer ki bir class'a constructor eklersek default constructor'ı ezmiş oluruz!



### Parametreli Constructor

Herhangi bir class'da constructor metot oluştururken bunu parametre alacak şekilde de oluşturabiliriz.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(5);
        new MyClass(10);
        
        MyClass m = new(15);
    }
}
class MyClass
{
    public MyClass(int a)
    {
        Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur." + a);
    }
}
```

> Constructor parametre alabildiğine göre overloading yapılabilir fonksiyonlardır.
>
> > Hatırlatma:
> >
> > Bir sınıf içerisinde aynı isimde birden fazla member tanımlayamayız. Lakin member'ların imzalarında farklılık olması durumunda çoklu yükleme (overloading) işlemi yapabilmekteyiz ve tanımlayabilmekteyiz.

```csharp
class MyClass
{
    public MyClass() //Overload
    {
        
    }
    public MyClass(int a) //Overload #1
    {
        Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur." + a);
    }
    public MyClass(string a) //Overload #2
    {
        Console.WriteLine("Bir adet myclass nesnesi oluşturulmuştur." + a);
    }
    public MyClass(string a, int b) //Overload #3
    {
        
    }
}
```



### Constructor'ın Erişim Belirleyicisini Private Yaparsak Sorunsalı?

> Constructor tanımlamadığımız durumda biz bir nesne oluştururken new MyClass(); olarak tanımlayabildiğimize göre,
>
> default constructor'ın erişim belirleyicisi de public durumdadır.
>
> Kendimiz bir constructor tanımlayarak bunun erişim belirleyicisini private yaparsak, ilgili sınıfın private yapılan constructor'ı dışarıdan erişilemeyeceğinden dolayı, haliyle bu sınıfa dair nesne üretiminde hata alacağız.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(); // Constructor'a erişilemeyeceği için nesne üretimi engellenir.
    }
}
class MyClass
{
    private MyClass() // Private
    {
        
    }
    void X()
    {
        new MyClass(); //-> Constructor içeriden erişilebilir bir yapıda olduğu için bu şekilde nesne üretimi gerçekleştirilebilmektedir.
    }
}
```

> [Singleton Design Pattern](https://metinalniacik.medium.com/singleton-design-pattern-tasar%C4%B1m-%C3%B6r%C3%BCnt%C3%BCs%C3%BC-b7221929dc26)'ı incelemeniz önerilir.



### this Keywordüyle Constructor'lar Arası Geçiş

> Hatırlatma:
>
> this Keyword'ü bir sınıfın içerisinde, o sınıfın o anki nesnesini temsil eder.
>
> Ayrıca this Keyword'ü bir sınıfın nesnesinin içerisinde tanımlanmış olan farklı constructor'lar arasında geçiş yapabilme sorumluluğunu da üstlenebilmektedir.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(5,10);
    }
}
class MyClass
{
    public MyClass()
    {
        Console.WriteLine("1. Constructor");
    }
    public MyClass(int a) : this() // Herhangi bir constructor'ın yanına this keyword'ünü getirdiğimiz durumda, o anki constructor'ın dışındaki diğer constructor'lara erişmemizi sağlayacaktır.
    {
        Console.WriteLine($"2. Constructor : a = {a}");
    }
    public MyClass(int a, int b) : this(a) //this(a) ile bir üstte tanımamış olduğumuz constructor'ı tetiklemiş oluyoruz.
    {
        Console.WriteLine($"3. Constructor : a = {a} | b = {b}");
    }
}
```

> this () 'dediğimizde erişebileceğimiz parametreler sadece tanımlanmış olan constructor'ların parametrelerindeki değerlere erişebilmektedir.
>
> Ayriyetten o parametre değeri dışında kendi vereceğimiz değerleri alabilmektedir.



### Record'larda Constructor

Record'lar özünde sınıf oldukları için class üzerinde anlatılmış olan kurallar record'larda da geçerli olacaktır.

* Parametre alabilecekler
* Overloading işlemlerine tabii tutulabilecekler
* this ile aynı şekilde yine temsil edilebilecek ve overloadlar arası geçiş yapabilecektir

