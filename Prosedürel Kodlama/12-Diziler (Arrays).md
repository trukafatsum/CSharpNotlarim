# C# Notları (Diziler)

[TOC]



## Dizi nedir?

> Dizi (Array) : Tek bir değişken altında birden fazla "aynı türde" değeri toplamamızı sağlayan veri kümelerine dizi denmektedir.
>
> ```csharp
> int ogrenci1 = 20;
> int ogrenci2 = 23;
> int ogrenci3 = 25;
> ```
>
> * Diziler içerisinde birden fazla aynı türde değer tutabilen yapılardır.
>
> * Prosedürel programlamanın temel veri kümeleridir. Yani yazılımsal boyutta, yazılım adına RAM'de birden fazla değeri, tek bir değişken altında bir veri kümesi halinde tutabilirler.
>
> * Diziler veri kümeleri oldukları için, içlerindeki birden fazla veri üzerinde kümesel işlemler yapmamızı sağlayabilirler.
>
> * Diziler, prosedürel programlamanın temel yapıları oldukları için daha gelişmiş yapılar olan koleksiyonlarında temelini teşkil etmektedirler ve gelişmelerine katkıda bulunmaktadırlar.
>
> * *Diziler referans türlü değerlerdir. Yani nesnel yapılardır, özlerinde "class"tırlar.*
>
> * Yapısal olarak RAM'de Heap'te tutulurlar.
>
>   > Kritik
>   >
>   > Dizi içerisine her türlü değer koyulabilir. (Değer türlü-Referans türlü)
>   >
>   > Bir dizi sadece tek bir türde değer alabilir.
>   >
>   > Dizi içerisine koyulan değerler işlevsel olarak aynı mahiyette olmalıdır. 
>   >
>   > Örneğin; yas dizisine, maas bilgisi aynı türde olduğu halde verilmemelidir.
>
>   * Diziler içerisine eleman/değer eklendikçe bunları düzenli bir şekilde, sıralı depolayacaktır.
>
>   * Dizilerde eklenen elemanlar index ismini verdiğimiz numaralarla, ardışık bir şekilde numaralandırlırlar.
>
>   Index no : Her bir elemana verilen ardışık sayı, 0'dan başlar n-1'e kadar gider.
>
> > Prototip
> >
> > ```csharp
> > // type a; -->Değişken
> > // type []a -->Dizi
> > 
> > /*
> > [] operatörü : Bir değişken tanımlanırken türünün yanına bu operatörü koyarsak o değişken o türde bir dizi değişkeni olacaktır. Bu operatöre INDEXER ismi verilmektedir.
> > */
> > 
> > type[] name = new type[...]; //Bu dizinin alacağı eleman sayısını [...] buraya bildiriyoruz.
> > ```
> >
> > * Buradaki new keywordu, bir dizi nesnesi oluşturmamızı sağlar,
> >
> >   OOP'de detayları ile inceleyeceğiz.
> >
> > 
>
> 



## Dizi Tanımlama

> Dizi:
> Tek bir değişken altında birden fazla "aynı türde" değeri toplamamızı sağlayan veri kümelerine dizi denmektedir.

```csharp
// Prototip: type[]isim = new type[..adet..];
int[] yaslar = new int[5];
bool[] medeniHal = new bool[7];
byte[] sayilar = new byte[12];
//Dizinin başlangıç türü ile bitiş türü aynı olacak! int[] sayilar2 = new bool[12]; OLAMAZ!
//Dizinin eleman sayısı negatif veya boş olamaz! Eleman sayısını mecburi girilmek zorundadır. Bu durum bir sınırlılıktır.
```

Bir dizi tanımlaması yapıldığı an bellekte o diziyi kullansakta, kullanmasakta verilen eleman sayısı kadar alan tahsisinde bulunulur.

Dizilerde tanımlama yaıldığı an alan tahsisinde bulunması bizim için pekte doğru bir durum değildir.

Kullanılmadığı halde diziler direkt olarak bellekten belirtilen eleman sayısı kadar alan tahsisinde bulunması bir sınırlılıktır.

Alan tahsisi yapıldığında ilgili alanlara türüne uygun default değerleri atarlar ve indexlenirler.



### Tanımlanmış Diziye Değer Atama

