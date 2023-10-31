# C# Notları (Dizilerde Verisel Performans)

[TOC]



## Dizilerde Verisel Performans

### Dizilerde Verisel Açıdan Performans Nedir?

Bir referans tarafından işaretlenmiş herhangi bir diziyi düşünelim.

```csharp
int[] sayilar = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };
```

Bu dizi tanımlandığında RAM'de aşağıdaki gibi bir alan tahsisinde bulunacaktır.

<img src= https://i.imgur.com/rl3JJmS.png width=60% align=left />

Bu dizinin belli bir değer aralığında çalışmak istersek Ranges and Indeces özelliği kullanılabilir ve istediğimiz aralığı elde edebiliriz.

Bunu yaptığımızı varsayarsak:

```csharp
int [ ] sayilar = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };

int [ ] sayilar2 = sayilar[2..5];
```

<img src= https://i.imgur.com/IqB3Gku.png width=60% align=left />

Böyle bir durumda aklımıza şu soru gelmektedir:

Zaten var olan dizinin dışında neden başka dizi tanımlandı, bu ekstradan maliyet değil mi?

> Esasında diziler üzerinde işlem yapmak oldukça maliyetli olabilmektedir.
>
> Çünkü dizi üzerinde bir alanı temsil etmek, esasında o alandaki verileri yeni bir diziye koyarak tekrar etmek demektir.
>
> Özellikle bu maliyetli durumlar string değerler için fazlasıyla geçerlidir.
>
> Çünkü string değerler için kullanılan string fonksiyonları arkaplanda sürekli yeni diziler oluşturmakta ve yüksek maliyetli olmaktadırlar.

```csharp
string text = "sebepsiz boş yere ayrılacaksan...";
string text2 = text.Substring(2,5);
string text3 = text.Insert(5,"merhaba");
string text4 = text.Remove(2,5);
string text5 = text.Trim();
string text6 = text.ToUpper();
string text7 = text.ToLower();
```

* Hatta string ifadeleri + operatörüyle birleştirmek bile sonuç olarak eldeki string değerleri arttıracağından dolayı muazzam bir bellek israfına yol açmakta ve maliyeti arttırmaktadır. Bundan dolayı string birleştirmeler + operatörüyle tavsiye edilmemektedir.

* İşte, diziler üzerinde yapılan çalışmalarda bu maliyeti ortadan kaldırabilmek ve daha performanslı çalışabilmek için ArraySegment ve StringSegment türleri geliştirilmiştir.
* Bu türler yapısal olarak dizi yahut string ifadelerdeki bir bölümü temsil etmemizi sağlayan ve bütünsel açıdan ilgili veri kümesini parça parça birden fazla referans eşliğinde yönetmemize imkan veren türlerdir.



### Dizilerde Verisel Açıdan Maliyetleri İnceleyelim

```csharp
int[] sayilar = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };
int[] sayilar2 = sayilar[2..7]; //[30, 40, 50, 60, 70] aralığını başka bir diziye atar. Bu bir maliyettir.
sayilar2[0] *= 10;
sayilar2[1] *= 10;
sayilar2[2] *= 10;
sayilar2[3] *= 10;
sayilar2[4] *= 10;
//Bu işlemler neticesinde sayilar2 dizisi üzerinde işlem yaptık, lakin sayilar dizisinde yapmadık. 
//[30, 40, 50, 60, 70] sayilar dizisinde sadece bu alanda çalış, bellekte yeni bir diziye alan tahsisinde bulunma diyebilmek için ArraySegment kullanmamız gerekir.
```



### ArraySegment Türü Nedir?

> ArraySegment : 
> Bir dizinin bütününden ziyade belirli bir kısımna yahut parçasına ihtiyaç dahilinde ilgili diziyi kopyalamak yerine(ki görece olduça maliyetli bir operasyondur) bağımsız bir referans ile erişmemizi ve böylece salt bir şekilde temsil etmemizi sağlayan bir yapıdır.



#### ArraySegment ile Dizinin Belli Bir Aralığını Referans Etme

```csharp
int[] sayilar = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };
ArraySegment<int> segment1 = new ArraySegment<int>(sayilar);//Dizinin tüm elemanlarını temsil eder.
//sayilar dizisini ArraySegment'in segment1 isimli referansıyla da referans etmiş olduk.
//sayilar üzerinde yaptığımız değişikliği nasıl görebiliyorsak, segment1 üzerinde yaptığımız işlemleri de sayilar üzerinde görebileceğiz.
//Çünkü ikiside aynı diziyi temsil eder.
ArraySegment<int> segment2 = new ArraySegment<int>(sayilar, 2, 5); // 2. indexten 5. elemana kadar aralığı referans eder.
```

Deneme yapalım:

```csharp
int[] sayilar = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };
ArraySegment<int> segment1 = new ArraySegment<int>(sayilar);//Dizinin tüm elemanlarını temsil eder.
ArraySegment<int> segment2 = new ArraySegment<int>(sayilar, 2, 5); // 2. indexten 5. elemana kadar aralığı referans eder.
segment1[0] *= 10;
segment2[0] *= 10;
//Neticede sayilar dizisinin değerleri { 100, 20, 300, 40, 50, 60, 70, 80, 90, 100 } olacaktır.
//segment2 üzerinde yapılan değişiklik segment1'de de yapılmış olacaktır çünkü aynı diziyi referans etmektedir.
```



#### ArraySegment Slicing(Dilimleme) Özelliği

