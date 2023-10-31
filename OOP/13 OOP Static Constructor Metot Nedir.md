# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Static Constructor

[TOC]

Static yapılanmasını ilerleyen konularda inceleyeceğiz, lakin burada özel sınıf elemanları başlığı altında belirli kavramlardan bahsedeceğiz.



### Bir sınıftan nesne üretilirken ilk tetiklenen fonksiyon hangisidir?

MyClass isminde bir sınıfımız olsun ve new MyClass(); diyerek bu sınıftan bir nesne üretildiğini varsayalım.

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass();
    }
}
class MyClass
{
    public MyClass() // Constructor : İlgili sınıftan nesne üretilirken ilk tetiklenen fonksiyondur.
    {
        
    }
    static MyClass() // Static Constructor : İlgili sınıftan ilk nesne üretilirken ilk tetiklenen fonksiyondur.
    {
        // Üretilen ilk nesne dışında bir daha tetiklenmez!
    }
}
```

Mülakattayız ve karşımızda bu şekilde bir kod ekranı mevcut ve bize ilk tetiklenen fonksiyon soruldu.

Bu durumda aklımıza direkt 'constructor' gelecektir. Halbu ki cevap Static Constructor olması gerekmektedir.

> Bir sınıftan nesne üretilirken ilk tetiklenen fonksiyon Static Constructor'dır...
>
> Amma velakin belirli bir duruma istinaden!!!

Eğer ki bir sınıftan **ilk kez bir nesne üretiliyorsa** burada **static constructor** devreye girecektir, ardından üretilen her nesnede constructor fonksiyonu ile devam edecektir.

> Ön bilgi:
>
> Statik yapılanmalar uygulama bazlı datalarımızı yerleştirdiğimiz alandır.
>
> Statik yapılanması nesnelerden bağımsızdır diyerek aklımızda tutalım.

* Static Constructor'da geri dönüş değeri ve erişim belirleyicisi bildirilmez!

* Bir sınıf içerisinde sade ve sadece bir tane tanımlanabilir. Yani parametre almaz!!
* Özel sınıf elemanı olduğu için ismi sınıf ismiyle aynı olmak zorundadır.



### Pratikte inceleyelim

```csharp
class Program
{
    static void Main(string[]args)
    {
        new MyClass(); // Static constructor ve ardından constructor tetiklenir.
        new MyClass(); // Constructor tetiklenir.
    }
}
class MyClass
{
    public MyClass()
    {
        Console.WriteLine("MyClass constructor'ı tetiklenmiştir.");
    }
    static MyClass()
    {
        Console.WriteLine("MyClass static constructor'ı tetiklenmiştir.");
    }
}
```

> Not: 
>
> Static constructor'ın tetiklenebilmesi için illa ilk nesne üretimi yapılmasına gerek yoktur. İlgili sınıf içerisinde herhangi bir static yapılanmanın da tetiklenmesi, static constructor'ın tetiklenmesini sağlayacaktır.

#### Sigleton Design Pattern'da Static Constructor Kullanımına Örnek

```csharp
class Program
{
    static void Main(string[]args)
    {
        var database1 = Database.GetInstance;
        var database2 = Database.GetInstance; 
        var database3 = Database.GetInstance; //Her çağırdığımızda bize üretilen aynı nesneyi getirecektir.
        
        database1.ConnectionString = "assaffqwfwqfwfa";
    }
}
#region Singleton Design Pattern
    // Bir sınıftan uygulama bazında sade ve sadece tek bir nesne oluşturulmasını istiyorsan kullanabileceğin bir design pattern.
#endregion
class Database
{
    Database() // Private olacağı için dışarıdan nesne üretimini engellemiş olacağız.
    {
    }
    public string ConnectionString {get; set;}
    static Database database; // Field : İlgili sınıfın kendi referansında bir field oluşturuyoruz -> Statik bellekte duran bir referans
    public static Database GetInstance // Property : İlgili sınıftan getinstance isminde statik bir property oluşturuyoruz ve sadece get işlemini kullanıyoruz
    {
        get
        {
            return database;
        }
    }
    static Database()
    {
        database = new Database();
    }
}
```

