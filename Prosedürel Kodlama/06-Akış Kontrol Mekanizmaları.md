# C# Notları (Akış Kontrol Mekanizmaları)

[TOC]



## Akış Kontrol Mekanizmaları Nedir?

> Akış kontrol mekanizmaları, kodun akış sürecinde belirli şartlara göre farklı yönlendirmeleri yapmamızı ve farklı algoritmaları kodları/ yapılanmaları çalıştırmamızı sağlayan mekanizmalardır.
>
> * Yazılım kodunun akış sürecinde şarta göre yönlendirilmesini sağlamaktadır.
>
> * Algoritmalarda ciddi manada kullanılan yapılardır. O yüzden yazılımcılar açısından olmazsa olmaz yapılanmalardır.
>
> * Akış kontrol mekanizmalarında If else veya switch yapılanmaları aynı işi farklı şekilde yapmamızı sağlayan birbirlerinden farklı yapılanmalardır.
>   * *İkisi arasında teknik olarak fark olsa da işleyiş/ kullanım açısından bir fark yoktur!*
>   
>     



## Switch Case

> Switch Case : Kodun akışında belirli bir şarta göre yönlendirme yapmamızı (farklı algoritma çalıştırmamızı / farklı operasyon gerçekleştirmemizi / tektiklememizi) sağlayan yapılanmadır.
>
> Swtich case yapılanması, bir değişkenin değerini ***sadece eşitlik durumlarını kontrol ederken kullanılabilir.***
>
> * Sadece eşitlik durumu check edilecekse o zaman switch kullanılabilir.
>
> <img src="https://imgur.com/5RX69nr.png" align=left>
>
> > Örnek
> >
> > ```csharp
> > string ad = "Ahmet";
> > switch(ad)//Kontrol edilen değerin türü neyse case bloklarında da aynı türde değerlerle kontrol edilmelidir.
> > {
> >     case "Mehmet": //Bunlar değişken olamaz!
> >         Console.WriteLine("Adı Mehmet");
> >         break;
> >     case "Ayşe":
> >         Console.WriteLine("Adı Ayşe");
> >         break;
> >     case "Hilmi":
> >         Console.WriteLine("Adı Hilmi");
> >         break;
> >     default : //case bloklarından hiçbiri eşleştirmeye uymuyorsa eğer, varsa default bloğu tetiklenir
> >         Console.WriteLine("Hiçbiri değil.")
> >         break;
> >         //default bloğu yoksa, ve hiçbiri eşleştirmeye uymuyorsa switch case'den çıkar.
> > }
> > ```
>
> * **Switch parantezinde kontrol edilen değer bir değişken veya sabit/statik bir değer olabilirken**
>
>   **case bloklarındaki değerler kesinlikle sabit/statik olmak zorundadır. Caselerdeki değerler değişkenlerden alınamaz!**
>
> * *Case bloklarının sıralaması ve default'un yerleştirildiği yer önemli değildir.*
>
>   



### when

> Switch yapılanmasında sadece elimizdeki değerin eşitlik durumunu kontrol edebilmekteyiz, bunun dışında bu kontrol esnasında farklı şartları da değerlendirmek istiyorsak, when keywordunu kullanırız.
>
> > Örnek
> >
> > ```csharp
> > int satisTutar = 1000;
> > switch(satisTutar)
> > {
> >     case 1000 when (3 == 5): //Konseptin içindeki şart doğrulandığı zaman buradaki blok tetiklenecektir.
> >         Console.WriteLine("Case doğrulanır, ikinci şart doğrulanmadığı için sonraki case'e geçer!");
> >         break;
> >     case 1000 when (3 == 3):
> >         Console.WriteLine("Case doğrulanır, ikinci şart da doğrulandığı için yazdırılır.");
> >         break;
> > }
> > ```
>
> 



### goto

> Switch case yapılanmasında sadece eşitlik durumunu inceleyebildiğimiz için mantıksal bir işlem gerçekleştirememekteyiz. Dolayısıyla bazen farklı değerlere eşit olma durumunda aynı operasyonu/kodu/akışı kullanacağımız senaryolarda karşılaşabilmekteyiz.
>
> > İnceleyelim
> >
> > ```csharp
> > switch(value)
> > {
> >     case "a":
> >         //A islemini uygula
> >         break;
> >     case "b":
> >         //B islemini uygula
> >         break;
> >     case "c":
> >         //A islemini uygula (tekrar kod)
> >         break;
> > }
> > //Farklı eşitliklerde aynı kodu çalışıtracaksak eğer, kod tekrarına girmemek için goto keywordu ile şu case'deki kodu çalıştır diyebilmekteyiz.
> > //Yani case'ler arasında zıplama yapabilmekteyiz.
> > ```
>
> > Örnek
> >
> > ```csharp
> > int i = 10;
> > switch(i)
> > {
> >     case 5:
> >         Console.WriteLine(i * 10);
> >         break;
> >     case 6:
> >         Console.WriteLine(i / 5);
> >         break;
> >     case 7:
> >         Console.WriteLine(i * 10);//Tekrar
> >         break;
> >     case 10:
> >         Console.WriteLine(i * 10); //Tekrar
> > }
> > ```
> >
> > Bu şekilde kod tekrarının olduğu durumlarda goto keywordunu şöyle kullanabilmekteyiz;
> >
> > ```csharp
> > int i = 10;
> > switch(i)
> > {
> >     case 5:
> >         Console.WriteLine(i * 10);
> >         break;
> >     case 6:
> >         Console.WriteLine(i / 5);
> >         break;
> >     case 7:
> >         goto case 5; //Case 5'deki kodu çalıştır demiş oluyoruz, goto kullanılan case'de break komutunu kullanmıyoruz!
> >     case 10:
> >         goto case 5; //Case 5'deki kodu çalıştır demiş oluyoruz, goto kullanılan case'de break komutunu kullanmıyoruz!
> > }
> > ```
> >
> > * *goto ile gidilen case'in eşleştirmesine bakmaksızın direkt olarak kodunu çalıştıracaktır.*
> >
> > * Birden fazla aynı case'e yönlendirilen goto keywordunun kullanıldığı durumlarda şu şekilde daha pratik bir yaklaşım uygulayabilmekteyiz;
> >
> >   ```csharp
> >   case 7:
> >   case 10:
> >   	goto case 5;
> >   ```
>
> 