> Bir dizi üzerinde birden fazla parçada çalışılacaksa eğer, her bir parçayı ayrı bir ArraySegment olarak tanımlayabiliriz.
>
> Bu tanımlamaların dışında diziyi tek bir ArraySegment ile referans edip ilgili parçaları o segment üzerinden talep edebiliriz.
>
> Yani ilgili diziyi tek bir segment üzerinden daha rahat bir şekilde parçalayabiliriz. Bu durumda bize yazılımsal açıdan efektiflik kazandırmış olacaktır.

```csharp
int[] sayilar = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };
ArraySegment<int> segment = new ArraySegment<int>(sayilar);
ArraySegment<int> segment1 = segment.Slice(0,3);
ArraySegment<int> segment2 = segment.Slice(4,7);
ArraySegment<int> segment3 = segment.Slice(5,10);
```



### StringSegment Türü Nedir?

> StringSegment, ArraySegment' in string değerler nezdindeki bir muadilidir.
>
> Esasında metinsel değerlerdeki birçok analitik operasyonlardan bizleri kurtarmakta ve Substring vs. gibi fonksiyonlar yerine string değerde hedef keesit üzerinde işlem yapmamızı sağlayan bir türdür.



#### StringSegment ile Dizinin Belli Bir Alanını Referans Etmek

```csharp
// StringSegment türünü kullanabilmek için uygulamaya Microsoft.Extensions.Primitive paketinin yüklenmesi gerekmektedir.
string text = "Ölüme gidelim dedin de mazot mu yok dedik";
StringSegment segment = new StringSegment(text);
StringSegment segment1 = new StringSegment(text, 2, 5); // "üme g"
Console.WriteLine(segment1);
```



### StringBuilder Sınıfı Nedir? Ne Amaçla Kullanılır?

> StringBuilder, string birleştirme operasyonlarında + operatörüne nazaran, yüksek maliyeti absorbe edebilmek için arka planda StringSegment algoritmasını kullanan ve bu algoritma ile bizlere ilgili değerleri olabilecek en az maliyetle birleştirip döndüren bir Sınıftır.

 ```csharp
 string isim = "Mustafa";
 string soyisim = "Kurt";
 StringBuilder builder = new StringBuilder();
 builder.Append(isim);
 builder.Append(" ");
 builder.Append(soyisim);
 
 Console.WriteLine(builder.ToString());
 ```



### Span, ReadOnlySpan, Memory ve ReadOnlyMemory Türleri Nedir? Nasıl Kullanılır?



#### Span

* Bellek üzerinde belirli bir alanı temsil ederek işlemler gerçekleştirmemizi sağlayan bir struct'tır.

* Bu belirli alanlardan kasıt tabi ki de ardışıl alan kaplayan Array değerleridir.

* Normal şartlarda
  Array'lerin belleğin HEAP kısmında tutulduğunu biliyoruz.

  Lakin stackalloc keyword'ü sayesinde STACK'te de Array tanımlayabilmekteyiz.

* Span, stack yahut heap farketmeksizin tanımlanmış olan Array'lerin tümünü yahut bir bölümünü
  bizler için refere edebilen ve üzerinde işlem gerçekleştirebildiğimiz kullanışlı bir yapılanmadır.

Span, dizi ve string gibi maliyetli veriler üzerinde yapılacak operasyonlarda performans açısından yüksek getiriyle birlikte maliyeti olabildiğince düşürmekte ve ekstradan değer kopyalamaya gerek kalmaksızın tüm faaliyetleri gerçekleştirmemize olanak sağlamaktadır.



#### ReadOnlySpan 

> Span niteliklerinin tümünü sağlayan bu tür, adı üzerinde sadece okunabilir kılmaktadır.



#### Span ile ArraySegment & StringSegment Farkı Nedir?

* ArraySegment sadece string ve dizilerde temsiliyet yapabiliyorken, Span bellek üzerinde olan herhangi bir yeri temsil edebilir.
* ArraySegment'te referans edilen alana hertürlü müdahale edilebilirken, ReadOnlySpan'da bu verisel operasyonlar engellenebilir ve sadece okunabilir bir davranış sergilenebilir.
* Sadece string yahut array türler ile çalışılacaksa eğer ArraySegment ve StringSegment tavsiye edilir.



#### Memory Türü Nedir?

* Span ref struct olarak tasarlanmış bir struct'tır.
* Dolayısıyla Heap'te allocation(tahsis) edilememe, object, dynamic yahut interface türleri aracılığıyla referans edilememe yahut bir class içerisinde field veya property olarak tanımlanamama gibi kısıtlamaları vardır.
* Memory türü Span'ın bu kısıtlamaların münezzeh versiyonudur.



#### ReadOnlyMemory

> Memory türünün sadece okunabilir halidir.



### Span Türünü Pratikte İnceleyelim

```csharp
int[] sayilar = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };

Span<int> span = new Span<int>(sayilar); //Tam referans örnek 1
Span<int> span2 = sayilar; //Tam referans örnek 2
Span<int> span3 = new Span<int>(sayilar,3,5); // 5.index dahil 3 eleman alır

Span<int> span4 = sayilar.AsSpan(); //Dizi üzerinden hangi spanın döneceğini bildiriyoruz
Span<int> span5 = sayilar.AsSpan(3,5);

string text = "Sen kalbimde batan güneş, ben yollarda çilekeş...";
ReadOnlySpan<char> readOnlySpan = text.asSpan();
ReadOnlySpan<char> span6 = text;
//Metinsel ifadeler üzerinde bir referans söz konusuysa bize readonly olarak döndürecektir.
```

