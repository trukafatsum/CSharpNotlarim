# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## this Keyword'ü

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/04-QR.png width=10% alt="İlgili Video İçeriği QR" />

1. ### Sınıfın Nesnesini Temsil Eder

```csharp
MyClass m1 = new MyClass();
MyClass m2 = new MyClass();

// m1.X  --> m1 nesnesi üzerindeki X'i temsil eder
// m2.X  --> m2 nesnesi üzerindeki X'i temsil eder

class MyClass
{
    public void X()
    {
        //this
    }
}
```



2. ### Aynı İsimde Field ile Metot Parametrelerini Ayırmak İçin Kullanılır

```csharp
class MyClass
{
    int a;
    public void X(int a)
    {
        //a dediğimiz zaman parametreye erişir
        //this.a dedğimiz zaman o anki nesnenin üzerindeki field'ı temsil edecektir.
    }
}
```



3. ### Bir Constructer'dan Başka Bir Constructer'ı Çağırmak İçin Kullanılır

Constructer konusuna geldiğimiz zaman inceleyeceğiz.