> Index numarası:
> Dizilere sistem tarafından otomatik verilen ve kimlik mahiyetinde kullanabileceğimiz bir numaradır.
> Her bir elemana karşılık gelen unique değerlerdir. Haliyle böyle olması demek, her bir elemana istediğimiz zaman erişip,
> değer atama yapabilmemizi veya okuyabilmemizi sağlamaktadır.

Diziye değer atarken hangi indexe karşılık değer koyacaksak, yine indexer operatörüyle bunu bildirmeli ve ilgili değeri atamalıyız.
```csharp
int[] yaslar = new int[7];
yaslar[3] = 25;
yaslar[0] = 5;//Dizilerde değer ataması yaparken sıralamayı göz önünde tutmak zorunda değiliz.
//! yaslar[15] = 123; //Dizilerde değer atama ve okuma işlemlerinde eğer ki dizinin sınırını aşarsak hata verecektir. Olan indexlerden biri olmalıdır.
```

Dizinin içerisindeki elemanlara değer atarken değişken davranışı gösterir. Dolayısıyla herhangi bir elemana atanan en son değer geçerlidir.

> Dizilerde eleman sayısının başta belirlenmesi durumunda, ihtiyaca binaen daha fazla değer atamak istediğimizde bu değerleri atayamayacağımızdan ve dizinin aralığını genişletemeyeceğimizden dolayı bu durum bir sınırlılık olarak karşımıza çıkmaktadır.



### Tanımlanmış Diziden Değer Okuma

Bir dizinin değerini okumak istersek, assign operatörünün sağında veya bir metotun parametresinde çağırılması gerekir.

```csharp
int[] yaslar = new int[7];
yaslar[3] = 25;
yaslar[0] = 5;
Console.WriteLine(yaslar[3]);
Console.WriteLine(yaslar[6]);//Her ne kadar değer vermemiş olsakta, başlangıçta default değer aldığı için 0 sonucunu getirecektir.
```

> Dizilerde değer okurken, değer aralığını aşmamaya özen gösteriniz.



### Tanımlanmış Dizi İçerisinde Döngüyle Dönme

> Bir dizi içerisinde illa ki dönmek zorunda değiliz. Her öğrendiğimiz bilgiyi birbirleriyle ilişkilendirmeliyiz.
>
> Diziler genellikle döngülerle birlikte algoritmalarda kullanılmaktadırlar.

```csharp
string[] personeller = new string[10];
personeller[0] = "Hilmi";
personeller[1] = "Hüseyin";
personeller[2] = "Rıfkı";
personeller[3] = "Şuayip";
personeller[4] = "Muiddin";
personeller[5] = "Naci";
personeller[6] = "Hüsnü";
personeller[7] = "Nurullah";
personeller[8] = "Cabbar";
personeller[9] = "Akif";

//Console.WriteLine(personeller[0]);
//Console.WriteLine(personeller[1]);
//Console.WriteLine(personeller[2]);
//Console.WriteLine(personeller[3]);
//... şeklinde yapmak yerine
for (int i = 0; i < 10; i++)
{
    Console.WriteLine(personeller[i]); //Şeklinde 1'den 10'a kadar değerleri i olarak alıp döngüde gerçekleştirebiliriz.
}
```



#### Kritik 1

```csharp
string[] personeller = new string[7];
personeller[0] = "Hilmi";
personeller[1] = "Hüseyin";
personeller[2] = "Rıfkı";
personeller[3] = "Şuayip";
personeller[4] = "Muiddin";
personeller[5] = "Naci";
personeller[6] = "Hüsnü";

//Dizi içerisinde dönecek olan döngü kombinasyonunda, dizinin eleman sayısı manuel bir şekilde kullanılmamalı, bu sayısal değeri dizinin kendisinden almalıyız.

for (int i = 0; i < personeller.Length; i++)
{
    Console.WriteLine(personeller[i]); //Dizi içerisindeki eleman sayısı değiştikçe artık hepsini getirecektir.
}
```



### Dizilerin Sınırlılıkları ve Koleksiyon Yapılarının Doğuşu