## Switch Expressions (C# 8.0)

### Switch Expression

> * Tek satırlık işlemler için maliyet düşürücü ve kullanışlı semantiklerdir.
>
>   ```csharp
>   string mesaj = "";
>   switch(DateTime.Now.DayOfWeek)
>   {
>       case DayOfWeek.Monday;
>           mesaj = "Bugün Pazartesi";
>           break;
>       case DayOfWeek.Tuesday:
>           mesaj = "Bugün Salı";
>           break;
>           //...
>   }
>   Console.WriteLine(mesaj);
>   ```
>
>   > Switch 8.0 ile gelen özelliğimizle ise semantik açıdan şu şekildedir
>   >
>   > ```csharp
>   > string mesaj = DateTime.Now.DayOfWeek switch
>   > {
>   >         DayOfWeek.Monday => "Bugün Pazartesi",
>   >         DayOfWeek.Tuesday => "Bugün Salı",
>   >         DayOfWeek.Wednesday => "Bugün Çarşamba",
>   >         DayOfWeek.Thursday => "Bugün Perşembe",
>   >         DayOfWeek.Friday => "Bugün Cuma",
>   >         DayOfWeek.Saturday => "Bugün Cumartesi",
>   >         DayOfWeek.Sunday => "Bugün Pazar"
>   > };
>   > Console.WriteLine(mesaj);
>   > ```
>
>   > Örnek
>   >
>   > ```csharp
>   > //Eski Yöntemle;
>   > /* 
>   > string isim = "";
>   > int i = 10;
>   > switch(i)
>   > {
>   >     case 5:
>   >         isim = "Hilmi";
>   >         break;
>   >     case 7:
>   >         isim = "Rıfkı";
>   >         break;
>   >     case 10:
>   >         isim = "Mustafa";
>   >         break;
>   > }
>   > */
>   > 
>   > //Switch Expression (Yeni Yöntem)
>   > int i = 10;
>   > string isim = i switch
>   > {
>   >         5 => "Hilmi",
>   >         7 => "Rıfkı",
>   >         10 => "Mustafa"
>   > };
>   > ```
>   >
>   > *Yapısal olarak bütün kurallar burada da geçerli, tek satırlı işlem yapmak için kullandığımız bir yapıdır.*
>
>   

### when Şartı ile Switch Expression

>İki şekilde kullanımı mevcuttur.
>
>>1.Kullanım
>>
>>```csharp
>>int i = 10;
>>string isim = i switch
>>{
>>        5 when 3 == 3 => "Hilmi", //case durumu yani 5'i ye eşitse ve ikinci şart olan 3 == 3 true ise çalışacaktır.
>>        7 when 5 == 3 => "Rıfkı", //case durumu yani 7'i ye eşitse ve ikinci şart olan 5 == 3 true ise çalışacaktır.
>>        10 when 10 > 9 => "Mustafa" //case durumu yani 10'i ye eşitse ve ikinci şart olan 10 > 9 true ise çalışacaktır. 
>>};
>>```
>
>> 2.Kullanım
>>
>> ```csharp
>> int i = 10;
>> string isim = i switch
>> {
>>         //5 when 3 == 3 => "Hilmi", olarak kullanılabilmesinin yanında bir değişken tanımlayarak da kullanılabilir.
>>         var x when x == 5 && x % 2 == 1 => "Hilmi",
>>         var x when x == 7 && x % 2 == 1 => "Rıfkı",
>>         var x when x == 10 && x % 2 == 1 => "Mustafa",
>>         var x => "Hiçbiri" //default : Hiçbir eşleştirmenin olmadığı durumda default tanımlamasına karşılık gelecektir.
>> };
>> ```
>
>



### Tuple Patterns

> * Tuple patterns ise switch yapılanmasını Tuple nesnelerini kontrol edebilecek şekilde hem standart hemde yeni yapılanmayla bizlere sunmaktadır.
>
>   ```csharp
>   string adi = "Ayşe";
>   int yasi = 27;
>             
>   string mesaj = "";
>   switch (adi, yasi) // -> Artık buraya tuple nesnemizi verebiliyoruz ve kıyaslayabiliyoruz.
>   {
>       case ("Hüseyin", 20):
>           mesaj = "Hoşgeldin Hüseyin";
>           break;
>       case ("Cansu", 37):
>           mesaj = "Hoşgeldin Cansu";
>           break;
>       case ("Nalan", 21):
>           mesaj = "Hoşgeldin Nalan";
>           break;
>       case ("Hilmi", 35):
>           mesaj = "Hoşgeldin Hilmi";
>           break;
>   }
>   Console.WriteLine(mesaj);
>   ```
>
>   > Bunun dışında tek satırda da bu işlemi gerçekleştirebiliyoruz.
>   >
>   > ```csharp
>   > string adi = "Ayşe";
>   > int yasi = 27;
>   > string mesaj = (adi,yasi) switch
>   > {
>   >         ("Hüseyin", 20) => mesaj = "Hoşgeldin Hüseyin",
>   >         ("Cansu", 37) => mesaj = "Hoşgeldin Cansu",
>   >         ("Nalan", 21) => mesaj = "Hoşgeldin Nalan",
>   >         ("Nevin", 27) => mesaj = "Hoşgeldin Nevin",
>   >         ("Hilmi", 35) => mesaj = "Hoşgeldin Hilmi",
>   >         (_,_) => "Hoşgeldin" //Default
>   > };
>   > Console.WriteLine(mesaj);
>   > ```
>
>   > Örnek
>   >
>   > ```csharp
>   > int s1 = 10;
>   > int s2 = 20;
>   > string mesaj = "";
>   > 
>   > switch (s1, s2)
>   > {
>   >     case (5, 10):
>   >         mesaj = "5 ile 10 değerleri";
>   >         break;
>   >     case (10,20):
>   >         mesaj = "10 ile 20 değerleri";
>   >         break;
>   >     default :
>   >         mesaj = "Değer bulunamadı";
>   >         break;
>   > }
>   > Console.WriteLine(mesaj);
>   > //Daha gelişmiş bir yapılanma ile ise;
>   > string mesaj2 = (s1, s2) switch
>   > {
>   >         (5,10) => mesaj = "5 ile 10 değerleri",
>   >         (10,20) => mesaj = "10 ile 20 değerleri",
>   >         (_,_) => "Değerler bulunamadı"
>   > };
>   > Console.WriteLine(mesaj2);
>   > ```
>
>   



