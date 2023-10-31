# C# Notları (String Tipi Analizi ve String Fonksiyonları)

[TOC]



## String Gerçeği

> string referans türlü olduğu halde programlama dilinde bir keyword barındıran tek değerdir.
> string'in değeri heap'de tutulur.



### Null-Empty Durumları, Farkları

> Null : 
> Bir değişken/nullable/referans eğer ki null alıyorsa bu durum ilgili değişkenin herhangi bir alanı tahsis etmediği anlamına gelir.

> Empty :
> Bir değişken/nullable/referans eğer ki empty ise bu değişkenin değeri yok anlamına gelir.
>
> Lakin alan tahsisinde bulunulmuştur.

* Değer türlü değişkenler null alamazlar!

* Null alabilen türler sadece referans türlerdir.

* Değer türlü değişkenlerin null alabilmesi için nullable(?) olmaları gerekmektedir.

  ```csharp
  int? a = null;
  string b = null;
  ```

* Alan tahsisinde bulunulup ilgili alana değer koymamak empty durumudur.

  Default değerlerin olduğu durumlar empty olarak gerçerler.

  ```csharp
  int a = 0;
  bool b = false;
  int = new int[55];
  ```

  ```csharp
  string a = ""; //Empty: Alan tahsisinde bulunuyor
  string _a = null; //Null: Alan tahsisinde bulunmuyor
  ```

> Null olan bir değer üzerinde işlem yapmaya çalıştığımızda run time hatası meydana gelir. Amma velakin empty olan bir değer üzerinde işlem gerçekleştirilebilir.



### IsNullOrEmpty Kontrolü

> Elimizdeki string ifadelerin işleme tabi tutulmadan önce kesinlikle kontrol edilmesi gerekmektedir.

```csharp
string x = ""; //Empty
if (x != string.Empty && x != null)
{
    //Operasyon...
}
//IsNullOrEmpty fonksiyonu elimizdeki string ifadenin null yahut empty olup olmama durumları hannkında bir check yapar ve geriye bool türde sonuç döner.
//Eğer ki değer null ya da empty ise geriye true, değilse false dönecektir.
if (!string.IsNullOrEmpty(x))
{
    //Operasyon...
}
```



### IsNullOrWhiteSpace Kontrolü

```csharp
//IsNullOrWhiteSpace fonksiyonu : Elimizdeki string ifadenin null, empty yahut boşluk karakterlerinden ibaret olma durumunda geriye bool true değerini döndüren bir fonksiyondur.
string x = "        ";
if (!string.IsNullOrWhiteSpace(x))
{
    //Operasyon...
}

```



## String RAM(Heap) İlişkisi

> String ifadelerin değerleri referans türlü oldukları için bir nesnedir. Nesne olduklarından dolayı heap'de tutulurlar. String değişkenler referans olduklarından dolayı belleğin stack kısmında tutulurlar.

```csharp
string x = "12345";
//Stack -> string x
//Heap -> "12345"
```



## String char Dizisidir!

> Bir string yapısal olarak nelerden oluşuyor inceleyelim,
>
> ```csharp
> //String ifadeler esasında bir char dizisidir. Yani yazılım açısından string ifadesi yoktur! Esasında karakterlerin bir araya gelmiş hali vardır. Dolayısıyla karakterleri bir araya getirebilecek yegane şey bir dizidir. String ifadeler yazılımsal açıdan bilgisayarda bir char dizisi olarak tarif edilmekte ve o şekilde tutulmaktadırlar.
> //string ifadeler özünde bir char dizisi/yani dizi olmasından dolayı referans türlü değişkenlerdir, nesnedirler ve heapte tutulurlar.
> 
> string metin = "sebepsiz boş yere ayrılacaksan...";
> //string ifadeler char dizisi olduklarından dolayı yapısal olarak her bir karakter baştan sona otomatik indexlenmektedirler. Dolayısıyla string bir ifade üzerinde bizler indexer operatörünüde kullanabilmekteyiz.
> Console.WriteLine(metin[3]);
> 
> Array array = metin; //string özünde bir çar dizisi olabilir amma velakin yapısal olarak yine de string olduğu için Array referansına atılamaz, Array ile karşılanamaz!
> ```



