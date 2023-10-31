# C# Notları(Konseptli Konseptsiz Keywordler)

[TOC]



## Keyword Nedir? Operatörden Farkı Nedir?

> Keyword : Programlama dilinin en atomik parçalarıdır.
>
> Derleyici için ön tanımlı olan, nerede hangi amaca hizmet edeceği belli ve kod içerisinde hangi noktalarda çağırılabileceği/kullanılabileceği kurallarla sınırlandırılmış olan anahtar sözcüklerdir.



> Keywordlerin operatörlerle ne farkı vardır?
>
> Operatörler esas olarak belirli bir operasyonu/eylemi üstlenen yapılardır.
>
> Keywordler daha geniş kavramdırlar.
>
> Operatörler esasında bir keyworddur lakin her keyword bir operatör değildir.
>
> 



## Konseptli Keywordler Genel Bakış

> Konspetli keywordler : Yapısal olarak tek başına kullanılmayan, bir bütün olarak konspete bağlı olan keywordlerdir.
>
> Örneğin namespace keywordu
>
> ```csharp
> namespace
> ```
>
> Tek başına kullanıldığında bir anlam ifade etmeyen keywordlerdir.
>
> Ancak namespace'yi bir isim vererek scope açarak kullandığımız taktirde, bir anlam ifade edecektir, derleyici açısından konsepte uygun bir şekilde yorumlanacaktır.
>
> ```csharp
> namespace keywords
> {
>     
> }
> ```
>
> Bu kapsamda ele alabileceğimiz diğer keywordlerden bir kısmı;
>
> * namespace
> * class
> * for
> * while
> * do while
> * switch
> * if
> * try-catch
> * değişken türleri
> * ...
>
> > **Dikkat **: Konseptli keywordlerde dikkat edilmesi gereken, konspete hakim olmamız gerektiğidir.
> >
> > Bir keywordun konseptine hakim olabilmek için de editörün bize sağlamış olduğu kolaylıklardan uzaklaşmamız (tab-tab gibi), Gençay Yıldız hocamızın tavsiyesidir.
>
> 



## Konseptsiz Keywordler Genel Bakış

> Konseptsiz Keywordler : Herhangi bir bütüne, konspete ihtiyaç duymaksızın, tek başına anlam ifade eden keywordlerdir.
>
> Bunlar daha azınlıkta olsa da belirli noktalarda kullanılan keywordlerdir.
>
> Örneğin;
>
> ```csharp
> return;
> break;
> continue;
> goto;
> //...
> ```
>
> 

