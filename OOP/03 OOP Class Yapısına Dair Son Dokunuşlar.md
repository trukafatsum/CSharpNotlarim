# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Class Yapısına Dair Son Dokunuşlar

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/03-QR.png width=10% alt="İlgili Video İçeriği QR" />

### Class İçerisinde Tanımlanan Class Sınıf Elemanı mıdır?

Sınıf elemanları;

* Feild
* Property
* Metot
* Indexer

> Nested-Type olan sınıflar bir sınıf elemanı değildir!



### Class Elemanlarına Açıklama Satırı Nasıl Eklenir?

```csharp
//Sınıfımıza veya sınıfın altındaki herhangi bir member'a açıklama eklemek için kullanılır.

/// <summary>
/// Bu bir örnek classtır.
/// </summary>
class Ornek
{
    /// <summary>
    /// Bu bir field'tir.
    /// </summary>
    int sayi;
    
    /// <summary>
    /// Bu bir property'dir.
    /// </summary>
    public string Metin {get; set;}
    
    /// <summary>
    /// Bu bir metottur.
    /// </summary>
    public void Topla ()
    {
        sayi += 10;
    }
    
    /// <summary>
    /// Bu bir örnek metot overloadıdır.
    /// </summary>
    /// <param name="a">a parametresi..</param>
    public void Topla (int a)
    {
        sayi += a;
    }
    
    /// <summary>
    /// Bu bir Indexerdır.
    /// </summary>
    public int this[int a]
    {
        get {return 0;}
    }
}
```

