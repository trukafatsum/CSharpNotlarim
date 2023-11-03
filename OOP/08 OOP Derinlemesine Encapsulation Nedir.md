# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Encapsulation

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/08-QR.png width=10% alt="İlgili Video İçeriği QR" />

### Encapsulation Nedir? Bir Veriyi Neden Kapsülleriz?

* Encapsulation, nesnelerimizde ki field'ların kontrollü bir şekilde dışarıya açılmasıdır.

* Bir başka deyişle, nesnelerimizi başkalarının yanlış kullanımlarından korumak için kontrolsüz değişime kapatmaktır.

<img src=https://i.imgur.com/i2BGM3V.png width=700, align=left />

<img src=https://i.imgur.com/R4frORb.png width=700, align=left />

> Field'larımıza direkt erişilmesini istemeyiz dolayısıyla encapsulation uygularız.



### Encapsulation Nasıl Uygulanır?

C#'da Encapsulation iki türlü uygulanmaktadır;

* Metot ile Encapsulation
* Property ile Encapsulation



### Eskiden Encapsulation'ı Nasıl Yapılıyordu?

C#'da property dediğimiz yapılanma gelmeden önce metotlar üzerinden encapsulation uygulanıyordu.

```csharp
class MyClass
{
    private int a;
    public int AGet ()
    {
        return this.a;
    }
    public void ASet (int value)
    {
        this.a = value;
    }
}
```



### Property ile Encapsulation

Class Members başlığı altında ele aldığımız üzere property yapılanması ile encapsulation işlemi gerçekleştirmiş oluyoruz.

Var olan bir field ile encapsulation gerçekleştirebilmek için full property kullanmamız gerekir.

```csharp
class MyClass
{
    private int a;
    public int A //Full Property
    {
        get { return a; }
        set { a = value; }
    }
}
```

