# C# Notları (Tür Dönüşümleri (Type Conversion))

[TOC]



## Tür Dönüşümü Nedir? Neden Verilerin Türlerini Değiştirmek/Dönüştürmek İsteriz?

> Konumuzun mahiyeti şudur, varsayalım elimizde T1 türünde n isminde değerimiz olsun, bunu biz süreçte T2 türünde veriye dönüştürebiliyoruz.
>
> * Yazılım sürecinde elimizdeki değerlerin türlerini değiştirebilmekteyiz.
>
>   <img src ="https://imgur.com/Poj11oX.png" align=left>
>
> >  Peki bir yazılımcı neden verilerin türlerini değiştirmek/dönüştürmek isteyebilir?
> >
> > * Diyelim ki elimizde bir elma var, biz bunu elma türünde tutabiliriz ya da meyve türünde de tutabiliriz.
> >
> >   Bir objectte de tutabiliriz, nihayetinde boxing yapabiliriz.
> >
> >   Şimdi biz bunu yapabiliriz ama bunu kafamıza göre keyfimize gelirse mi yapacağız?
> >
> >   ​	Tabi ki de hayır, bir yazılımcı hiçbir şeyi durduk yere yapmaz!
> >
> >   Bu durumları örnek olaylarla inceleyelim;
> >
> >   1. Tür dönüşümleri elimizdeki verinin fıtratındaki/mahiyetindeki türe uygun işlemlere tabii tutabilmek için uygulanabilir.
> >
> >      <img src="https://imgur.com/T3b1wFp.png" align=left>
> >
> >   2. Farklı servislerden gelen değerleri uygun türe dönüştürmek isteyebiliriz.
> >
> >      <img src = "https://imgur.com/8GacEIV.png" align=left>
>
> **Dikkat:** Tür dönüşümlerinde amaç türü dönüştürmektir. Yani elimizdeki veriye uygun bir türe geçiş yapmaktır.
>
> * Elimizdeki veriyi uygun olmayan bir türe dönüştürmeye çalışırsak bu mümkün değildir! Hata verecektir.
>
> * Elimizdeki türe uygun dönüşüm yapılmalıdır. Elmayı armut olarak dönüştürmeyeceğiz.
>
> * Amaç: elimizdeki veriyi karşılayabilecek farklı bir türe dönüştürmektir.
>
>   <img src="https://imgur.com/FS2k12p.png" align=left><img src="https://imgur.com/aMyKKry.png">
>
>   

## Metinsel İfadelerin Diğer İfadelere Dönüştürülmesi

> Metinsel ifadeden kastımız string türündeki herhangi bir ifade.
>
> > Tür dönüşümlerinde dikkat edilmesi gereken tek bir husus vardır ki, o da; 
> >
> > *dönüşüm yapılacak verinin türüne uygun bir hedef tür belirlenmelidir.*
>
> 

### Parse Metodu

> ***Parse metodu sadece string verileri hedef türe dönüştürürken kullanılır!***

> > Örnek 1
> >
> > ```csharp
> > //String türde x değişkeni ile aritmatik işlem yapmak istiyoruz
> > string x = "123";
> > //Console.WriteLine(x * 5); //-> Metinsel olduğu için 5 ile çarpamıyoruz.
> > Console.WriteLine(short.Parse(x) * 5); //-> tür.Parse(degiskenAdi) ile dönüşümü yaptık.
> > //veya
> > short x2 = short.Parse(x);
> > Console.WriteLine(x2 * 5);
> > ```
>
> > Örnek 2 : Tür Hatalı
> >
> > ```csharp
> > string a = "Ahmet";
> > int a2 = int.Parse(a);
> > Console.WriteLine(a2);
> > ```
> >
> > * Compiler derlerken hata vermez, buradaki dönüşüm runtime'da olur ve runtime'da hata verir.
>
> > Örnek 3 
> >
> > ```csharp
> > string medeniHal = "Evli";
> > bool medeniHal2 = bool.Parse(medeniHal);
> > Console.WriteLine(medeniHal2);
> > ```
> >
> > Mantıksal hata yaptık. *Beşeri hayatta kullandığımız Evli'yi true yada false olarak düşünmeyin.*
> >
> > Burada bool türünü karşılayabilecek bir değer olsaydı dönüşümü yapabilecekti.
> >
> > ```csharp
> > string medeniHal = "true";
> > bool medeniHal2 = bool.Parse(medeniHal);
> > Console.WriteLine(medeniHal2);
> > ```
>
> > Örnek 4
> >
> > ```csharp
> > string x = "ab";
> > char x2 = char.Parse(x);
> > ```
> >
> > char birden fazla karakter tutamayacağı için hata verecektir.
>
> 



### Convert Fonksiyonu