### Tupple Patterns when Şartı Uygulamak

> ```csharp
> int s1 = 10;
> int s2 = 20;
> string mesaj = (s1,s2) switch
> {
>         (5,10) when (true) => "5 ile 10 değerleri",
>         var x when x.s1 % 2 == 1 || x.s2 == 10 => "10 ile 20 değerleri"
> };
> Console.WriteLine(mesaj)
> ```
>
> 



### Property Patterns

> Property patterns, nesnenin proportylerine girerek belirli durumları hızlı bir şekilde kontrol etmemizi gerçekleştiren ve bunu farklı değerler için birden fazla kez tekrarlı bir şekilde yapmamıza olanak sağlayan bir gelişimdir.
>
> ```csharp
> namespace SwitchExpression
> {
>     class Program
>     {
>         static void Main(string[]args)
>         {
>             Ogrenci ogrenci = new Ogrenci
>             {
>                 Adi = "Mustafa",
>                 Soyadi ="KURT",
>                 Meslek = "Öğrenci"
>             };
>             /*
>             double maas = 0;
>             switch (ogrenci.Meslek)
>             {
>                 case "Kasap":
>                     maas = 8000;
>                     break;
>                 case "Tesisat Ustası":
>                     maas = 7500;
>                     break;
>                 case "Otobüs Şöförü":
>                     maas = 7800;
>                     break;
>                 case "Öğrenci":
>                     maas = -2000;
>                     break;
>             }
>             Console.WriteLine(maas);
>         *///-> Burada yapılan işlemleri switch expression ile bu şekilde gerçekleştirebiliyoruz.
>             double maas = ogrenci switch
>             {
>                     { Meslek: "Kasap" } => 8000, //Meslek propertysine bu şekilde erişebiliyoruz.
>                     { Meslek: "Tesisat Ustası" } => 7500,
>                     { Meslek: "Otobüs Şöförü" } => 7800,
>                     { Meslek: "Öğrenci" } => -2000
>             };
>             Console.WriteLine(maas);
>         }
>     }
>     class Ogrenci
> 	{
>     	public string Adi {get; set;}
>     	public string Soyadi {get; set;}
>     	public string Meslek {get; set;}
> 	}
> }
> 
> ```
>
> 



### Property Patterns when Şartı Uygulamak

> ```csharp
> namespace SwitchExpression
> {
>     class Program
>     {
>         static void Main(string[]args)
>         {
>             Ogrenci ogrenci = new Ogrenci
>             {
>                 Adi = "Mustafa",
>                 Soyadi ="KURT",
>                 Meslek = "Öğrenci"
>             };
>            
>             double maas = ogrenci switch
>             {
>                     { Meslek: "Kasap" } => 8000, //Meslek propertysine bu şekilde erişebiliyoruz.
>                     var x when x.Meslek == "Tesisat Ustası" => 7500,
>                     { Meslek: "Otobüs Şöförü" } when !true => 7800,
>                     var x when x.Meslek == "Öğrenci" } => -2000,
>                     var x => 0 //ya da _ => 0 //Default
>             };
>             Console.WriteLine(maas);
>         }
>     }
>     class Ogrenci
> 	{
>     	public string Adi {get; set;}
>     	public string Soyadi {get; set;}
>     	public string Meslek {get; set;}
> 	}
> }
> ```
>
> 



### Positional Patterns

> Positional patterns ise *Deconstruct* özelliği olan nesneleri kıyaslamak veya değersel karşılaştırmak için kullanılan bir gelişimdir.
>
> ```csharp
> namespace SwitchExpression
> {
>     class Program
>     {
>         static void Main(string[]args)
>         {
>             Ogrenci ogrenci = new Ogrenci
>             {
>                 Adi = "Mustafa",
>                 Soyadi ="Kurt",
>                 Meslek = "Öğrenci"
>             };
>            
>             var isim = ogrenci switch
>             {
>                     ("Ahmet", "Yıldırım") => "Ahmet Yıldırım",
>                     ("Hilmi", "Celayir") => "Hilmi Celayir",
>                     ("Semih", "Fidan") => "Semih Fidan",
>                     ("Mustafa", "Kurt") => "Mustafa Kurt",
>                     (_,_) => "Hiçbiri",
>                     _ => "Hiçbiri"
>             };
>         }
>         class Ogrenci
> 	    {
>     		public string Adi {get; set;}
>     		public string Soyadi {get; set;}
>     		public string Meslek {get; set;}
>         	public void Deconstruct (out string adi, out string soyadi)//Geriye Tuple gibi bir değer dönüyor
>         	{
>             	adi = Adi;
>             	soyadi = Soyadi;
>         	}
> 	    }
>     }
> }
> ```
>
> Tuple türünde _ hiçbiri anlamına gelir.
>
> 



### Positional Patterns when Şartı Uygulamak

> Diğerlerinde olduğu gibi when şartını '=>' ise'den önce ya da değişken eşliğinde kullanabilmekteyiz.
>
> ```csharp
> namespace SwitchExpression
> {
>     class Program
>     {
>         static void Main(string[]args)
>         {
>             Ogrenci ogrenci = new Ogrenci
>             {
>                 Adi = "Mustafa",
>                 Soyadi ="Kurt",
>                 Meslek = "Öğrenci"
>             };
>            
>             var isim = ogrenci switch
>             {
>                     ("Ahmet", "Yıldırım") => "Ahmet Yıldırım",
>                     var x when x.Adi == "Hilmi" && x.Soyadi == "Celayir" => "Hilmi Celayir",
>                     ("Semih", "Fidan") when 3 == 5 => "Semih Fidan",
>                     var x when x.Adi == "Mustafa" && x.Soyadi == "Kurt" => "Mustafa Kurt",
>                     (_,_) => "Hiçbiri",
>                     _ => "Hiçbiri"
>             };
>             Console.WriteLine(isim);
>         }
>         class Ogrenci
> 	    {
>     		public string Adi {get; set;}
>     		public string Soyadi {get; set;}
>     		public string Meslek {get; set;}
>         	public void Deconstruct (out string adi, out string soyadi)//Geriye Tuple gibi bir değer dönüyor
>         	{
>             	adi = Adi;
>             	soyadi = Soyadi;
>         	}
> 	    }
>     }
> }
> ```
>
> 