## Döngülerle String Metin İçerisinde Her Bir Karaktere Ulaşma

```csharp
string metin = "sebepsiz boş yere ayrılacaksan...";

for (int i = 0; i < metin.Length; i++)
{
    //e harfinin bulunduğu index değerlerini ekrana yazdıralım.
    if (metin[i] == 'e')
        Console.WriteLine(i);
}
```



## String İfadelerde "+" Operatörü

> '+' operatörü kullanılabilmektedir:
>
> İki string ifade arasında birleştirme görevi görür.
>
> ```csharp
> string a ="merhaba",b ="dünya";
> Console.WriteLine(a+b);
> //Bir string ifade ile herhangi bir tür + operatörüyle işleme tabi tutulabilir.
> //+ operatörü string bir ifadeyle herhangi bir türdeki ifadeleri işleme tabi tutarken object + string davranışı sergileyecek ve sonuç olarak geriye string değer döndürecektir.
> int a2 = 5;
> Console.WriteLine(a + a2);
> //Dolayısıyla herhangi bir ifadeyi string'e dönüştürebilmek için o ifadeyi +"" ile işleme tutmak yeterli olabilir.
> Console.WriteLine(5+6+7+8+"metin");
> ```



## String Formatlandırma

```csharp
string isim ="Mustafa", soyisim="Kurt", tcNo ="12345678910";
int yas = 26;
bool medeniHal = true;

Console.WriteLine("TC No: ......... olan ....... ....... şahsın bilgileri | Yaş : .. | Medeni Hali : ..");
```

