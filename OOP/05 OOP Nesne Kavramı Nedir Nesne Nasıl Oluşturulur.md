# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Nesne Kavramı

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/05-QR.png width=10% alt="İlgili Video İçeriği QR" />

### Nesne Nedir?

Nesneler içerisinde bir veya birden fazla, anlamlı değerleri barındıran (complex) değerlerdir.

Nesneleri modellememizi sağlayan class'lar ise Complex Type'lardır.



### Bir Sınıftan Nesne Üretme/Türetme/Oluşturma

```csharp
class MyClass
{
    public int A {get; set;}
    public void X()
    {
        
    }
}
```

C#'ta nesne üretimi için new operatörü kullanılmaktadır.

```csharp
// new Type();
// Type --> Nesnesini talep ettiğimiz sınıf
// ()   --> Constructor metot
```

```csharp
class Program
{
    new Entity1();
}
class Entity1
{
    
}
```



### Target-Type New Expression (C# 9.0)

Nesne oluşum sürecinde, oluşturulacak olan nesne eğer ki direkt bir referansa atılıyorsa, burada hangi nesnenin oluşturulduğu referans sayesinde bilinebilmektedir.

Dolayısıyla ilgili nesnenin oluşturulması için

```csharp
// Type x = new Type()
```

semantiğinden ziyade

```csharp
// Type x = new()
```

şeklinde de oluşturmamızı sağlayan bir özelliktir.