> Sınırlılıklar:
>
> * Dizilerde tanımlama yaparken eleman sayısının bildirilmesi zorunluluğu bir sınırlılıktır.
> * Diziler tanımlandığında kullansakta kullanmasakta bellekte belirtilen eleman sayısı kadar alan tahsisinde bulunurlar. Bu durum bellek boyutunda ekstradan maliyete sebep olacağı için bir sınırlılıktır.
> * Dizilerde eleman sayısının başta belirlenmesi durumunda, ihtiyaca binaen daha fazla değer atamak istediğimizde bu değerleri atayamayacağımız ve dizinin aralığını genişletemeyeceğimizden dolayı bu durum bir sınırlılık olarak karşımıza çıkmaktadır.
> * Tanımlanmış bir dizide elemanlara değer atarken [ ] indexer operatörüyle değer atanması bir sınırlılıktır.

Dizilerle bu incelemiş olduğumuz veri yapısındaki sınırlılıklardan kurtulmak için yavaş yavaş koleksiyonlara yöneleceğiz.

İlk koleksiyonumuz ArrayList olacaktır ve onunda kendine göre sınırlılıkları olacaktır.



### Dizi Tanımlama Varyasyonları

#### Varyasyon 1

```csharp
int[] yaslar = new int[3];
yaslar[2] = 123;
Console.WriteLine(yaslar[2]);
```



#### Varyasyon 2

```csharp
int[] yaslar = {30,25,41,52}; // Burada yapmış olduğumuz işlem:
/*
	int[] yaslar = new yaslar[4]; olarak arka planda ayarlanacaktır.
	yaslar[0] = 30;
	yaslar[1] = 25;
	yaslar[2] = 41;
	yaslar[3] = 52;
*/
```



#### Varyasyon 3

```csharp
string[] isimler = new string[] {"Rıfkı","Şuayip","Hüseyin","Hilmi","Mehmet"}
```



#### Varyasyon 4

```csharp
string[] isimler = new string[3]{"Rıfkı","Şuayip","Hüseyin"};
```



#### Varyasyon 5 (Biraz önemli)

```csharp
// İnternette ve makalelerde genellikle kullanılır.
int[] sayilar = new[]{ 3, 5, 7 };
var sayilar2 = new[] { 3, 5, 7, 9 };
```



## Array Sınıfı

Dizi olarak tanımlanan değişkenler Array sınıfından türetilmektedirler.

Dolayısıyla dizilerde Array sınıfından gelen belirli metotlar ve özellikler mevcuttur.

```csharp
Array yaslar = new int[3];
```



### Bir Dizinin Kendi Türünde Tanımlanmasıyla Array Türünde Tanımlanması Arasındaki Fark Nedir?

Bir dizi kendi türünde tutuluyorsa, indexer operatörü kullanılabilir. Array türünde tutuluyorsa indexer operatörü kullanılamaz!

```csharp
int[] a = new int[5]; //-->Bu şekilde çalışıldığında ilgili diziye verisel müdahaleler operatif gerçekleştirilirken, genellikle bu format algoritmalarda tercih edilir. Çünkü indexer algoritmalarda çok kullanılır.
Array a2 = new int[5]; //-->Bu şekilde ise fonksiyonel çözümler getirilmektedir. Genellikle elimizdeki dizinin üzerinde işlem yaparken tercih edilen formattır. Dizi hakkında bilgi edinirken vs. kullanılır.
```



### Array Türünden Dizilere Değer Atama/Okuma

```csharp
Array dizi = new int[3];
//dizi[0] = 123; -> bu şekilde yapamayız!
```

> Yöntem 1:
> ```csharp
> int[] dizi = new int[3];
> dizi[0] = 30;
> dizi[1] = 31;
> dizi[2] = 32;
> Array dizi2 = dizi;
> ```
>
> Çok pratik değil.

> Yöntem 2:
>
> ```csharp
> Array dizi = new int[4] { 3, 5, 7, 9};
> Array dizi = new int[] { 3, 5, 7, 9};
> Array dizi = new[] { 3, 5, 7, 9};
> //Array dizi = { 3, 5, 7, 9}; //KULLANILAMAZ!
> ```

> Yöntem 3:
>
> ```csharp
> Array dizi = new int[3];
> dizi.SetValue(30,0); //Değer atama bu şekilde
> dizi.SetValue(31,1);
> dizi.SetValue(32,2);
> object value = dizi.GetValue(1); //Değer okuma bu şekilde yapılır. Object türünde geriye değer döner.
> Console.WriteLine(value);
> ```