## if...else Yapısı

> Switch Case : Elimizdeki bir değerin sadece eşitlik durumunu check eden /kontrol eden, kıyaslayan bir akış kontrol mekanizmasıdır.

> If Yapılanması : Elimizdeki bir değerin eşitlik durumu da dahil, tüm karşılaştırmaları yapmamızı sağlayan ve sonuca göre akışı yönlendirmemizi sağlayan bir yapılanmadır.

> Prototip:
>
> ```csharp
> if (...ŞART...) // Eğer ki bu şart doğru/true ise kod bloğu tetiklenir.
> {
>     //Kod bloğu
> }
> //Eğer ki False ise compiler If scope aralığından çıkacak ve yoluna devam edecektir.
> ```
>
> 

### if  Yapısı

> * **If yapılanmasında şart kısmı her daim bool türde olmalıdır.**
> * **Karşılaştırma operatörleri ve mantıksal operatörlerin hepsi burada kullanılabilir.**

> Örnek
>
> ```csharp
> bool medeniHal = true;
> if (medeniHal == true)
> {
>     Console.WriteLine("Allah tek yastıkta kocatsın.");
> }
> // if yapılanması tek başına kullanılıyorsa sadece şarta bağlı çalışacak koda odaklanır.
> ```
>
> 

#### Kritik 1

> Örnek
>
> ```csharp
> //if yapılanmasında illa ki else kullanmak zorunda değiliz.
> int i = 10;
> if (i != 10)
> {
>     Console.WriteLine("Merhaba");
> }
> Console.WriteLine("Dünya"); //if true da olsa false da olsa burası her daim tetiklenecektir.
> ```
>
> 



#### Kritik 2

> Örnek
>
> ```csharp
> bool medeniHal = true;
> //if (medeniHal == true)
> //bool türdeki değişkenlerin değerleri zaten bool olacağından dolayı karşılaştırma operatörünü kullanmak zorunda değiliz.
> if (medeniHal) 
> {
>     Console.WriteLine("Hayırlı olsun..");
> }
> ```
>
> 



### If - Else Yapısı

> If Yapısı : Şarta göre bir kodun çalışıp çalışmayacağını belirleyen bir yapılanmadır.
>
> If Else Yapısı : Şarta göre bir kodun çalışıp, şartın olmadığı durumda bir başka kodun çalışmasını belirleyen bir yapılanmadır.
>
> *Şartın olumsuz/değil durumunda da çalışacak kodu belirlemiş oluyoruz!*
>
> > Prototip
> >
> > ```csharp
> > if (....Şart....)
> > {
> >     Şart true ise buradaki kodlar devreye girer
> > }
> > else
> > {
> >     false ise burası tetiklenecektir.
> > }
> > ```
> >
> > * If bloğunda else varsa, şartın false olması durumunda kesinlikle else bloğu tetiklenir.
> >
> > * If Else yapılanmasında şart doğru olduğunda sadece if, yanlış olduğunda ise sadece else bloğu tetiklenir.
> >
> >   ```csharp
> >   int i = 3;
> >   if(i > 5)
> >   {
> >       Console.WriteLine("i değeri 5'ten büyüktür.");
> >   }
> >   else
> >   {
> >       Console.WriteLine("i değeri 5'ten küçüktür.");
> >   }
> >   ```
>
> 



#### Kritik 1

> Örnek
>
> ```csharp
> int i = 10;
> if (i == 10)
> {
>     Console.WriteLine("i değeri 10");
> }
> else
> {
>     Console.WriteLine("i değeri 10 değil");
> }
> //Eşitlik durumuna göre tersi (manevratik ! operatörü ile kullanım)
> if (i != 10)
> {
>     Console.WriteLine("i değeri 10 değil");
> }
> else
> {
>     Console.WriteLine("i değeri 10");
> }
> ```
>
> 

#### Kritik 2

> Örnek
>
> **Önemli** : *Dont Repeat Yourself (DRY) prensibi gereği her iki kod bloğunda da aynı kodu tetiklemek istersek;*
>
> ```csharp
> int i = 10;
> if (i == 10)
> {
>     Console.WriteLine("i değeri 10");
>     Console.WriteLine("Merhaba");//Tekrar
> }
> else
> {
>     Console.WriteLine("i değeri 10 değil");
>     Console.WriteLine("Merhaba");//Tekrar
> }
> ```
>
> *Her iki durumda da ortak çalıştırılacak olan komutları if else bloğunun dışına yazmamız olayı çözecektir.*
>
> ```csharp
> int i = 10;
> if (i == 10)
> {
>     Console.WriteLine("i değeri 10");
> }
> else
> {
>     Console.WriteLine("i değeri 10 değil")
> }
> Console.WriteLine("Merhaba");//komut dışarıda
> ```
>
> 



### If - Else If  Yapısı

> If-Else if yapılanması : Birden fazla şartı kontrol etmemizi sağlayan bir yapılanmadır.
>
> > Prototip
> >
> > * else if (...şart...) : istenildiği kadar yazılabilir.
> >
> > ```csharp
> > if (...şart1...)
> > {
> >     //Eğer şart1 doğruysa bu if bloğu tetiklenecektir.
> > }
> > else if (...şart2...)
> > {
> >     //Eğer şart1 yanlış ise buradaki şart2 kontrol edilecek ve doğruysa bu kod bloğu tetiklenecektir.
> > }
> > else if (...şart3...)
> > {
> >     //Eğer önceki şartlar yanlış ise buradaki şart3 kontrol edilecek ve doğruysa bu kod bloğu tetikenecektir.
> > }
> > ...
> >     //Eğer hiçbir şart doğru değilse, if-else if yapılanmasından çıkacak, devam edecektir.
> > ```
> >
> > * If yapılanmasından herhangi biri doğruysa eğer diğer if ler(else if ler) denetlenmeyecektir. 
>
> > Örnek
> >
> > ```csharp
> > int sayi = 30;
> > if (sayi > 5 && sayi <= 10)
> > {
> >     Console.WriteLine(sayi * 5);
> > }
> > else if (sayi > 10 && sayi <= 20)
> > {
> >     Console.WriteLine(sayi * 10);
> > }
> > else if (sayi > 20 && sayi <= 30)
> > {
> >     Console.WriteLine(sayi * 20);
> > }
> > ```
>
> 