* 3 çeşit string formatlandırma operasyonu vardır:
  1) '+' operatörüyle string formatlandırma
  2) string.Format fonksiyonu
  3) string interpolation (c# 6.0)



### "+" Operatörü ile Formatlandırma

```csharp
string isim ="Mustafa", soyisim="Kurt", tcNo ="12345678910";
int yas = 26;
bool medeniHal = true;

//Console.WriteLine("TC No: ......... olan ....... ....... şahsın bilgileri | Yaş : .. | Medeni Hali : ..");
Console.WriteLine("TC No: "+ tcNo +" olan "+ isim +" "+ soysisim +" şahsın bilgileri | Yaş : "+ yas +" | Medeni Hali : "+ (medeniHal ? "Evli" : "Bekar"));
//+ ile string formatlandırmada ternary operatörü kullanıyorsanız bunu parantez içerisine almanız gerekmektedir.
```

> '+' operatörü ile string formatlandırma operasyonu hem kod hem de performans açısından oldukça maliyetlidir.
>
> O yüzden tercih etmeyeceğiz.



### String.Format

```csharp
string isim ="Mustafa", soyisim="Kurt", tcNo ="12345678910";
int yas = 26;
bool medeniHal = true;

//Console.WriteLine("TC No: ......... olan ....... ....... şahsın bilgileri | Yaş : .. | Medeni Hali : ..");
string sonuc = string.Format("TC No: {0} olan {1} {2} şahsın bilgileri | Yaş : {3} | Medeni Hali : {4}",tcNo, isim, soyisim, yas,(medeniHal ? "Evli" : "Bekar"));
Console.WriteLine(sonuc);
```

> String.Format fonksiyonu metinsel kalıbın içerisindeki belirlenen noktalara sırasıyla değer göndermemizi sağlayan bir fonksiyondur.
>
> ```csharp
> // "......{0}......{1}......{2}.....",...., ....., .....
> ```



### $(String Interpolation) (C# 6.0)

> String Interpolation, string ifadenin içerisinde süslü parantez ile araya girerek, programatik bir değişkenin değerini bırakmamızı/eklememizi sağlayan bir operatördür.

```csharp
string isim ="Mustafa", soyisim="Kurt", tcNo ="12345678910";
int yas = 26;
bool medeniHal = true;
// Bir string değerin başına $ operatörü konulursa bu ifadenin içerisinde string interpolation operasyonunun/operatörünün kullanılabilirliği sağlanır. Yani ilgili string içerisindeki {} süslü parantezler bir interpolation özelliği sergiler.
// $"....{}...."
Console.WriteLine($"TC No: {tcNo} olan {isim} {soyisim} şahsın bilgileri | Yaş : {yas} | Medeni Hali : {(medeniHal ? "Evli": "Bekar")}");
//String interpolation yapısal olarak arkaplanda string.Format fonksiyonuyla şekillenen bir operatördür.
//Ternary vs.. kullanılıyorsa parantez içerisine alınız.
//String interpolation kullanılan string ifadelerde metinsel olarak {} süslü parantez kullanma ihtiyacı durumunda operatif olan süslü parantezleri yine aynı operatörlere ezerek metinsel hale getirebilmekteyiz. {{ahmet}} gibi..
```



## Escape(Kaçış) Karakterleri

```csharp
//"........" -> (")Eylemsel bir karakterdir. String açısından belirli bir operasyonu/eylemi/sorumluluğu üstlenen bir karakterdir.
// Dolayısıyla böyle bir karakteri metinin içerisinde salt bir şekilde kullanmamız mümkündür.
//"....."........" -> Eğer ki bu şekilde string için özel eylemsel mahiyet ifade eden bir karakteri metinsel olarak kullanacaksam, bu karakterin o anlık özel karakter olmadığını ifade etmemiz gerekir.
// String içerisinde kaçış karakteri olarak \(Backword Slash) kullanılmaktadır. String içerisinde özel/operatif karakterleri ezen ve bunları metinsel hale getirmemizi sağlayan bir karakterdir.
```

```csharp
Console.WriteLine("\"Bugün hava çok güzel\"");
// \.. Kendisinden sonra gelen karakterin özel/operatif olmadığını, bunun metinsel bir karakter olduğunu bildirir.
// Metinsel olarak \ kullanmak istiyorsak eğer, bunu kendisi ile ezmeliyiz.
Console.WriteLine("Mustafa\\Kurt");

```

<img src=https://i.imgur.com/ePenoVE.png width=60% align=left />

> Görüldüğü üzere tab, enter, satır sonu vs. gibi doğrudan klavye tarafından girilemeyen bazı tuşları oluşturmak için de kullanılabilir.



## @(Verbatim Strings) Operatörü

### Kullanım-1

Bir değişken yahut metot vs. gibi yapılanma isimlerinin programatik bir keyworde karşılık gelmesi mümkün değildir. Derleyici hatası verilir.
Eğer ki illa ben bir keyword ismi kullanacağım diyorsanız, @ kullanabilirsiniz.

```csharp
int @void = 5;
int @class = 5;
int @namespace = 5;
void @void ()
{
    
}
```



### Kullanım-2

Escape karakterlerinin kullanılması durumunda, metinsel ifadeye @ operatörünü kullanarak eylemsel karakterleri kendileriyle ezebilecek özellik kazandırıyoruz.

```csharp
//string metin = "hava çok \"güzel\"";
string metin = @"hava çok ""güzel""";
```



### Kullanım-3

```csharp
string metin = "masdasdafafs //C#'da string ifade birleştirilmeden bu şekilde alt alta yazılmaz.
    awfwkoqwfpoqwf
    epoqgmoqogeg
    qowqrqowrqwr
    asdasfasf";

string metin = "masdasdafafs" + //Yazabilmek için bu şekilde + operatörüyle birleştirmek gerekir.
    "awfwkoqwfpoqwf" +
    "epoqgmoqogeg" +
    "qowqrqowrqwr" +
    "asdasfasf";

string metin = @"masdasdafafs //Veya @ verbatim operatörü kullanarak da bu şekilde yazabilmekteyiz.
    awfwkoqwfpoqwf
    epoqgmoqogeg
    qowqrqowrqwr
    asdasfasf";
```



## String Interpolation İle Verbatim Strings Birlikteliği (C# 8.0)

```csharp
string isim = "Mustafa", soyisim = "Kurt", siparisNo="123123";
int fiyat = 150;

string mailMessage = 
@$"Merhaba {isim} {soyisim}
{siparisNo} nolu sipariş talebiniz tarafımızca alınmıştır.
Fiyat : {fiyat}";
        
//String interpolation ile verbatim strings kullanılıyorsa, önce verbatin sonra string interpolatin bildirilmelidir.
        // @$
```



## String Fonksiyonlar

> String üzerinde işlem yapmamızı sağlayan fonksiyonlardır.

### Contains

String içerisinde bir metinsel ifadenin olup olmadığını check eden ve geriye bool türünde değer döndüren bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";

bool sonuc = metin.Contains("laylom");
Console.WriteLine(sonuc);
```



### StartsWith

İlgili metinin verilen değerle başlayıp başlamama durumunu kontrol edip bool türünde değer döndüren bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
Console.WriteLine(metin.StartWith("Laylay"));
```



### EndsWith

İlgili metinin verilen değerle sonlanıp sonlanmama durumunu kontrol edip bool türünde değer döndüren bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
Console.WriteLine(metin.EndWith("r..."));
```



### Equals

Elimizdeki metinsel ifade ile herhangi bir ifadenin değersel olarak eşit olup olmamasını check eden ve geriye bool sonuç dönen bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
Console.WriteLine(metin.Equals("laylaylom galiba sana göre sevmeler...")); //Büyük-küçük harf duyarlılığı vardır. Haliyle false döner.
```



### Compare

Metinsel ifadeleri karşılaştırmamızı ve sonuç olarak int türde değer elde etmemizi sağlayan bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
//0 : Her iki değer birbirine eşittir.
//1 : Soldaki sağdakinden alfa-numerik olarak büyük
//-1 : Soldaki sağdakinden alfa-numerik olarak küçük

Console.WriteLine(string.Compare(metin, "Z"));
Console.WriteLine(string.Compare(metin, "a"));
Console.WriteLine(string.Compare(metin, metin));
```



### CompareTo

Metinsel ifadeleri karşılaştırmamızı ve sonuç olarak int türde değer elde etmemizi sağlayan bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
Console.WriteLine(metin.CompareTo("Z"));
Console.WriteLine(metin.CompareTo("a"));
Console.WriteLine(metin.CompareTo(metin));
```



### IndexOf

Verilen değerin string ifade içerisinde olup olmamasını geriye int döndren bir fonksiyondur.

Geriye int olarak indexNo'yu döndürür. Eğer ki aradığımız bir kelimeyse bize ilk harfinin index numarasını döndürür.

Verilen değer string ifade içerisinde yoksa -1 değerini döndürür.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
Console.WriteLine(metin.IndexOf("La"));
Console.WriteLine(metin.IndexOf("lay"));
Console.WriteLine(metin.IndexOf("sana"));
```

> IndexOf ilk eşleşen değerin indexini döndürür.



### Insert

Elimizdeki metinsel ifadeye bir değer dahil etmemizi/eklememizi sağlayan bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
string yeniMetin = metin.Insert(17,"merhaba");
//İlgili ekleme operasyonu gerçekleştikten sonra eklenmiş hali string olarak döndürülecektir. Yani deep copy yapacaktır.
Console.WriteLine(metin);
Console.WriteLine(yeniMetin);
```



### Remove

Metinsel ifade de indexel olarak verilen değer aralığını silen bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
//Insertte olduğu gibi ilgili fonksiyon yapmış olduğu işlem neticesinde yeni bir değeri üreterek string olarak döndürecektir. Elimizdeki orjinal veri değişmeyecektir.
Console.WriteLine(metin.Remove(5));//5. indexten sonraki tüm değerleri sil..
Console.WriteLine(metin.Remove(5,10));//5. indexten başlar 10 adet sil..
Console.WriteLine(metin);
```



### Replace

Elimizdeki metinsel ifade de belirtlien değerleri yahut karakterleri, diğer değerler ya da karakterler ile değiştirmemizi sağlayan bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
//Sonuç olarak string değer üretecek ve geriye döndürecektir.
Console.WriteLine(metin.Replace("a","b"));
Console.WriteLine(metin.Replace("la","lo"));
```



### Split

Metinsel ifadeyi verilen değeri ayraç olarak kullanıp, parçalayan ve sonucu string dizisi olarak döndüren bir fonksiyondur.

```csharp
string metin = "Laylaylom galiba sana göre sevmeler...";
string[] _metin = metin.Split(' ');
string[] _metin2 = metin.Split(' ', 'a');
```



### Substring

Metinsel ifadenin belirli bir aralığını elde etmemizi sağlar.

```csharp
string metin = "laylaylom galiba sana göre sevmeler...";
Console.WriteLine(metin.Substring(5));//5. indexten sonuna kadar tüm değerleri getir.
Console.WriteLine(metin.Substring(5,10));//5. indexten başlayacak ve 10 karakter getirecektir.
```



### ToLower

Metinsel ifadenin tüm karakterlerini küçük karakter olarak düzenler.

```csharp
string metin = "Laylaylom Galiba Sana Göre Sevmeler...";
Console.WriteLine(metin.ToLower());
Console.WriteLine(metin);
```



### ToUpper

Metinsel ifadenin tüm karakterlerini büyük karakter olarak düzenler.

```csharp
string metin = "Laylaylom Galiba Sana Göre Sevmeler...";
Console.WriteLine(metin.ToUpper());
Console.WriteLine(metin);
```



### Trim

Metinsel ifadelerin varsa solundaki ve sağındaki boşluk karakterlerini temizleyen bir fonksiyondur.

```csharp
Console.WriteLine("ahmet cümbül");
Console.WriteLine("          ahmet cümbül      ".Trim());
```



### TrimEnd

Metinsel ifadelerin sonunda varsa boşluk bunları temizlememizi sağlayan bir fonksiyondur.

```csharp
Console.WriteLine("ahmet cümbül");
Console.WriteLine("          ahmet cümbül      ".TrimEnd());
```



### TrimStart

Metinsel ifadelerin başında varsa boşluk bunları temizlememizi sağlayan bir fonksiyondur.

```csharp
Console.WriteLine("ahmet cümbül");
Console.WriteLine("          ahmet cümbül      ".TrimStart());
```



## Örnek Çalışmalar

### Adımızın İlkten 5. Soyadımızın Sondan 3. Karakterini Getirelim

```csharp
//Adımızın ilkten 5. soyadımızın sondan 3. karakterini getirelim.
string adSoyad = "Mustafa Kurt";
////Çözüm-1
//Console.WriteLine(adSoyad[4]);
//Console.WriteLine(adSoyad[adSoyad.Length-3]);

////Çözüm-2
//string aralik = adSoyad[4..^2];
//Console.WriteLine(aralik[0]);
//Console.WriteLine(aralik[aralik.Length-1]);
```



### Girilen Metinin İçerisinde Kaç Adet "n" Karakterinin Geçtiğini Hesaplayalım

```csharp
//Girilen metinin içerisinde kaç adet 'n' Karakterinin geçtiğini hesaplayalım.
Console.WriteLine("Lütfen bir metin giriniz.");
string metin = Console.ReadLine();

int sayac = 0;
for (int i = 0; i < metin.Length; i++)
{
    if(metin[i] == 'n')
        sayac++;
}
Console.WriteLine(sayac);
```



### Girilen Metindeki Kelime Sayısını Hesaplayalım

```csharp
//Girilen metindeki kelime sayısını hesaplayalım.
Console.WriteLine("Lütfen bir metin giriniz.");
string metin = Console.ReadLine();

////Çözüm-1
//string[] kelimeler = metin.Split(' ');
//Console.WriteLine(kelimeler.Length);

////Çözüm-2
int sayac = 1;
while (true)
{
    int index = metin.IndexIf(' ');
    if(index == -1)
        break;
    
    sayac++;
    
    metin = metin.Substring(index + 1);
}
Console.WriteLine(sayac);
```