### Metotlar

#### Clear

```csharp
//Dizi içerisindeki tüm elemanları siliyor diye bilinir. Halbuki bu yanlıştır. Dizi içerisindeki tüm elemanlara, dizinin türüne uygun default değerleri atayan bir fonksiyondur.
Array isimler = new[] {"Hilmi","Hüseyin","Şuayip","Rıfkı","Hamdullah"};
Array.Clear(isimler, 0, isimler.Length); // Parametrelerde (dizi, başlangic_index, defaultAtanacakElemanSayisi)
```



#### Copy

```csharp
//Elimizdeki bir dizinin verilerini bir başka diziye kopyalamamızı sağlayan bir fonksiyondur.
Array isimler = new[] {"Hilmi","Hüseyin","Şuayip","Rıfkı","Hamdullah"};
string[] isimler2 = new string[isimler.Length];
Array.Copy(isimler,isimler2, 5); //Çeşitli overloadları vardır. Kullandığımız overload'da (kopyalanacakDizi, atanacakDizi, dizininElemanSayisi)
for (int i = 0; i < isimler2.Length; i++)
{
    Console.WriteLine(isimler2[i]);
}
```



#### IndexOf

```csharp
//Dizi içerisinde bir elemanın var olup olmadığını sorgulayabildiğimiz fonksiyondur.
//Arama neticesinde ilgili değer varsa int olarak o değerin index numarasını döndürecektir.
//yoksa -1 değerini döndürür.
int index = Array.IndexOf(isimler,"Rıfkı");
if (index != -1)
{
    //Demekki aranan değer ilgili dizide bulunmaktadır.
    Console.WriteLine("Var");
}
```



#### Reverse

```csharp
// Elimizdeki dizinin elemanlarını tersine sıralayan bir fonksiyondur.
Array isimler = new[] {"Hilmi","Hüseyin","Şuayip","Rıfkı","Hamdullah"};
for (int i = 0; i < isimler.Length; i++)
    Console.WriteLine(isimler.GetValue(i));

Array.Reverse(isimler);

Console.WriteLine("****************");
for (int i = 0; i < isimler.Length; i++)
    Console.WriteLine(isimler.GetValue(i));
```



#### Sort

```csharp
// Alfa-numerik bir şekilde A-Z ye sıralama yapar
Array isimler = new[] {"Hilmi","Hüseyin","Şuayip","Rıfkı","Hamdullah"};
Array.Sort(isimler);
```



### Özellikler

#### IsReadOnly

> Readonly: salt-okunur demektir. Yani sadece okunabilir, yazılamaz demektir.

```csharp
// Bir dizinin sadece okunabilir olup olmadığını bool olarak döndüren bir özelliktir.
Array isimler = new[] {"Hilmi","Hüseyin","Şuayip","Rıfkı","Hamdullah"};
Console.WriteLine(isimler.IsReadOnly);
```



#### IsFixedSize

```csharp
// Bir veri kümesinin eleman sayısının sabit olup olmama durumunu IsFixedSize ile öğrenebiliriz.
Array isimler = new[] {"Hilmi","Hüseyin","Şuayip","Rıfkı","Hamdullah"};
Console.WriteLine(isimler.IsFixedSize);
//Tüm dizilerde eleman sayısı sabit olduğu için sürekli true dönecektir. Örneğin ArrayList koleksiyonunda false dönmektedir.
```



#### Length

```csharp
//Dizinin eleman sayısını döndüren özelliktir.
Array isimler = new[] {"Hilmi","Hüseyin","Şuayip","Rıfkı","Hamdullah"};
Console.WriteLine(isimler.Length);
```



#### Rank

```csharp
//İlgili dizinin derecesini bize getirir. 
int[,,] sayilar = new [10,11,6]; // İlerleyen derslerde göreceğimiz çok boyutlu bir dizidir.
Console.WriteLine(sayilar.Rank); //Rank ile bize derecesinin 3 olduğunu getirecektir. [,,]
```



#### CreateInstance Metodu ile Dizi Tanımlama