#### Kritik

> Örnek
>
> Algoritma süreçlerinde sürekli karşımıza çıkacak bir kritik olabilir.
>
> * Bazen birden fazla şartın doğru olduğunda birden fazla işlem yapmak isteyebiliriz.
>
> ```csharp
> Console.WriteLine("Bir sayı giriniz : ")
> int sayi = int.Parse (Console.ReadLine());
> if (sayi > 100 && sayi <=200)
> {
>     Console.WriteLine("100 ile 200 arasında");
> }
> else if (sayi > 200 && sayi <=300)
> {
>     Console.WriteLine("200 ile 300 arasında");
> }
> else if (sayi > 200 && sayi <=400)
> {
>     Console.WriteLine("200 ile 400 arasında");
> }
> //Bu durumu else if ile yaptığımızda örn. 200 sayısını girersek, sadece 1 blok çalışacaktır.
> //Bu durumu breakpoint ile debug ederek test edebilirsiniz.
> if(sayi > 100 && sayi <=200)
> {
>     Console.WriteLine("100 ile 200 arasında");
> }
> if (sayi > 200 && sayi <=300)
> {
>     Console.WriteLine("200 ile 300 arasında");
> }
> if (sayi > 200 && sayi <=400)
> {
>     Console.WriteLine("200 ile 400 arasında");
> }
> ```
>
> * If'ler birbirinden bağımsızdır.
> * If- Else if ise başka bir yapıdır.
>
> 



### If- Else if- Else Yapısı

> If- Else if - Else Yapılanması : If (1 kere) Else if (istenildiği/gerektiği kadar) Else(1 kere) kullanılır.
>
> > Örnek
> >
> > ```csharp
> > int i = 100;
> > if (i < 100)
> > {
> >     Console.WriteLine("100'den küçük");
> > }
> > else if (i > 100)
> > {
> >     Console.WriteLine("100'den büyük");
> > }
> > else
> > {
> >     Console.WriteLine("100'e eşit");
> > }
> > ```
>
> 



### Scopesuz If  Yapısı

> If yapılanmalarının (if-else if-else vs..) hepsi için geçerlidir.
>
> ```csharp
> if (true)
>     Console.WriteLine("Merhaba Dünya"); //If yapılanması tek satırlık bir işlem gerçekleştiriyorsa eğer, bunu scope içerisine yazmak mecburiyetinde değiliz. // Tek satırdan kastımız konseptlik 
> if (true)
> {
>     Console.WriteLine("Merhaba");//Eğer ki birden fazla konspet/işlem/operasyon barındıracaksa bunları kesinlikle scope içerisine almamız gerekir.
>     Console.WriteLine("Dünya");//Aksi taktirde scopesuz çalışırsa ilk işlemi if bloğu içerisine alacak, diğerini almayacaktır.
> }
> ```
>
> 



#### Örnek Senaryolar

##### 1.Senaryo

> Klavyeden iki ürünün fiyatı girildiğinde toplam fiyat 200TL'den fazla ise, 2.üründen %25 indirim yaparak ödenecek tutarı gösteren uygulamayı yapalım.
>
> ```csharp
> Console.Write("Lütfen birinci ürünün fiyatını giriniz : ");
> int birinciUrunFiyati = int.Parse(Console.ReadLine());
> Console.Write("Lütfen ikinci ürünün fiyatını giriniz : ");
> int ikinciUrunFiyati = int.Parse(Console.ReadLine());
> int toplamFiyat = birinciUrunFiyati + ikinciUrunFiyati;
> 
> if (toplamFiyat > 200)
> {
>     //int toplamSonTutar = birinciUrunFiyati + (ikinciUrunFiyati * 3 / 4); -> Sonradan kullanmayacağımız için gereksiz.
>     //Console.WriteLine(toplamSonTutar);
>     Console.WriteLine("Ödenecek Tutar : " + toplamFiyat - (ikinciUrunFiyati * 1 / 4));
> }
> else
> {
>     Console.WriteLine("Ödenecek Tutar : " toplamFiyat);
> }
> ```
>
> 



##### 2.Senaryo