> *Parse metodundaki gibi sadece string verileri diğer türlere dönüştürmüyor.*
>
> ***Diğer türleri de birbirleri arasında dönüştürüyor.***
>
> Dönüştürebildiği türleri visual studio ortamında şu şekilde görebilirsiniz.
>
> <img src="https://imgur.com/D3CO8Jr.png" align=left>

> > Örnek 1
> >
> > ```csharp
> > string x = "25";
> > int x2 = Convert.ToInt32(x);
> > ```
> >
> > Parse'da anlattıklarımız burada da geçerli, türüne uygun bir dönüştürmeye dikkat edeceğiz.
>
> > Örnek 2
> >
> > ```csharp
> > string x = "3.14";
> > double d = Convert.ToDouble(x);
> > Console.WriteLine(d);
> > //Çıktı : 314
> > ```
> >
> > ```csharp
> > string x = "3,14";
> > double d = Convert.ToDouble(x);
> > Console.WriteLine(d);
> > //Çıktı : 3,14
> > ```
> >
>
> 



## Diğer İfadelerin Metinsel İfadelere Dönüştürülmesi

> **Convert fonksiyonu** ile akılımıza gelen bütün verileri string'e dönüştürebiliriz.
>
> > Örnek
> >
> > ```csharp
> > int a = 25;
> > string a2 = Contert.ToString(a);
> > ```
> >
>
> 



### ToString Fonksiyonu

> Diğer ifadelerin metinsel ifadelere hızlı bir şekilde dönüştürmemizi sağlayan ToString fonksiyonu mevcuttur.
>
> > Örnek
> >
> > ```csharp
> > //ToString fonksiyonu tüm türlerde mevcuttur.
> > float f = 35;
> > string f2 = f.ToString();
> > ```
> >
>
> 



## Sayısal İfadelerin Kendi Aralarında Tür Dönüşümü