```csharp
//Array sınıfının sonuncu ve belki en önemli olabilecek metodudur.
//Bu metot üzerinden biz, programatik olarak dizi tanımlayabiliyoruz.
int[] yaslar = new int[3];
//Normalde yukarıdaki gibi yapılan dizi tanımlaması esasında arkaplanda Array sınıfının CreateInstance metodunu kullanmaktadır. Bizlerde bu metodu kullanarak fonksiyonel diziler oluşturabilmekteyiz.
Array yaslar2 = Array.CreateInstance(typeof(int),3); //Int türünde 3 elemanlı dizi tanımlamış olduk.
```



#### CreateInstance Metodu ile Çok Boyutlu Dizi Tanımlama

```csharp
Array yaslar = Array.CreateInstance(typeof(int),5,3,5,6);
Console.WriteLine(yaslar.Rank);
```



### Ranges and Indices C# 8.0

C# 8.0 bizlere:

- System.Index

- System.Range

  '..' operatörü

  '^' operatörü
  kazandırmıştır.

C# 8.0 ile veri kaynakları üzerinde gerekli manipülasyonu sağlayabilmek ve bunun yanında kaynak içerisindeki tüm veriler
üzerinde yapılan genel sorgulamalar ve algoritmalardan kaçınmak, yani direkt olarak hedef veri/ler odaklı çalışabilmek için
yeni tipler ile operatörler geliştirilmiş bulunmaktadır.



#### System.Index

* Dizi ve koleksiyon yapılarındaki index kavramının tip olarak belirlenmiş halidir.

* Temelde index değerini bir tür ile tutmakla beraber ^ operatörüyle birlikte daha fazla anlam ifade etmekte ve dizinin
  index değerlerini tersine ifade edecek şekilde bir sorumluluk yüklenmektedir.

  ```csharp
  Index i = 3; // İfadesi 0 1 2 3 deki 3 değerini ifade ederken;
  Index i = ^3; // ise 3 2 1 tersinden(sağdan başlar) alıp 3.elemanı ifade edecektir.
  //Index 0'dan başlayıp n-1'e doğru ele alınırken,
  //^ (tersine) operatörü ile tersine aldığımızda 1'den başlar n'e doğru.
  //^ operatörü ile tersine index durumları kullanılırken, index değerinin 0'dan değil 1'den başladığına dikkat ediniz.
  ```

  > Indexer[ ] operatörü içerisine tam sayı verilebildiği gibi Index türüde verilebilir.

  

##### İnceleme

```csharp
int[] sayilar = { 3, 5, 7, 9, 1, 2, 31, 321, 534, 5643, 457, 56, 78};
//Index index = 5; --> Soldan 0 - (n-1)
Index index = ^8; //--> Sağdan n - 1
Console.WriteLine(sayilar[index]);
```

> ^ operatörü Index sınıfına özel bir operatördür.



#### System.Range

* Veri kümelerinde hangi değerler ile çalışacağımızı belirleyebilmek için index üzerinden aralık vermemizi ve bunu '..' operatörü ile gerçekleştirmemizi sağlayan yapılanmadır.

* Yani ilgili dizide hangi değer aralığında çalışacağımızı '..' operatörü ile sağlamaktadır.

  <img src=https://i.imgur.com/2EvgbYY.png width=75% align=left />

> .. operatörü hedeflenen aralığı bizlere Range türünde geri getirecektir. Böylece biz ilgili aralığı diziymiş gibi kullanabileceğiz.

* .. operatörünün solundaki değer index değerini, sağındaki değer ise sıra numarasını ifade etmektedir. Index 0'dan, sıra numarası 1'den başlar.

<img src=https://i.imgur.com/cssjdpT.png width=75% align=left />

<img src=https://i.imgur.com/XaKzt9R.png width=75% align=left />

> Indexer[ ] operatörü içerisine tam sayı veya Index türü verilebildiği gibi Range türüde verilebilir.



##### İnceleme 1

```csharp
//Örneğin 2 ile 5643 arasında çalışmak istiyorsak,
int[] sayilar = { 3, 5, 7, 9, 1, 2, 31, 321, 534, 5643, 457, 56, 78};
Range range = 5..10; //Herhangi bir dizide kullanabileceğimiz [2, 31, 321, 534, 5643] değerlerini alır
var sayilar2 = sayilar[range];//İlgili aralığı yeni bir dizi olarak getirir.

//Range range = ..; --> Tüm diziye karşılık gelir.
```