> Belirlenen kullanıcı adı ve şifre doğru girildiğinde "Giriş Başarılı", yanlış girildiğinde "Girdiğiniz kullanıcı adı veya şifre hatalı" mesajı veren Console uygulamasını yapalım.
>
> > Kritik 1
> >
> > If yapılanması ile tek konseptlik bir yapı oluşturarak scopesuz bir şekilde yazabiliriz.
> >
> > ```csharp
> > Console.WriteLine("Lütfen kullanıcı adını yazınız : ");
> > string kullaniciAdi = Console.ReadLine();
> > Console.WriteLine("Lütfen şifrenizi giriniz : ");
> > string sifre = Console.ReadLine();
> > //Normalde veri tabanından getirilecek olan bilgileri manuel olarak burada tutacağız.
> > if (kullaniciAdi == "Mustafa" && sifre == "12345")
> >     Console.WriteLine("Giriş Başarılı.");
> > else
> >     Console.WriteLine("Girdiğiniz kullanıcı adı veya şifre hatalıdır.");
> > ```
>
> > Kritik 2
> >
> > Kullanıcı adı ve şifreyi doğruladıktan sonra girişin başarılı veya hatalı olduğu durumun tam tersini de alabiliriz.
> >
> > ```csharp
> > Console.WriteLine("Lütfen kullanıcı adını yazınız : ");
> > string kullaniciAdi = Console.ReadLine();
> > Console.WriteLine("Lütfen şifrenizi giriniz : ");
> > string sifre = Console.ReadLine();
> > //Normalde veri tabanından getirilecek olan bilgileri manuel olarak burada tutacağız.
> > if (!(kullaniciAdi == "Mustafa" && sifre == "12345"))
> >     Console.WriteLine("Girdiğiniz kullanıcı adı veya şifre hatalıdır.");
> > else
> >     Console.WriteLine("Giriş Başarılı.");
> > ```
>
> Bu kritiklerin dışında
>
> > Kritik 3 Ternary operatörü ile de yapabiliriz.
> >
> > ```csharp
> > Console.WriteLine("Lütfen kullanıcı adını yazınız : ");
> > string kullaniciAdi = Console.ReadLine();
> > Console.WriteLine("Lütfen şifrenizi giriniz : ");
> > string sifre = Console.ReadLine();
> > //Normalde veri tabanından getirilecek olan bilgileri manuel olarak burada tutacağız.
> > Console.WriteLine(kullaniciAdi == "Mustafa" && sifre == "12345" ? "Giriş Başarılı." : "Girdiğiniz kullanıcı adı veya şifre hatalıdır.");
> > ```
>
> > Kritik 4 Switch ile de yapabiliriz. (Switch expression - Tuple Patterns)
> >
> > ```csharp
> > Console.WriteLine("Lütfen kullanıcı adını yazınız : ");
> > string kullaniciAdi = Console.ReadLine();
> > Console.WriteLine("Lütfen şifrenizi giriniz : ");
> > string sifre = Console.ReadLine();
> > //Normalde veri tabanından getirilecek olan bilgileri manuel olarak burada tutacağız.
> > string mesaj = (kullaniciAdi,sifre) switch 
> > {
> >         ("Mustafa","12345") => "Giriş Başarılı.",
> >         _ => "Girdiğiniz kullanıcı adı veya şifre hatalıdır."
> > };
> > Console.WriteLine(mesaj);
> > ```
>
> 



##### 3.Senaryo

> Kullanıcıdan alınan iki sayının ve yapılacak işlem türünün (toplama, çıkarma, çarpma, bölme) seçilmesiyle, sonucu hesaplayan programı yazalım.
>
> > Kritik 1 (If-Else if- Else)
> >
> > ```csharp
> > Console.WriteLine("Lütfen 1. sayıyı giriniz. ");
> > int sayi1 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen 2. sayıyı giriniz. ");
> > int sayi2 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen yapılacak işlemi belirtiniz (+,-,*,/)");
> > char islem = char.Parse(Console.ReadLine());
> > if (islem == "+")
> > {
> >     Console.WriteLine(sayi1 + sayi2);
> > }
> > else if (islem == "-")
> > {
> >     Console.WriteLine(sayi1 - sayi2);
> > }
> > else if (islem == "*")
> > {
> >     Console.WriteLine(sayi1 * sayi2);
> > }
> > else if (islem == "/")
> > {
> >     Console.WriteLine(sayi1 / sayi2);
> > }
> > else
> > {
> >     Console.WriteLine("İşlem bulunamadı!");
> > }
> > ```
>
> > Kritik 2 (Switch-Case)
> >
> > ```csharp
> > Console.WriteLine("Lütfen 1. sayıyı giriniz. ");
> > int sayi1 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen 2. sayıyı giriniz. ");
> > int sayi2 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen yapılacak işlemi belirtiniz (+,-,*,/)");
> > char islem = char.Parse(Console.ReadLine());
> > switch (islem)
> > {
> >     case '+':
> >         Console.WriteLine(sayi1 + sayi2);
> >         break;
> >     case '-':
> >         Console.WriteLine(sayi1 - sayi2);
> >         break;
> >     case '*':
> >         Console.WriteLine(sayi1 * sayi2);
> >         break;
> >     case '/':
> >         Console.WriteLine(sayi1 / sayi2);
> >         break;
> >     default:
> >         Console.WriteLine("İşlem bulunamadı!");
> >         break;
> > }
> > ```
>
> > Kritik 3 (Switch Expression)
> >
> > ```csharp
> > Console.WriteLine("Lütfen 1. sayıyı giriniz. ");
> > int sayi1 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen 2. sayıyı giriniz. ");
> > int sayi2 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen yapılacak işlemi belirtiniz (+,-,*,/)");
> > char islem = char.Parse(Console.ReadLine());
> > 
> > int sonuc = islem switch
> > {
> >         '+' => sayi1 + sayi2,
> >         '-' => sayi1 - sayi2,
> >         '*' => sayi1 * sayi2,
> >         '/' => sayi1 / sayi2,
> >         _ => 0
> > };
> > Console.WriteLine(sonuc);
> > ```
>
> > Kritik 4 (Ternary operatörü)
> >
> > ```csharp
> > Console.WriteLine("Lütfen 1. sayıyı giriniz. ");
> > int sayi1 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen 2. sayıyı giriniz. ");
> > int sayi2 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen yapılacak işlemi belirtiniz (+,-,*,/)");
> > char islem = char.Parse(Console.ReadLine());
> > 
> > Console.WriteLine(islem == '+' ? sayi1 + sayi2 : (islem == '-' ? (sayi1 - sayi2).toString() :(islem == '*' ? (sayi1 * sayi2).toString() : (islem == '/' ? (sayi1 / sayi2).toString() : "İşlem bulunamadı!"))));
> > ```
>
> 



##### 4.Senaryo

