# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Class Kavramı

[TOC]


<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/01-QR.png width=10% alt="İlgili Video İçeriği QR" />

### Sınıf Nedir? Neden Sınıf  Yapısı Kullanılır?

Sınıf nesne modelidir.

OOP'de bir object oluşturabilmek için öncelikle o objectin modellenmesi tanımlanması gerekmektedir.

Bir objenin modelini/tanımını oluşturabilmek için class yapısı kullanılır.



### Sınıf ile Nesne Arasındaki İlişki Nedir?

Sınıf ile nesne arasındaki ilişki, sınıflarda nesnelerdeki ortak alan tanımları yapılır.

Sadece bir modele karşı bir sınıf tanımlarız ve nesneler sınıftan çoğul olarak türer, bire çok bir ilişki vardır.



### Sınıf Nasıl ve Nerede Oluşturulur?

Bir sınıf oluşturmak istiyorsak şu şekilde oluştururuz:

```csharp
/*Prototip 
class Isim
{
    
}
*/
// class'lar bir referans türüdür.
```



Sınıflar 3 farklı yerde oluşturulabilir;

* Namespace İçerisinde
* Namespace Dışarısında
* Class İçerisinde (Nested Type)

```csharp
namespace oop_sinif
{
    class MyClass1 //Namespace İçerisinde
    {
        
    }
    class MyClass3
    {
        class MyClass4 // Class İçerisinde (Nested Type)
        {
            
        }
    }
}
class MyClass2 //Namespace Dışarısında, diğer tüm sınıflardan erişilebilir.
```

Bir class tanımlamasında tanımlanan yerde (namespace/dışı, class) aynı isimde birden fazla class tanımlanamaz.



### Sınıf ile Nesne Modeli Tasarlama

```csharp
class Program
{
    OrnekModel model = new OrnekModel; // Referans noktası OrnekModel model; Referans alarak nesne oluşturma OrnekModel model = new OrnekModel;
    static void Main (string[] args)
    {
        Console.WriteLine(model.Y(5,10));
        Console.WriteLine(model.Y(20,2));
    }
}
public class OrnekModel
{
    //Fields
    int a;
    int b;
    //Functions
    public void X()
    {
        Console.WriteLine(a + " " + b);
    }
    public int Y()
    {
        return a * b;
    }
}
```



### Sınıf Modelinden Referans Noktası Oluşturma

Bir class tanımlandığında o class adı bir türdür. Haliyle o türü kullanabilmek için direkt olarak class adını kullanmamız yeterlidir.

Eğer ki bir referans noktasında herhangi bir nesne referans edilmiyorsa, o referans noktasi/referans null değere sahiptir.

**Referans türlü değişkenler özünde nullable değişkenlerdir.**