##### İnceleme 2

```csharp
//Örneğin 2 ile 5643 arasında çalışmak istiyorsak ve tersine yapmak istiyorsak,
int[] sayilar = { 3, 5, 7, 9, 1, 2, 31, 321, 534, 5643, 457, 56, 78};
Range range = 5..^3; // [2, 31, 321, 534, 5643] değerlerini alır. Sıra numarasını tersine alır.
//Range range = ^8..^3; // [2, 31, 321, 534, 5643] değerlerini alır. Sıra numarasını ve indexi tersine alır.
var sayilar2 = sayilar[range];
```



#### .. Operatörü

* Veri kümelerinde belirli bir aralığı temsil eden operatördür.

* Aralık operatörü diyede isimlendirilebilir.

* Index..Index

  .. operatörü sağına ve soluna sayısal bir değer alabildiği gibi özü itibariyle System.Index türünden de değerler alabilir.

  Geriye System.Range türünden yapı döndürür.

  

##### İnceleme

```csharp
int[] sayilar = { 3, 5, 7, 9, 1, 2, 31, 321, 534, 5643, 457, 56, 78};
Index i1 = 5, i2 = 10;
Range range = i1..i2;
var sayilar2 = sayilar[range]; //[2, 31, 321, 534, 5643] değerlerini alacaktır.
```



#### ^ Operatörü

* Veri kümelerinde index değerinin tersini ifade eder.

* Normal index yapılanmasına nazaran ters index durumu 0'dan değil 1'den başlamaktadır.

  * Genellikle bir dizinin son elemanına erişmek için kullandığımız karışık manevrasal algoritmalardan bizleri kurtarmaktadır.

    ```csharp
    //string isim = isimler[isimler.Length-1];
    string isim = isimler[^1];
    ```

    

##### İnceleme

```csharp
int[] sayilar = { 3, 5, 7, 9, 1, 2, 31, 321, 534, 5643, 457, 56, 78};
//int i = ^3; --> ^ bu operatörü kullanabilmek için index türünde çalışılması gerekmektedir. Çünkü geriye Index türünde değer döndürür.

//Index i = ^3;
//Console.WriteLine(sayilar[i]); --> 457 sonucunu ekrana yazdırır

Range range = ^7..^3; //[31, 321, 534, 5643, 457, 56, 78] değerlerini alacaktır.
```



## Çok Boyutlu Diziler

> Çok boyutlu diziler oyun programlamada yahut yüksek istatistiksel çalışmalarda kullanılan bir yapıdır.



### Çok Boyutlu Dizi Tanımlama

type[ ] -> Tek boyutlu dizi tanımlaması

type[ , ] -> İki boyutlu dizi tanımlaması (Çift)

type[ , , , ,] -> 4 boyutlu dizi tanımlaması

* Çok boyutlu dizilerde indexer içerisinde virgül(,) ile tanımlama yapılmaktadır.

  Virgül sayısının +1 fazlası dizinin derecesini verecektir.

```csharp
int[] sayilar = new int[3]; // Tek boyutlu dizi tanımlaması
int[,] sayilar2 = new int[3,5] // Çift/İki boyutlu dizi tanımlaması;
//İki boyutlu diziler x ve y koordinatlarıyla tahayyul edebileceğimiz dizilerdir.
int[,,,] sayilar3 = new int[3,4,5,6] //İki dereceliden fazla olan dizileri günlük hayatta tahayyul etmek pek mümkün olmasada programatik olarak inşa edebilmekteyiz.
```



### Tanımlanmış Çok Boyutlu Diziye Değer Atama

* İki dereceli dizide değer atama
  ```csharp
  int[,] sayilar = new int[3,4];
  ```

  <img src=https://i.imgur.com/kjgpR7E.png width=25% align=left />

  Oluşacak olan dizimiz x ve y düzleminde bu şekildedir. Bunlara değer gönderirken ilgili indexlerle değer göndereceğiz.

  ```csharp
  sayilar[1,2] = 5;
  sayilar[2,0] = 15;
  ```

