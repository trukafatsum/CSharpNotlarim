# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Partial Yapılanmalar

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/24-QR.png width=10% alt="İlgili Video İçeriği QR" />

### Partial Yapılanmalar Nelerdir?

* Bir class'ın struct'ın yahut interface'in aynı veya farklı dosyalarda birden fazla parçasının tasarlanmasını, lakin bu parçaların özünde bir bütün olarak kullanılmasını sağlayan, kodun daha organize ve kolay okunabilirliğini arttıran özelliklerdir.

* Aynı namespace altında aynı isimde birden fazla sınıf tanımlayamayız, lakin bu sınıflar partial ile işaretlenirse aynı isimde tanımlanabilmesi mümkündür.

  ```csharp
  namespace Deneme
  {
      partial class X
      {
          
      }
      partial class X
      {
          
      }
  }
  ```

  Bu tanımlamalar fiziksel olarak farklı olsalarda compiler açısından bir bütünün parçalarıdır.

  `new X()`Yani yandaki gibi bu sınıftan bir nesne üretilmeye çalışıldığı zaman özünde tek bir nesne üretilecektir. 

  Bu tanımlar ister aynı ister farklı dosya içerisinde tanımlanabilir.

  > Aynı dll, aynı proje, aynı namespace içerisinde olması gerekmektedir.

  Tabi unutmamak lazımdır ki, fiziksel olarak farklı olan bu tanımların birbirlerinin parçaları olabilmesi için aynı namespace içerisinde, aynı isimde ve aynı yapıda olmaları gerekmektedir.

  

### Partial Yapılanmaların Kullanım Amaçları

* Partial yapılanmaları genellikle aşağıdaki amaçlar doğrultusunda tercih etmekteyiz:

  * Kod Bölümleme

    Büyük ve karmaşık yapıdaki sınıfları daha okunabilir ve düzenlenebilir parçalara bölmek için kullanılabilir.

    <img src = https://i.imgur.com/JiuBbcG.png width=%55 align=left />

  * İş Bölümü
    Ekiplerin, aynı sınıfın farklı kısımlarını aynı anda geliştirebilmeleri için kullanılabilir.

    <img src =https://i.imgur.com/lK38Yf4.png width=70% align=left />

  * Code Generator
    Code Generator sistemleri tarafından yazdığımız kodun ezilmemesi için kullanılabilir.



### Partial Yapılanmalarda Kısıtlamalar Nelerdir?

* Partial yapılanmalarda aşağıdaki kısıtlama durumları söz konusu olabilir :

  * Parça olması amaçlanan tüm yapılar partial keyword'ü ile işaretlenmelidir.
    ```csharp
    namespace X
    {
        var m = new MyClass();
        //m. dediğimizde her iki metotta gelecektir.
    partial class MyClass
    {
        public void A()
        {
            
        }
    }
    partial class MyClass
    {
        public void B()
        {
            
        }
    }
    partial class MyClass
    {
        public void C()
        {
            
        }
    }
    }
    ```

  * İç içe partial türler kullanılabilir.(Nested)

    ```csharp
    namespace X
    {
        partial class MyClass
        {
            partial class MyClass2
            {
                
            }
        }
        partial class MyClass
        {
            partial class MyClass2
            {
                
            }
        }
    }
    ```

  * Tüm partial yapılar aynı namespace altında bulunmalıdır. Farklı projeler yahut modüllere yayılamaz!

  * partial olan bir yapının tüm parçalarının türleri ve isimleri aynı olmak zorundadır.

  

### Partial Olabilen Yapılar

> Partial olarak neler tasarlanabilir?
>
> - class
> - record
> - struct
> - abstract class
> - interface

```csharp
partial record X
{
    
}
partial record X
{
    
}
```

