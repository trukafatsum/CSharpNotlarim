# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Desctructor/Finalizer Functions

[TOC]



### Desctructor/Finalizer Metot Nedir?

Bir class'tan üretilmiş olan nesne imha edilirken otomatik çağrılan metottur.

C# programlama dilinde Desctructor sadece class yapılanmasında kullanılabilir ve bir class sade ve sadece bir adet Destructor içerebilir.



Peki bir nesne hangi şartlarda kim tarafından imha edilir?

* Bir nesnenin imha edilmesi için;

  * İlgili nesne herhangi bir referans tarafından işaretlenmemelidir,
  * Yahut nesnenin oluşturulduğu ve kullanıldığı scope sona ermiş olmalıdır.
  * Yani anlaşılan ilgili nesneye bir daha erişilemez hale gelinmelidir.

  işte o zaman nesne imha edilir.

Peki kim tarafından?

### Garbage Collector

* Uygulamada lüzumsuz olan nesneleri toplamak için Garbage Collector isimli bir mekanizma devreye girer.

* Esasında Garbage Collector C#'da bellek optimizasyonunu üstlenen bir yapılanmadır.

* C#'da Garbage Collector'ın ne zaman iş göreceği tahmin edilemez. Kafasına göre takılır :)

* Dolayısıyla biz geliştiricilerin bu mekanizmaya müdahale etmesi pek önerilmez.



### Desctructor Tanımlama Kuralları

```csharp
class MyClass
{
    ~MyClass()
    {
        //..İşlemler..
    }
}
```

> ~MyClass() : Bir sınıf içerisinde sade ve sadece bir adet desctructor tanımlanabilir.
>
> ~ : Desctructor tanımlayabilmek için ~(tilde) işareti kullanılır.
>
> MyClass : Ve her özel sınıf elemanlarında olduğu gibi destructor'da sınıf ismiyle aynı isimde olan bir fonksiyondur.
>
> İşte bu fonksiyon, bu sınıftan üretilen nesne imha edilirken otomatik olarak son kez "selametle" demek için (yani son işlemleri yapabilmek için) tetiklenecek olan fonksiyondur.

```csharp
class MyClass
{
    public MyClass() // Constructor
    {
        Console.WriteLine("Selamın aleyküm..");
    }
    ~MyClass()   // Destructor
    {
        Console.WriteLine("Selametle..");
    }
}
```



### Garbage Collector Kullanımına Örnek

Her ne kadar manuel olarak çağırılması önerilmese de, destructor'ı gözlemleyebilmemiz açısından buradaki örnekler üzerinden inceleyelim.

#### Örnek 1 - Referanssız nesneler üzerinden garbage kullanımı

```csharp
class Program
{
    static void Main(string[]args)
    {
        int sayi = 100;
        while (sayi >= 1)
        {
            new MyClass(sayi--);
        }
        Console.WriteLine("*******************************");
        GC.Collect(); // Burada garbage collector'ı çağırarak o anki boşta olan tüm nesnelerin temizlenmesini sağlamaktayız.
        Console.ReadLine();
    }
}
class MyClass
{
    int no;
    public MyClass(int no) // Constructor
    {
        this.no = no;
        Console.WriteLine($"{no} numaralı nesne oluşturuldu.");
    }
    ~MyClass() // Destructor
    {
        Console.WriteLine($"{no} numaralı nesne destructorda tetiklendi ve silindi.");
    }
}
```

#### Örnek 2- Metot ile nesne oluşturulması, metodun sonlanması neticesinde garbage kullanımı.

```csharp
class Program
{
    static void Main(string[]args)
    {
        NesneOlustur();
        GC.Collect(); // Burada garbage collector'ı çağırarak o anki boşta olan tüm nesnelerin temizlenmesini sağlamaktayız.
        Console.ReadLine();
    }
    static void NesneOlustur() // Metot
    {
        MyClass m = new MyClass(); // MyClass sınıfından m referansı ile işaretlenmiş bir nesne üretilmesini sağlar.
    }
}
class MyClass
{
    public MyClass() // Constructor
    {
        Console.WriteLine("Nesne oluşturuldu.");
    }
    ~MyClass() // Destructor
    {
        Console.WriteLine("Nesne silindi. Son çalışan metot!")
    }
}
```