* Üç dereceli dizide değer atama

  ```csharp
  int[,,] sayilar = new int(2,3,4);
  sayilar[0,0,0] = 15;
  sayilar[0,0,1] = 16;
  sayilar[0,0,2] = 17;
  ```

  

### Çok Boyutlu Dizilerde Değer Atama Farklı Varyasyonu

```csharp
//Diyelim ki 2 dereceli bir sayımız olsun
int[,] sayilar = {
    {3, 5, 7}, 
    {5, 6, 7}, 
    {15, 36, 57}, 
    {25, 46, 67} 
};
```

<img src=https://i.imgur.com/fU3alrP.png width=25% align=left />



### Çok Boyutlu Dizilerden Değer  Okuma

> Dizilerde değer atamada gördüğümüz gibi, okuma işlemi de aynı şekilde indexler üzerinden belirtilir.
>
> ```csharp
> int[,] sayilar = new int[3,4];
> sayilar[0,0] = 3;
> sayilar[0,1] = 5;
> sayilar[0,2] = 7;
> sayilar[1,0] = 5;
> sayilar[1,1] = 6;
> sayilar[1,2] = 7;
> sayilar[3,2] = 67;
> Console.WriteLine(sayilar[3,2]);
> ```
>
> <img src=https://i.imgur.com/kjgpR7E.png width=25% align=left />



### Çok Boyutlu Dizilerin Eleman Sayısını Hesaplama

> Çok boyutlu dizilerde eleman sayısını bize 'Length' özelliği getirecektir.

```csharp
int[,,] sayilar = new int[2,2,4]; // Total hücre sayısını hesaplamak için tüm elemanları çarpmamız yeterlidir.
sayilar[0,0,0] = 1;
sayilar[0,0,1] = 2;
sayilar[0,0,2] = 3;
sayilar[0,0,3] = 4;
sayilar[0,1,0] = 5;
sayilar[0,1,1] = 6;
sayilar[0,1,2] = 7;
sayilar[1,0,0] = 9;
sayilar[1,0,1] = 10;
sayilar[1,0,2] = 11;
sayilar[1,0,3] = 12;
sayilar[1,1,0] = 13;
sayilar[1,1,1] = 14;
sayilar[1,1,2] = 15;
sayilar[1,1,3] = 16;
Console.WriteLine(sayilar.Length);
```



### Çok Boyutlu Dizilerin Belirli Bir Derecesinin Eleman Sayısını Hesaplama

> Eğer ki dizinin belirli bir derecesinin eleman sayısını hesaplamak isterseniz, bunu 'GetLength()' özelliğini kullanarak yapmanız gerekir.

```csharp
int[,,] sayilar = new int[2,2,4]; // Total hücre sayısını hesaplamak için tüm elemanları çarpmamız yeterlidir.
sayilar[0,0,0] = 1;
sayilar[0,0,1] = 2;
sayilar[0,0,2] = 3;
sayilar[0,0,3] = 4;
sayilar[0,1,0] = 5;
sayilar[0,1,1] = 6;
sayilar[0,1,2] = 7;
sayilar[1,0,0] = 9;
sayilar[1,0,1] = 10;
sayilar[1,0,2] = 11;
sayilar[1,0,3] = 12;
sayilar[1,1,0] = 13;
sayilar[1,1,1] = 14;
sayilar[1,1,2] = 15;
sayilar[1,1,3] = 16;
Console.WriteLine(sayilar.GetLength(0));
Console.WriteLine(sayilar.GetLength(1));
Console.WriteLine(sayilar.GetLength(2));
```



### Çok Boyutlu Dizilerdeki Verileri İç İçe Döngülerle Ekrana Yazdırma

> Kaç boyutluysa, o kadar iç içe for döngüsü tanımlamamız gerekiyor.

```csharp
int[,,] sayilar = new int[2,2,4];
sayilar[0,0,0] = 1;
sayilar[0,0,1] = 2;
sayilar[0,0,2] = 3;
sayilar[0,0,3] = 4;
sayilar[0,1,0] = 5;
sayilar[0,1,1] = 6;
sayilar[0,1,2] = 7;
sayilar[1,0,0] = 9;
sayilar[1,0,1] = 10;
sayilar[1,0,2] = 11;
sayilar[1,0,3] = 12;
sayilar[1,1,0] = 13;
sayilar[1,1,1] = 14;
sayilar[1,1,2] = 15;
sayilar[1,1,3] = 16;

for (int i = 0; i < sayilar.GetLength(0); i++)
{
    for (int j = 0; j < sayilar.GetLength(1); i++)
    {
        for (int h = 0; h < sayilar.GetLength(2); i++)
        {
            Console.Write(sayilar[i,j,h] + "        ");
            Console.WriteLine("");
        }
    }
}
```



