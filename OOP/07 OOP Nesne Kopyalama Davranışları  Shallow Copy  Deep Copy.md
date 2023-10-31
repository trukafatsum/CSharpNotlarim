# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Nesne Kopyalama Davranışları | Shallow Copy | Deep Copy

[TOC]



### Nesne&Değer Kopyalamadan Kastedilen Nedir?

Temel progralmamada görmüş olduğumuz değer türlü değişkenleri ele alarak başlayalım.

```csharp
int a = 5; // int türünde a değişkeni oluşturulur ve 5 değeri atanır.
int b = a; // int türünde b değişkeni oluşturulur ve *a'nın değeri* atanır.
a = 10; // a değişkenine 10 değeri atanır.
```

Burada yapmış olduğumuz davranışı incelediğimizde sonuç olarak a değişkeni 10, b değişkeni 5 olacaktır.

a veya b üzerinde yapmış olduğumuz herhangi bir operasyonel işlem, birbirini etkilemeyecektir.

> Değer türlü değişkenlerde default olarak Deep Copy uygulanır.



### Nesne&Değer Kopyalama Özünde İki Davranış Üzerinden Seyreder

#### 1)Shallow Copy

* Var olan bir nesnenin, değerin, referansının kopyalanmasıdır.

  Shallow copy neticesinde eldeki değer çoğaltılmaz. Sadece birden fazla referansla işaretlenmiş olur.

<img src=https://i.imgur.com/maobWLA.png width=700, align=left />

<img src=https://i.imgur.com/KbXgze9.png width=700, align=left />

<img src=https://i.imgur.com/tKvxsbs.png width=700, align=left />

> Referans türlü değişkenlerde default olarak Shallow Copy uygulanır.



#### 2)Deep Copy

* Var olan bir nesne, deep copy ile kopyalanıyorsa eğer ilgili nesne miktarı çoğalır. 

  Aynı özelliklere ve değerlere sahip olan bellekte farklı bir nesne daha oluşur.

**Klonlama işlemini manuel, kendi imkanlarımızla nasıl yapabiliriz?**

```csharp
class Program
{
    static void Main(string[]args)
    {
        MyClass m1 = new MyClass();
        MyClass m2 = m1; // Shallow Copy
        MyClass m3 = m1.Clone(); // Deep Copy
    }
}
class MyClass
{
    public MyClass Clone()
    {
        return (MyClass)this.MemberwiseClone();
        // MemberwiseClone bir sınıfın içerisinde o sınıftan üretilmiş olan o anki nesneyi klonlamamızı sağlayan bir fonksiyondur.
        // Object türünde geriye değer döndürdüğü için metodun geriye dönüş türüne cast etmemiz gerekir.
    }
}
```