> Girilen sayının değeri 10 değilse ekrana "sayı yanlış" yazdıralım.
>
> > Kritik 1
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > if (sayi == 10)
> > {
> > 
> > }
> > else
> > {
> >     Console.WriteLine("sayı yanlış");
> > }
> > ```
>
> > Kritik 2
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > if (sayi != 10)
> > {
> >     Console.WriteLine("sayı yanlış");
> > }
> > ```
> >
> > Kritik 1 ve 2'yi ele alırsak bunların arasındaki kod maliyetine dikkat edeceğiz.
>
> > Kritik 3
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > Console.WriteLine(sayi == 10 ? "" : "sayı yanlış");
> > ```
>
> 



##### 5.Senaryo

> Girilen sayının negatif ya da pozitif olduğunu gösteren uygulamayı yazalım.
>
> > Kritik 1
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > if (sayi < 0)
> >     Console.WriteLine("Negatif");
> > else
> >     Console.WriteLine("Pozitif");
> > ```
>
> > Akış kontrol mekanizmalarında şarta göre bir kodu işlediğimizde, o kod işlendikten sonra, şarta bağlı bir değeri süreçte kullanmak istiyorsak, akış kontrol mekanizmasının dışına taşıyacak bir değişkene ihtiyacımız olacaktır.
> >
> > Örnek
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > string sonuc = "";
> > if(sayi < 0)
> >     sonuc = "Negatif";
> > else
> >     sonuc = "Pozitif";
> > Console.WriteLine(sonuc);
> > ```
>
> 



### Pattern Matching (C# 7.0)

> Belirli desenlere eşleştirme söz konusudur. Şu deseni de kullanabilirsin diyebileceğimiz yapılanmaları getirmektedir.

#### Type Pattern

> * Object içerisindeki bir tipin belirlenmesinde kullanılan is operatörünün desenleştirilmiş halidir.
> * is ile belirlenen türün direkt dönüşümünü sağlar.
>
> > Örnek
> >
> > ```csharp
> > object x = 125;
> > if (x is string)
> > {
> >     string xx = x as string;
> >     Console.WriteLine($"x değişkeni string tipindedir.");
> > }
> > else if (x is int)
> > {
> >     int xx = (int)x;
> >     Console.WriteLine($"x değişkeni int tipindedir.");
> > }
> > //Type Pattern haliyle
> > if (x is string xx)
> >     Console.WriteLine($"x değişkeni string tipindedir.");
> > else if (x is int xx)
> >     Console.WriteLine($"x değişkeni int tipindedir.");
> > ```
>
> 



##### Kritik

> Type Pattern : Herhangi bir objectte yani boxing işlemine tabii tutulmuş bir değerin türünü tespit ettikten sonra cast işlemini is operatöründen sonra otomatik yapan bir desendir. Is opeartörünün desenleştirilmiş halidir.
>
> > Kritik
> >
> > ```csharp
> > object x = "Mustafa";
> > //C# 7.0'a kadar bu işlemi bu şekilde yaparken;
> > if (x is string) //içeride x'i kendi türünde kullanmak, kendi türündeki fonksiyonlarına erişmek isteyebilirim. 
> > {
> >     string _x = (string)x;//Dolayısıyla bunu cast ediyoruz.
> > }
> > //C# 7.0'dan sonra
> > if (x is string a)
> > {
> >     a = "Metin";
> > }
> > //Console.WriteLine(a); //Değişkenin durumu null olacabileceğinden dolayı dışarıda rahatlıkla kullanamıyoruz. (Kritik burası)
> > a = "Yeni metin";
> > Console.WriteLine(a);
> > ```
> >
> > * string a değişkeni if scope aralığında değil argümanlarında (parametrelerinde) tanımlandığından dolayı kapsadığı scope alanı if'in dışıdır.
> > * Dışarıdan erişilebilir ancak ilgili değişken null olabileceğinden dolayı Compiler hata verecektir. Dışarıda değer verdikten sonra rahatlıkla kullanabiliyoruz.
>
> 



#### Constant Pattern

> Elimizdeki veriyi sabit bir değer ile karşılaştırabilmemizi sağlar.
>
> > Örnek
> >
> > ```csharp
> > object x = "Mustafa Kurt";
> > if(x is "Mustafa")
> >     Console.WriteLine($"Mustafa");
> > else if (x is null)
> >     Console.WriteLine($"null");
> > //Veya
> > object y = 125;
> > if(x is 128)
> >     Console.WriteLine($"y değişkeninin değeri 128");
> > else if (x is 125)
> >     Console.WriteLine($"y değişkeninin değeri 125");
> > else if (x is 120)
> >     Console.WriteLine($"y değişkeninin değeri 120");
> > //Veya benzer bir şekilde
> > int a = 123;
> > Console.WriteLine(a is 123); //Değer bazlı kontrol yapmamızı da sağlayan bir patterndir.
> > ```
>
> 



##### Kritik

> Constant Pattern : Is operatörüne sabit değerleri check etmemizi sağlayan bir desendir.
>
> * is operatörü bir değişkenin türünü sormamızı/belirlememizi sağlayan bir operatördür. Ve bu operatörün kullanıldığı değişkenlerin türü illa bir referans türlü olmak zorunda değildir.
>
> * İsterseniz değer türlü değişkenlerde de is operatörü kullanılabilmektedir. Ve hatta primitive türlerde bile kullanılabilmektedir.
>
>   
>
> > Kritik
> >
> > ```csharp
> > int a = 5;
> > Console.WriteLine(a is int);
> > Console.WriteLine(a is string);
> > Console.WriteLine(a is bool);
> > //Eğer ki is operatöründe tür kontrolü yapıyorsanız bu constant pattern değildir. Yok eğer herhangi bir değişkende değer kontrolü yapıyorsanız bu Constant Pattern'dir.
> > Console.WriteLine(a is 5);
> > //Türe uygun bir değer kontrolü yapılması gerekir.
> > Console.WriteLine(a is "5"); //compiler hata verir
> > Console.WriteLine(a is "asdasdas"); //compiler hata verir
> > Console.WriteLine(a is false); //compiler hata verir
> > ```
> >
> > * *Eğer ki is operatörüyle bir değişkenin değerini == operatörünün sorumluluğuyla check ediyorsa işte buna Constant Pattern denmektedir.*
>
> 



#### Var Pattern

> Eldeki veriyi 'var' değişkeni ile elde etmemizi sağlamaktadır.
>
> > Örnek
> >
> > ```csharp
> > object x = "Türkiye";
> > if (x is var a)
> > {
> >     Console.WriteLine(a);
> > }
> > ```
>
> 



##### Kritik 1

> ```csharp
> object x = "ilk metin";
> if (x is var a) //var a -> Türü runtime da belirlenecektir.
> {
>     
> }
> ```
>
> 

##### Kritik 2

> * var normalde derleyici sürecinde türü belirlerken, var pattern'daki var run time da belirlenir.
>
> ```csharp
> object x = "metin";
> var b = "metin"; //Compiler sürecinde(derleme zamanında) direkt string olur.
> if (x is var a) // Türü runtime da belirlenir.
> {
>     
> }
> ```
>
> 



##### Kritik 3

> * var patternda türünü runtime da belirler dedik ancak eğer ki runtime da atanan değere bürünen bir değişken tanımlamak istiyorsanız bu dynamicdir.
>
> * Ama bir pattern uyguluyorsanız buradaki gibi bu senaryoda dynamic koyamazsınız.
>
>   ```csharp
>   object x = "metin";
>   if (x is dynamic a)//Bu şekilde kullanılamaz!
>   {
>           
>   }
>   ```
>
>   



#### Recursive Pattern

> * Bu desen switch-case yapılanması üzerinde bir çok yenilik getirmektedir.
> * switch bloğunda değer türlü değişkenlerin dışında, *referans türlü değişkenler de* kontrol edilebilmektedir.
> * Ayrıca switch bloğuna when komutu ile çeşitli şart/koşul niteliği kazandırılmıştır.
>
> > Örnek
> >
> > ```csharp
> > static void X(ICloneable instance)
> > {
> >     switch (instance)//instance, int, string, char gibi bir yapılanma değil, farklı bir değer türü
> >     {
> >         case SqlConnection connection:
> >             connection.ConnectionString = "Server=.;Database...";
> >             break;
> >         case SqlCommand command when (command.Connection.Conntected)://when şartı da kullanılıyor
> >             command.CommandText = "Select * from ...";
> >             break;
> >         case StreamWriter stream:
> >             stream.Write("....");
> >             break;
> >         case null://statik değer kontrolü
> >             break;
> >     }
> > }
> > ```
> >
> > *Recursive pattern, tür kontrolü yaptığı için Type Pattern'i kapsamaktadır.*
> >
> > *Recursive pattern, case null komutu ile ilgili türün/referansın null olup olmamasını kontrol edebilmesinden dolayı, Constant Pattern'ı da kapsamaktadır.*
>
> 



##### Type Pattern - Var Pattern Üzerine Kritik

> Kritik
>
> * Bahsetmiş olduğumuz patternlar akış kontrol mekanizması olmadan da kullanılabilmektedir.
>
> ```csharp
> object x = "metin";
> if (x is string a)
>     Console.WriteLine(a);
> if (x is var b)
> {
>     
> }
> 
> bool result = x is string o;//Type pattern -> Türü string ise x'i o değişkenine atayacağından dolayı null olma ihtimali vardır.
> Console.WriteLine(o); // null olma ihtimalinden dolayı compiler hata verir!
> 
> bool result0 = x is var _o;//Var pattern -> x'in türü ne olursa olsun _o değişkenine ata dediğimizden dolayı null olma ihtimali yoktur.
> Console.WriteLine(_o); // dolayısıyla rahatça kullanabilmekteyiz.
> ```
>
> 

### Pattern Matching (C# 9.0)

#### Simple Type Patterns

> * Bir değişken içerisindeki değerin belirli bir türde olup olmadığını hızlı bir şekilde kontrol etmemizi sağlayan desendir.
>
> * C# 9.0'dan önce Type Pattern ile yapılan tür bildirimlerinin yanına değişken adı tanımlaması yahut discard ifadesinin kullanılması zaruriydi. 
>
>   C# 9.0 ile bu gereksiz zorunluluk ortadan kaldırılmış ve direkt olarak tür kontrol işlemine odaklanılması sağlanmıştır.
>
>   ```csharp
>   object obj = new Person();
>   switch (obj)
>   {
>       case Person p:
>           //...
>           break;
>   }
>   ```
>
>   ```csharp
>   object obj = new Person();
>   switch (obj)
>   {
>       case Person:
>           //...
>           break;
>   }
>   ```
>
>   > Örnek
>   >
>   > ```csharp
>   > string GetProduct(IProduct p) => p switch
>   > {
>   >         Technologic _ => "Teknolojik",
>   >         Computer _ => "Bilgisayar",
>   >         Goggles _ => "Gözlük"
>   > };
>   > ```
>   >
>   > ```csharp
>   > string GetProduct(IProduct p) => p switch
>   > {
>   >         Technologic => "Teknolojik",
>   >         Computer => "Bilgisayar",
>   >         Goggles => "Gözlük"
>   > };
>   > ```
>
>   



#### Relational Patterns

> * Desenlerde <, >, <= ve >= operatörleri kullanılabilmekte ve belirli karşılaştırmalar hızlıca gerçekleştirilebilmektedir.
>
> ```csharp
> int number = 111;
> string result = number switch
> {
>         < 50 => "50'den küçük",
>         > 50 => "50'den büyük",
>         _ => "Hiçbiri"
> };
> ```
>
> ```csharp
> int number = 111;
> string result = number switch
> {
>         < 50 => "50'den küçük",
>         > 50 => "50'den büyük",
>         50 => "50'ye eşit"
> };
> ```
>
> 

##### Kritik

> Relational Pattern'dan önce switch sadece eşitlik durumuna bakarken C# 9.0'dan sonra diğer kıyaslamaları da yapabilmektedir.
>
> Dolayısıyla ileride mülakatta bir soru ile karşılaşırsak bunu da aklımızdan çıkartmamamız gerekir.

#### Logical Patterns

> and, or ve not gibi mantıksal operatörler kullanılabilmektedir.
>
> ```csharp
> string GetProduct(IProduct p) => p switch
> {
>         Technologic or Computer => "Teknolojik",
>         Goggles => "Gözlük"
> };
> ```
>
> Relational Pattern ile oldukça uyumludur.
>
> ```csharp
> int number = 60;
> string result = number switch
> {
>         > 10 and < 50 => "10'dan büyük 50'den küçük",
>         > 50 or < 100 and 60 => "50'den büyük veya 100'den küçük ve 60'a eşit",
>         not 51 => "51 değil"
> };
> ```
>
> 

#### Not Patterns

> not operatörünün kullanılabildiği bir desendir.
>
> ```csharp
> string GetProduct(IProduct p) => p switch
> {
>         Technologic => "Teknolojik",
>         Computer => "Bilgisayar",
>         not Goggles => "Gözlük"
> };
> ```
>
> ```csharp
> object obj = new Goggles();
> if (obj is not Technologic)
> {
>     //...
> }
> ```
>
> 
