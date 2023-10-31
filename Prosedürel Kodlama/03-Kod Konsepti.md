# C# Notları (Kod Konsepti)

[TOC]



## Kod Nasıl Çalışır?

> Kodun, Senkron ve Asenkron olarak 2 türlü çalışma yöntemi vardır.

> Senkron: T zamanda bir işlem gerçekleşebilir, işlem bitmeden diğer işleme geçmez.
>
> Asenkron: T zamanda birden fazla işlem aynı anda gerçekleşebilir.

<img src = "https://imgur.com/kOWvDkC.png" align=left>

> Örnek vermek gerekirse, bilgisayarda hem oyun oynarken aynı zamanda müzik dinleyebilmemiz asenkron çalışma yöntemidir.

## Kod Konsepti Nasıldır?

> Bütün kod konseptlerini gösteremeyiz. Temelde nasıl olduğuna bir bakalım.
>
> <img src="https://imgur.com/ROV1yRv.png" align=left>
>
> Genel olarak sol tarafta bir (tür,değişken,referans..) karşılayıcı birşey olacak, sağ tarafta ise işlem yapıp değer döndüren bir kod olacak;
> ya da sağ tarafta kodumuz herhangi bir işlem yapacak ama bir değer döndürmeyecekse olduğu gibi bırakacağız, herhangi bir yere assign etmeyeceğiz.
>
> 



## Noktalı virgül ';' Operatörü

> C# programlama dilinde kodun konseptinin bittiğini ifade eder.
>
> ```csharp
> int a = 5;
> int a = 5.ToString().Split.....;
> ```
>
> * ; kod konseptinin sona erdiğini ifade eder.
>
> * Bir kod konsepti sona erdiğinde ; kullanılmak zorundadır. Aksi taktirde compiler hata verecektir.
>
> * Noktalı virgül bir konseptin sonunda istenildiği kadar kullanılabilir.
>
>   ```csharp
>   int a = 123;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
>   ```
>
>   Daha temiz bir kod görüntüsü olması açısından 1 kere kullanmak daha faydalı olacaktır.
>   
>   



## Satır Satır Kod Mantığı Yoktur!

> Genellikle düşünürken yanlışa sürükleyen Line To Line yani satır satır kod konseptinin aslında bir yanlış olduğunu göreceğiz.
>
> ```csharp
> namespace LineToLine
> {
>  class Program
>  {
>      static void Main(string[] args)
>      {
>          int a = 5;
> 			string b = "Mustafa";
>      }
>  }
> }
> ```
>
> > Bilgisayar bilimlerinde bunun bir yeri olabilir ama bizim temasta bulunduğumuz kod yüzeyinde böyle bir kural yok.
>
> Compiler kodu derlerken satır satır değil, konsept konsept derler.
>
> Eğer ki satır satır okuyor olsaydı biz bu kodu şu şekilde yazamazdık;
>
> ```csharp
> namespace LineToLine{class Program{static void Main(string[] args){int a = 5;string b = "Mustafa";}}}
> ```
>
> ```csharp
> namespace LineToLine
> {
>     class Program
>     {
>         static void Main(string[] args)
>         {
>             int a = 5;
> 			string b = "Mustafa";
>         }
>     }
> }
> ```
>
> Bizim böyle yazabilmemizin sebebi yazdığımız kodu daha rahat okuyabilmek, hızlı bir şekilde koda adapte olabilmek. Yani okunabilir kod inşa etmek.
>
> Belki Bilgisayar Bilimleri seviyesinde satır satır kod diye bir kavram olabilir ancak bizim seviyemizde böyle bir mantıkta düşünmeyeceğiz.
>
> Eğer ki satır satır kod diye birşey olsaydı şunu da yazamazdık;
>
> ```csharp
> namespace LineToLine
> {
>     class Program
>     {
>         static void Main(string[] args)
>         {
>             int
>                 a
>                 =
>                 5
>                 ;
> 			string 
>                 b
>                 =
>                 "Mustafa"
>                 ;
>         }
>     }
> }
> ```
>
> 