```csharp
//abstract class'larda partial kullanılırken işaretin class'tan önce olması gerekmektedir. Semantik açıdan bu şekilde geliştirilmiştir.
//partial abstract class şeklindeki tanımlama da compiler hata verecektir.
abstract partial class MyClass
{
    
}
abstract partial class MyClass
{
    
}
```

```csharp
partial struct c
{
    
}
partial struct c
{
    
}
partial struct c
{
    
}
```

```csharp
partial interface IInterface
{
    
}
partial interface IInterface
{
    
}
```



### Partial Metotlar Nelerdir?

* partial yapılar, partial metotlar barındırabilirler.

  partial metotlar ne işe yararlar?

  Partial metotlar, sınıfın bir parçasında geliştiricinin metot bildiriminde bulunmasını sağlar. Başka bir parçasında ise diğer geliştirici tarafından bu metot tanımlanabilir. Bunun yararlı olduğu iki senaryo vardır :

  1) Template Code

  - Geliştirilen kodda metotlara dair bir şablon oluşturmak için kullanılabilir.

  - Bu şablonların uygulanıp uygulanmayacağına dair geliştiricinin karar vermesine olanak tanınır.

  - Eğer şablonu tanımlanan metot uygulanmazsa derleyici tarafından metodun imzası ve o metoda dair yapılan tüm çağrılar/tetiklemeler kaldırılır.

    Yani anlayacağınız, partial bir metot tanımlandığı taktirde ister uygulansın ister uygulanmasın herhangi bir farklı noktadan çağırılabilir/tetiklenebilir. Ancak uygulandığı taktirde herhangi bir derleme yahut çalışma zamanı hatası alınmayacaktır.

  ```csharp
  new MyClass();
  partial class MyClass
  {
      public MyClass()
      {
          X();
          Y();
          Z();
      }
      partial void X(); //tanım-declaration/beyanname
      partial void Y(); //tanım-declaration/beyanname
      partial void Z(); //tanım-declaration/beyanname
  
      partial void Y() //gövde-implementation/uygulama
      {
          Console.WriteLine("Y tetiklendi...");
      }
  }
  ```

  2. Source Generator

  - Source generator sistemleri ile sınıflarda tanımlanmış olan partial metot imzalarına karşılık gövdeler oluşturulabilir.

  - Geliştirici, uygulanacak metodun partial bir şekilde şablonunu ekledikten sonra source generator derleme sırasında bu metodun uygulamasını sağlar.

    Tabi geliştirici isterse, bu metotların gövdeleri source generator tarafından üretilmeden önce ya da başka deyişle bu metotlar uygulanmadan önce başka bir noktada çağırılabilir/tetikleyebilir.



### Partial Metot Kuralları

* Partial metotlarla ilgili aşağıdaki ekstra bilgileri bilmekte fayda vardır :

  * partial metotların runtime'da var olacağı kesin değildir. Eğer implementation edilmedilerse partial metotlar derleme sırasında yok sayılırlar.

  * Yukarıdaki durumdan dolayı partial metotlar delegate'ler ile temsil edilemezler.

  * partial metotlar :

    * ancak partial yapılar içerisinde tanımlanabilirler.
    * geri dönüş tipleri her daim void olmak zorundadır.
    * static veya generic olabilirler.
    * out parametresi alamazlar lakin ref parametresi alabilirler.
    * extern ve virtual olamazlar.

  * Aynı class'lar da olduğu gibi partial metodun hem tanımı hem de gövdesi partial ile işaretlenmelidir.

  * Bir metot imzasına karşılık tanım ve gövde olabilir.

  * Eğer ki partial metotlar başka bir metot tarafından çağırılırlarsa compiler tarafından var oldukları bilinecektir,

    yok eğer çağırılmazlarsa compiler derleme aşamasında ilgili metodu hiç görmeyecektir.

  * partial metotlar gövdeleri tanımlanıp public olarak işaretlenebilmektedir. Lakin gövdeleri tanımlanmadıysa imzaları public olarak işaretlenemezler.