## Düzensiz Diziler

> Düzensiz diziler, dizi dizileri veya dizi içerisinde dizi olarak da isimlendirilmektedirler.
>
> Bir dizi her bir hücresinde ayrı bir diziyi ele alıyorsa, biz buna düzensiz diziler demekteyiz.

```csharp
//Düzensiz diziler; her bir elemanı kendi içerisinde farklı bir dizi barındıran dizilerdir.
//Çok boyutlu dizilerden tek farkı, çok boyutlu dizilerin sütun sayılarının sabit; düzensiz dizilerin sütun sayısının değişken olmasıdır.
```



### Düzensiz Dizi Tanımlama

> Dizi tanımlama :
>
> ```csharp 
> type[] 'diyerek type türünde bir dizi tanımlayabildiğimizi biliyoruz.
> ```
>
> Düzensiz dizi tanımlama :
> ```csharp
> type[][] 'diyerek de type türünde bir type dizisi tanımladığımızı belirtiyoruz.
> ```
>
> ```csharp
> int[][] sayilar = new int[3][];
> sayilar[0] = new int[3]{ 3, 5, 7};
> sayilar[1] = new int[5]{ 3, 5, 7, 523, 81};
> sayilar[2] = new int[10]{ 3, 5, 7, 234, 254, 23, 4, 234, 234, 123};
> ```



### Değer Atama/Değer Okuma

> Bir önceki başlıkta değer atamayı gördük, dolayısıyla değer okuma üzerine devam edelim.

```csharp
int[][] sayilar = new int[3][];
sayilar[0] = new int[3]{ 3, 5, 7};
sayilar[1] = new int[5]{ 3, 5, 7, 523, 81};
sayilar[2] = new int[10]{ 3, 5, 7, 234, 254, 23, 4, 234, 234, 123};

Console.WriteLine(sayilar[0][0]);
sayilar[0][0] = 13;
Console.WriteLine(sayilar[0][0]);
```



### Eleman Sayısını Öğrenme

```csharp
int[][] sayilar = new int[3][];
sayilar[0] = new int[3]{ 3, 5, 7};
sayilar[1] = new int[5]{ 3, 5, 7, 523, 81};
sayilar[2] = new int[10]{ 3, 5, 7, 234, 254, 23, 4, 234, 234, 123};
Console.WriteLine(sayilar.Length); //Düzensiz dizinin eleman sayısını(3) getirir. Bu bize total eleman sayısını vermez. Çok boyutlu dizilerde olduğu gibi düzensiz diziler başlı başına farklı bir dizi yapısı değildir. Normal dizi yapılanmasıdır. Lakin içerisinde dizi barındıran bir dizidir. Haliyle eleman sayısını döndürür.

//İçteki dizilerin eleman sayılarını totalde elde edebilmek için herbirini toplamamız gerekmektedir.
Console.WriteLine(sayilar[0].Length + sayilar[1].Length + sayilar[2].Length);
```



### Düzensiz Dizilerde İç İçe Döngülerle Çalışma

```csharp
int[][] sayilar = new int[3][];
sayilar[0] = new int[3]{ 3, 5, 7};
sayilar[1] = new int[5]{ 3, 5, 7, 523, 81};
sayilar[2] = new int[10]{ 3, 5, 7, 234, 254, 23, 4, 234, 234, 123};

for (int i = 0; i < sayilar.Length; i++)
{
    for (int j = 0; j < sayilar[i].Length; j++)
    {
        Console.Write(sayilar[i][j]+ "       ");
        Console.WriteLine("");
    }
}
```

> Çok boyutlu dizilerde boyuta göre hareket ederken, düzensiz dizilerde ana diziye göre hareket eder ve altındaki hücrelerin her biri bir değermiş gibi değerlendirir o şekilde operasyon yaparız.