> Sayısal ifadeler kendi aralarında dönüşüm yaparken farklı bir derinlikte kontrol gerektirebiliyor.
>
> <img src="https://imgur.com/k23eyIK.png" align=left>
>
> > Bir sayısal değer **kendi türünden daha büyük değer aralığına** sahip olan diğer türlere dönüştürülürken burada herhangi bir işlem yapmamıza gerek kalmayacağı için bu dönüştürme işlemine **bilinçsiz tür dönüşümü** denir.
>
> > Bir sayısal değer ***kendi türünden daha küçük değer aralığına** sahip olan diğer türlere dönüştürülürken hedef türün ilgili veriyi karşılayamama riskinden dolayı buradaki işlemi bilinçli yapmamız gerekecek, haliyle buna **bilinçli tür dönüşümü** diyeceğiz.
>
> > Örnek
> >
> > integer türünde değeri 63000 olan bir değişkenimiz olsun.
> >
> > > Max-Min Değer aralıkları için : Değişkenler konusu altındaki [Hangi türlerle bu bildirimde bulunuyoruz?](./2-Değişkenler.md##hangi-türlerle-bu-bildirimde-bulunuyoruz?) başlığımıza bir göz atmamız gerekir.
> >
> > int max-min değer aralığı: -2.147.483.648 ile 2.147.483.647 arası
> >
> > Decimal,double,float,long içerisinde integer'ı kapsadığı için herhangi bir işlem yapmamız gerekmez dolayısıyla bilinçsiz tür dönüşümü gerçekleşir.
> >
> > Ancak ushort,byte,sbyte türlerine dönüştürmek istersek yazılım bize, "buna ben müsade etmem, sen kendi iradenle yapacaksın, senin sorumluluğunda" der. Bu noktada biz bilinçli olarak tür dönüşümünü gerçekleştiririz.
>
> > Bir sayısal türün alt türüne bir veriyi dönüştürdüğümüzde eğer ki veri o **alt türün değer aralığına girmiyorsa veri kaybı söz konusu olacaktır!**
>
> 



### Bilinçsiz Tür Dönüşümü

> Örnek
>
> ```csharp
> int a = 3000;
> float f = a; //Şuanda burada bir tür dönüşümü söz konusudur. Lakin buradaki tür dönüşümü bizim kararımızla/bilincimizle yaptığımız bir dönüşüm değildir. Compiler buradaki sorumluluğu üstlenecektir.
> ```



### Bilinçli Tür Dönüşümü

> Compiler değerden bağımsız türün kapasitesine odaklandığı için, kendisinden daha dar bir türe dönüştürmek istediğimiz değişkende bize hata verecektir.
>
> ```csharp
> int x = 3000;
> short y = x; //Hata verir.
> ```
>
> **Cast Operatörü**
>
> > Boxing, Unboxing işlemlerinde tanıştığımız cast operatörü; bilinçli tür dönüşümünde de sayısal türleri kendi aralarında dönüştürürken iradeli bir şekilde bu işlemin yapılmasını sağlayan bir operatördür.
>
> ```csharp
> int x = 3000;
> short y = (short)x; //-> Bilinçli tür dönüşümü
> ```
>
> 

> Veri Kayınba Örnek
>
> ```csharp
> int x = 60000;
> short y = (short)x;
> Console.WriteLine(y);
> //Çıktı: -5536
> byte z = (byte)x; 
> Console.WriteLine(z);
> //Çıktı: 96 //0 ile 256 arasında değer alan byte
> ```
>



### Kritik

> Diyelim ki mülakattayız ve bize "şu kodda bilinçli tür dönüşümü mü, bilinçsiz tür dönüşümü mü yapıldı?" diye bir soruyla karşılaştık.
>
> ```csharp
> int a = 3000;
> short s = (byte)a;
> ```
>
> > Burada elimizdeki a değişkenine cast operatörü ile int'ten byte türüne bilinçli bir dönüşüm yapılmıştır. `(byte)a`
> >
> >  `(byte)a ` artık byte türünde olacağı için short'a atanırken de bilinçsiz tür dönüşümü gerçekleşecektir.
>
> 

### checked

> checked : Bilinçli tür dönüşümü esnasında bir veri kaybı söz konusu olursa eğer, runtime'da bizleri uyaracak olan bir kontrol mekanizmasıdır.
>
> ```csharp
> checked
> {
> 	int a = 500; //0~255 arasında bir değer olsaydı, uyarmayacaktı.
> 	byte b = (byte)a;
> 	Console.WriteLine(b);
> }
> ```
>
> 

### unchecked

> unchecked : Bilinçli tür dönüşümü esnasında bir veri kaybı söz konusu olursa, runtime'da veri kaybını göz ardı edecek ve çalışacaktır.
>
> * Normal bir kod bloğu default olarak unchecked'dir.
>
> ```csharp
> unchecked
> {
>     int a = 500;
>     byte b = (byte)a;
>     Console.WriteLine(b);
> }
> ```
>



## bool Türünün Sayısal Türe Dönüştürülmesi

> Elimizdeki mantıksal bir değeri herhangi bir sayısal değere Convert edersek ilgili değerin mantıksal karşılığını elde edebiliriz...
>
> True : 1, False : 0 olarak dönüştürecektir.
>
> ```csharp
> bool b = true;
> int i = Convert.ToInt32(b);
> Console.WriteLine(i);
> ```
>
> Sayısal türden kastımız sadece integer değildir, herhangi bir sayısal türe dönüştürülebilir.
>
> 



## Sayısal Türlerin bool Türüne Dönüştürülmesi

> Tür dönüşümlerinde dönüştürülecek türün hedef türe uygun olması gerekiyordu. Burada bir istisna var.
>
> Normalde, 0 'ın false 'a ; 1 'in de true 'ya eşit olması ve geri kalanının mümkün olmaması gerekmektedir.
>
> Halbuki burada 0'ın dışındaki tüm değerler true olarak kabul edilmesi bir istisnadır. 
>
> ```csharp
> int i = -123;
> bool b = Convert.ToBoolean(i);
> Console.WriteLine(b);
> ```
>



## char Türünün Sayısal Türe Dönüştürülmesi

**ASCII** : Bilgisayardaki her bir karakterin sayısal bir karşılığı vardır. Bu sayısal değerlere ASCII kaynak kodu denmektedir.

<img src="https://www.alpharithms.com/s3/assets/img/ascii-chart/ascii-table-alpharithms-scaled.jpg" align=left>

Yani anlayacağınız klavye üzerindeki bütün tuş kombinasyonlarının esasında arka planda, ASCII kaynak kodda bir karşılığı vardır.

> Elimizde char türünde a değişkeni olsun, eğer ki biz bu değişkeni int _a değişkenine cast edersek bize ascii kaynak kodunu verecektir.
>
> ```csharp
> char a = 'a';
> int _a = (int)a;
> Console.WriteLine(_a); //Çıktı : 97
> ```
>
> **Cast Operatörü** : Unboxing, bilinçli tür dönüşümü ve burada da kullanıyoruz. Yani bir operatör yeri ve konumuna göre farklı sorumluluklar üstlenebiliyor.
>
> *Tüm tamsayı değerleri üzerinde bu işlemi gerçekleştirebilmekteyiz.*
>
> 



## Sayısal Türlerin char Türüne Dönüştürülmesi

> Diyelim ki;
>
> ```csharp
> int oascii = 111;
> int Oascii = 79;
> Console.WriteLine((char)oascii);
> Console.WriteLine((char)Oascii);
> ```
>
> Elimizdeki herhangi bir tamsayısal değeri, char'a cast edersek bize ascii karşılığı olan karakteri bizlere getirecektir.