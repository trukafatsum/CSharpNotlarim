# C# Notları (Regular Expressions- Düzenli İfadeler)

[TOC]



## Regular Expressions (Düzenli İfadeler) Nedir?

Metinsel yapılanmalarda belirli koşulları sağlayabilen ifadelerdir.

Metinsel ifade içerisinde ihtiyaca istinaden düzenlenirler.

> Örnek
>
> Bir metinsel ifade içerisinde **@** karakteri geçen bütün aralıkları elde etmek istediğimizi varsayalım.
>
> basefqfq**@**awdqopfq21429asd**@**353rqrfeqfq
>
> - Dikkat ederseniz bu değerlerdeki karakterlerin uzunluğu ve ne olduğu önemli değil. Yeter ki @ karakteri olsun.
>
>   Peki bu aralıkları nasıl elde edeceğiz?
>
> - @ karakteri geçen tüm aralıkları elde etmenin çeşitli yolları olabilir.
> - Ancak şartlar arttıkça işlemi koda dökmek zorlaşacaktır.
>
> Misal
>
> - Milyonlarca email adresi olduğunu düşünelim.
>
> - Biliyoruz ki tek bir email formatı vardır. (.....@......'.'com/org/net/)
>
>   Her email adresi mutlaka @ ve ardından .(nokta) karakteri barındırır. Eğer birden fazla nokta varsa noktalardan biri mutlaka @ karakterinden sonra olmalıdır.
>
>   mustafa.kurt**@**sebepsizbosyereayrilacaksan**.**com
>   Haliyle bir karakter dizisinin email adresi olup olmadığını test etmek oldukça zor olacaktır.

### Regex

* Bu yüzden C#'ta bu tür düzenli ifadeleri temsil edebilmek için Regular Expressions operatörleri geliştirilmiştir.
* Bu operatörler eşliğinde elde edilen verinin tasarlanan metinsel düzene uyup uymadığı değerlendirilebilmektedir.
* Regular ifadeler System.Text.RegularExpressions namespace'i altındaki Regex sınıfı tarafından temsil edilmektedir.
* Regular Expressions'lar ufak tefek farklılıklar olsa dahi hemen hemen tüm programlama dillerinde olan evrensel yapılanmalardır.

Düzenli ifadeler başlı başına bir konudur.

Ya hayat kurtarırlar, ya da ömür törpülerler..



## Regular Expressions Operatörleri 

### ^ Operatörü

> ^ Operatörü : Satır başının istenilen ifade ile başlamasını sağlayan bir operatördür.

```csharp
// ^ Operatörü
// ^9 : 9asdasdasdj, 91231231, 9''!!12312 ; aqweqwr, 123, 1239, 091231241
string text = "9123151akqofkq"
Regex regex = new Regex("^9");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### \ Operatörü

> \ Operatörü : Belirli karakter gruplarını içermesini istiyorsak kullanırız.
>
> * \D : Metinsel değerin ilgili yerinde rakam olmayan tek bir karakterin bulunması gerektiği belirtilir.
> * \d  : Metinsel değerin ilgili yerinde 0-9 arasında tek bir sayı olacağı ifade edilir.
>
> * \W : Metinsel değerin ilgili yerinde alfanumerik olmayan karakterin olması gerektiği belirtilir. Alfanumerik karakterler : a-z A-Z 0-9
> * \w : Metinsel değerin ilgili yerinde alfanumerik olan karakterin olacağı ifade edilir.
>
> * \S : Metinsel değerin ilgili yerinde boşluk karakterleri(tab/space) dışında herhangi bir karakterin olamayacağı belirtilir.
> * \s : Metinsel değerin ilgili yerinde boşluk karakterinin olacağı ifade edilir.

 ```csharp
 //Örnek
 // 9 ile başlayan, ikinci karakteri herhangi bir sayı olan ve üçüncü karakteri de boşluk olmayan bir düzenli ifade oluşturalım.
 // ^9\d\S
 string text = "921312315asdasdqwdqwd";
 Regex regex = new Regex(@"^9\d\S");
 Match match = regex.Match(text);
 
 Console.WriteLine(match.Success);
 ```



### '+' Operatörü

> '+' Operatörü : Belirtilen gruptaki karakterlerden bir ya da daha fazlasının olmasını istiyorsak kullanılan operatördür.

```csharp
//Örnek
// 9 ile başlayan, arada herhangi bir sayı olan ve son karakteri de boşluk olmayan bir düzenli ifade oluşturalım.
// ^9\d+\S
string text = "9879789d";
Regex regex = new Regex(@"^9\d+\S");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### | (veya) Operatörü

> | (veya) Operatörü : Birden fazla karakter grubundan bir ya da birkaçının ilgili yerde olabileceğini belirtmek istiyorsak mantıksal veya operatörü kullanılır.

```csharp
//Örnek
// Baş harfi a ya da b yada c olan metinsel ifadeyi girelim.
string text = "ahmet";
Regex regex = new Regex(@"a|b|c");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### {n} Operatörü

> {n} Operatörü : Sabit sayıda karakterin olması isteniyorsa {adet} şeklinde belirtilmelidir.

```csharp
//Örnek
// 555-999999 formatında..
// \d\d\d-\d\d\d\d\d\d
// \d{3}-\d{6}
string text = "555-999999";
Regex regex = new Regex(@"\d{3}-\d{6}");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### ? Operatörü

> ? Operatörü : Bu karakterin önüne gelen karakter en fazla bir en az sıfır defa olabilmektedir.

```csharp
//Örnek
// \d{3}B?A --> 234BA, 543BA, 543A, 123BBA
string text = "123BBA";
Regex regex = new Regex(@"\d{3}B?A");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### . (nokta) Operatörü

> .(nokta) Operatörü : Kullanıldığı yerde \n karakteri dışında herhangi bir karakter bulunabilir.

```csharp
//Örnek
// \d{3}.A
string text = "123'A";
Regex regex = new Regex(@"\d{3}.A");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### \b-\B Operatörleri

```csharp
// \B : Bu ifade ile kelimenin başında ya da sonunda olmaması gereken karakterleri bildirilir.
// \b : Bu ifade ile ilgili kelimenin belirtilen karakter dizisi ile sonlanmasını sağlar.

//Örnek
// \d{3}dır\B => 123dır, dır123, 123dır2
string text = "123dır2";
Regex regex = new Regex(@"\d{3}dır\B");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### [n] Operatörü

> [n] Operatörü : Karakter aralığı belirtilebilir.
>
> Ayrıca özel karakterlerin yerinde yazılmasınıda ifade eder.

```csharp
//Örnek
// \d{3}[A-E]
string text = "123F";
Regex regex = new Regex(@"\d{3}[A-E]");
Match match = regex.Match(text);

Console.WriteLine(match.Success);

//Örnek2
//(507) 751 45 92
//[(]\d{3}[)]\s\d{3}\s\d{2}\s\d{2}

string text2 = "(555) 555 55 55";
Regex regex = new Regex(@"[(]\d{3}[)]\s\d{3}\s\d{2}\s\d{2}");
Match match = regex.Match(text);

Console.WriteLine(match.Success);
```



### Match Sınıfı Özellikleri

```csharp
string text2 = "(555) 555 55 55";
Regex regex = new Regex(@"[(]\d{3}[)]\s\d{3}\s\d{2}\s\d{2}");
Match match = regex.Match(text);

Console.WriteLine($"Success : {match.Success}");
Console.WriteLine($"Value : {match.Value}");
Console.WriteLine($"Index : {match.Index}");
Console.WriteLine($"Length : {match.Length}");
```

* Success : İlgili metinsel ifade pattern'a uyuyorsa bize bool sonuç döndürür.
* Value : Doğrulamanın yapıldığı kısmı geri döndürür.
* Index : Doğrulamanın hangi index numarasında başladığını bize getirir.
* Length : Doğrulamanın yapıldığı karakter uzunluğunu bize döndürür.

