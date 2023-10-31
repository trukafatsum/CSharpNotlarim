# C# Notları (Operatörler)

[TOC]



## Programlamada Operatör Nedir?

> ***Operatörler belirli bir sorumluluğu /işi /operasyonu üstlenen sembolik veya metinsel yapılardır. Bizim yerimize o sorumluluğu icra ederler.***
>
> > * Örnek üzerinden ele almamız gerekirse, aritmetik işlemlerde kullandığımız + operatörü ile toplama işlemi  yapabiliyorsak, diğer operatörlerle de belirli sorumlulukları gerçekleştirebilmekteyiz.
> >
> > * Bir metafor üzerinden ele almamız gerekirse de; nasıl ki bir karakollarda planlamayı yapanlar stratejisyenler ise
> >
> >   operasyonu genellikle özel harekatlar yapıyor. Özel harekatlar, operatörlerdir. İşte orada sorumluluğu üstlenen, stratejik kararda olması gerekenleri yapanlar nasıl ki özel harekatlarsa, bizim de yazılımdaki özel harekatlarımız, operatörlerimiz olacak.
> >
> >   Örneğin ++ operatörünü kullanacağız, bizim yerimize 1 arttırıyor vs..
>
> 



### Operatör Okur Yazarlığı

> Operatör konusunu direk kitaptan ya da kaynaktan araştırdığımızda direkt konuya girildiğini, tanımlandığını ve kullanıldığını görürüz.
>
> Halbuki kodun semantiği genişledikçe, zorlaştıkça orada kullanılan operatörler, yapısal olarak zor okunaklı hale gelebiliyor. Dolayısıyla ilk önce operatörün kullanımından öte okuryazarlığında biraz gelişme, kuramsal açıdan değerlendirme gerekiyor. Onun için biz operatörlerin bir yazılımsal semantiği açısından nasıl bir kullanıma, işleyişe sahip olduğunu inceleyeceğiz.

> *Operatörler; genellikle iki değer arasında matematiksel, mantıksal veya farklı bir işlemsel görev/operasyon yapan yapılardır.*
>
> Operatörler genellikle yaptıkları işlem neticesinde bir sonuç dönerler. Tabi ki bu iki değer semantik açıdan her zaman operatörün sağında ve solunda olmak zorunda değil. Çünkü bu durumu cast operatörünü görmüştük. İki değer arasında bağıntı yapan yapılardır diye de düşünebiliriz.
>
> *Operatörler kullanılırken geriye dönüş değerlerine dikkat edilmesi gerekmektedir.*
>
> <img src="https://imgur.com/A58PVcc.png" align=left>
>
> 



### Neleri göreceğiz?

* Aritmetik operatörler
* Karşılaştırma operatörleri
* Mantıksal operatörler

* Diğer(Özel işlemler) operatörler



## Aritmetik Operatörler

```csharp
// + -> toplama
// - -> çıkarma
// * -> çarpma
// / -> bölme
// % -> mod : belki bilmeyebilirsiniz, bir sayıyı başka bir sayıya bölerken kalanı veren operatördür
```



### Aritmetik Operatörler Nelerdir? Geriye Dönüş Değeri Nedir?

> Aritmetik operatörler, iki sayısal değer üzerinde işlem yapan operatöler oldukları için işlem neticesinde geriye "uygun türde" sonuç dönerler.

> Örnek, iki sayıyı toplamak istiyoruz;
>
> ```csharp
> 3 + 5
> ```
>
> Farenin imlecini operatörün üstüne getirirsek,
>
> <img src="https://imgur.com/Ppo7fHW.png" align=left>
>
> soluna ve sağına vermiş olduğumuz iki değer üzerinde işlem yapacağını ve işlemin sonucunda integer türünde bir değer döndüreceğini söylüyor.
>
> > İnceleme 1
> >
> > Bu durumda biz ne yapıyoruz;
> >
> > ```csharp
> > int sonuc = 3 + 5 ; 
> > ```
> >
> > yazarak konsepti kapatıyoruz.
>
> > İnceleme 2
> >
> > ```csharp
> > int x = 3, y = 5;
> > int sonuc = x * y;
> > ```
> >
> > <img src="https://imgur.com/KfznhwG.png" align=left>
> >
> > soldaki ve sağdaki değer üzerinde işlem yapıp, integer türünde değer döndüreceğini söylüyor.
>
> *Aynı türde olan sayısal değer üzerinde işlem yaparken sonuç türü aynı olacaktır.*
>
> > İnceleme 3
> >
> > ```csharp
> > double s1 = 123;
> > double s2 = 321;
> > double sonuc = s1 + s2;
> > ```
> >
> > <img src="https://imgur.com/FTgwBP7.png" align=left>
>
> 



### İki Farklı Tür Üzerinde Aritmetik İşlem

**(int) * (double) =? **

> İki farklı türde sayısal değerler üzerinde yapılan aritmetik işlem neticesinde sonuç büyük olan türde dönecektir.
>
> ```csharp
> int s1 = 10;
> double s2 = 5;
> double sonuc = s1 + s2 ;
> ```
>
> **Dikkat :** Aritmetik operatörlerde küçük olan tür, büyük olan türe bilinçsiz bir şekilde dönüştürülerek o şekilde hesap yapılır!
>
> Bu sebeple sonuç büyük olan türde elde edilecektir/edilmektedir.
>
> <img src="https://imgur.com/bL2cNLM.png" align=left>
>
> 



**(byte) * (int) =?**

> Büyük olan türde sonuç dönmesini bekliyoruz.
>
> ```csharp
> int s1 = 3;
> byte s2 = 123;
> int sonuc = s1 - s2;
> ```
>
> <img src="https://imgur.com/RmIijj5.png" align=left>
>
> 



**(byte) * (byte) =?** *(İstisna - Mülakat!)*

> Normalde iki aynı türdeki sayısal değer üzerinde yapılan aritmetik işlem neticesinde sonuç aynı türde dönecekken, ***bu iki değer byte ise sonuç her daim int dönecektir.***
>
> ```csharp
> byte s1 = 10;
> byte s2 = 5;
> int sonuc = s1 - s2;
> ```
>
> <img src="https://imgur.com/OEpcJ0e.png" align=left>
>
> ***İstisnadır, mülakat sorusu olabilir***
>
> 



### Matematiksel İşlemler (Öncelik Sırası)

> Gündelik hayatta bildiğimiz, kullandığımız matematiksel işlemlerdeki öncelik sırası aynı şekilde yazılımda da geçerlidir.

## Karşılaştırma Operatörleri

> İki sayısal değer arasında büyüklük, küçüklük ve eşitlik durumuna göre karşılaştırma yapan operatörlerdir.
>
> Metinsel ifadelerde de karşılaştırma operatörlerini kullanabiliyoruz, onu da ilgili başlık altında değerlendireceğiz.
>
> ```csharp
> // < : Küçüklük operatörü
> // > : Büyüklük operatörü
> // <= : Küçük veya eşitlik operatörü
> // >= : Büyük veya eşitlik operatörü
> // ==  : Eşitlik operatörü
> ```



### Karşılaştırma Operatörleri Geriye Dönüş Değeri

> Karşılaştırma operatörleri geriye her daim bool türde bir değer döndürecektir.
>
> ```csharp
> int a = 15;
> int b = 20;
> bool sonuc = a >= b;
> ```
>
> <img src="https://imgur.com/X6NQPCC.png" align=left>
>
> 



## Mantıksal Operatörler

> Tüm şartları değerlendirip, kendine göre sonuç döndüren operatörlerdir.
>
> ```csharp
> //ve &&
> //veya ||
> //ya da ^
> ```
>
> * ve(&&) operatörü, tüm şartların yerine getirilmiş olmasını ister.
> * veya(||) operatörü, şartlardan en az bir tanesinin yerine getirilmiş olması yeterlidir.
> * ya da (^) operatörü, şartlardan bir tanesinin kesinlikle bir tanesinin yerine getirilmesini ister.
>
> 



### Mantıksal Operatörler Kullanım Mantığı *(Solu Sağı bool olmalı)*

> Mantıksal operatörler, mantıksal değerler üzerinde kullanılır.
>
> Sağdaki ve soldaki değerler kesinlikle boolean olmak zorundadır.
>
> > Örnek
> >
> > ```csharp
> > bool patates = true, kofte = false;
> > bool sonuc1 = patates && kofte;
> > bool sonuc2 = patates || kofte;
> > bool sonuc3 = patates ^ kofte;
> > ```
> >
> > Mantıksal operatörler geriye bool sonuç dönerler.
>
> 



### Mantıksal Operatörler  Geriye Dönüş Değeri

> ve (&&)
>
> ```csharp
> Console.WriteLine(true && true); //Geriye dönüş değeri : true
> Console.WriteLine(true && false); //Geriye dönüş değeri : false
> Console.WriteLine(false && false); //Geriye dönüş değeri : false
> Console.WriteLine(false && true); //Geriye dönüş değeri : false
> ```

> veya(||)
>
> ```csharp
> Console.WriteLine(true || true); //Geriye dönüş değeri : true
> Console.WriteLine(true || false); //Geriye dönüş değeri : true
> Console.WriteLine(false || false); //Geriye dönüş değeri : false
> Console.WriteLine(false || true); //Geriye dönüş değeri : true
> ```

> ya da(^)
>
> ```csharp
> Console.WriteLine(true ^ true); //Geriye dönüş değeri : false
> Console.WriteLine(true ^ false); //Geriye dönüş değeri : true
> Console.WriteLine(false ^ false); //Geriye dönüş değeri : false
> Console.WriteLine(false ^ true); //Geriye dönüş değeri : true
> ```

> Örnek
>
> ```csharp
> Console.WriteLine(((true && true)||false && ((true ^ false) && false)|| true));
> ```
>
> <img src="https://imgur.com/Qj1L427.png" align=left>
>
> Sonuç olarak *True* çıkacaktır.
>
> 



## Arttırma Azaltma Operatörleri

> ++ arttırma operatörü: Sadece 1 arttırır.
>
> -- azaltma operatörü: Sadece 1 azaltır.
>
> İşlem neticesinde değişkenin değerini döner.
>
> ```csharp
> // ++
> int i = 5;
> i++; // i = i + 1; kombinasyonunun yerine operatör kullanabiliriz
> //++i
> Console.WriteLine(i); //Sonuç 6 gelecektir.
> ```
>
> Sağında veya solunda olması durumunu inceleyelim.
>
> > Örnek 1
> >
> > ```csharp
> > int i = 5;
> > //++i -> Öncelikle i değerini 1 arttırır, ardından i değerini döndürür.
> > //i++ -> Önce i değerini döndürür, sonra 1 arttırır.
> > Console.WriteLine(i++); // Çıktı : 5 | Bellek : 6
> > Console.WriteLine(++i); // Çıktı : 7 | Bellek : 7
> > ```
>
> > Örnek 2
> >
> > ```csharp
> > int a = 5;
> > int b = a++;
> > Console.WriteLine(a); // Çıktı : 6
> > Console.WriteLine(b); // Çıktı : 5
> > ```
> >
> > <img src="https://imgur.com/C6NSzrs.png" align=left>
>
> > Örnek 3
> >
> > ```csharp
> > int i1 = 5;
> > int i2 = ++i1;
> > int i3 = i1;
> > i2 = ++i2; //++i2 ile aynı, atama operatörü burada yersiz olmuş. :)
> > Console.WriteLine(i1); // Çıktı : 6
> > Console.WriteLine(i2); // Çıktı : 7
> > Console.WriteLine(i3); // Çıktı : 6
> > ```
> >
> > <img src="https://imgur.com/CVQVGsi.png" align=left>
>
> Birebir hepsi -- için de geçerlidir.
>
> 



## Üzerine Ekleme Yığma Operatörleri

```csharp
// +=
// -=
// *=
// /=
// %=
```

> Arttırma, azaltma operatörlerine benzer mantıkta çalışmaktadır.
>
> Farkı sadece 1 arttırmak veya 1 azaltmak için değil, isteinildiği kadar arttırmak ve azaltmak için vb. işlemlerde pratik kullanımlar için vardır.
>
> ```csharp
> //Prototip
> int i =5;
> i += 3; //-> i = i + 3;
> i -= 3; //-> i = i - 3;
> i *= 3; //-> i = i * 3;
> i /= 3; //-> i = i / 3;
> i %= 3; //-> i = i % 3;
> ```



## Metinsel İfadelerde Kullanılan Operatörler

### '+' Operatörü

> Metinsel ifadeler + operatörüyle yanyana birleştirilebilirler.
>
> ```csharp
> int a = 5, b = 3;
> Console.WriteLine(a + b); //Eğer ki sayısal ifadelerde kullanmış olsaydık, aritmetik işlem gerçekleşecekti.
> 
> string c = "Ahmet", d = "Mehmet";
> Console.WriteLine(a + c); // Çıktı : 5Ahmet
> Console.WriteLine(b + d); // Çıktı : 3Mehmet
> Console.WriteLine(c + d); // Çıktı : AhmetMehmet
> Console.WriteLine(a + b + c); // Çıktı : 8Ahmet
> Console.WriteLine(a + c + b); // Çıktı : 5Ahmet3
> ```
>
> String bir değer ile toplanacak olan sayısal bir değeri object olarak görür.
>
> ```csharp
> int a = 5;
> string b = "abc";
> string sonuc = a + b;
> ```
>
> <img src="https://imgur.com/mv9ZbIY.png" align=left>

> Tür dönüşümlerinde herhangi bir değeri string'e dönüştürebilmek için .ToString fonksiyonu kullanıyorduk.
>
> Ayrıca ilgili türü string'e dönüştürebilmek için string bir ifade ile + operatörüne tabii tutulması yeterli olacaktır.
>
> 



### '+=' Operatörü

> Metinsel ifadelerde += operatörünü kullanabilmekteyiz, yani metinsel ifadeler birbirleri üzerine yığılabilirler.
>
> ```csharp
> string a = "ahmet";
> string b = "mehmet";
> 
> a += b; //a = a + b; // Çıktı : ahmetmehmet
> Console.WriteLine(a);
> ```
>
> 

### '==' Operatörü

> Metinsel ifadelerde == operatörü ile eşitlik durumunu karşılaştırabiliriz.
>
> > Örnek
> >
> > a ile b içerik olarak eşit olma durumu karşılaştırılacaktır ve sonucunda *bool* dönecektir.
> >
> > ```csharp
> > string a = "Ahmet";
> > string b = "Mehmet";
> > 
> > bool sonuc = a == b;
> > Console.WriteLine(sonuc);//Çıktı : False | Eğer ki hem a hem b aynı metinsel ifade olsaydı True olacaktı.
> > ```
>
> 

### '!=' Operatörü

> Metinsel ifadelerde eşitlik operatörünün zıttıdır. Eşit değil mi diye sormak istediğimizde kullanacağımız != operatörüdür.
>
> > Örnek
> >
> > a ile b içerik olarak eşit olmama durumu karşılaştırılacaktır ve sonucunda *bool* dönecektir.
> >
> > ```csharp
> > string a = "Ahmet";
> > string b = "Mehmet";
> > 
> > bool sonuc = a != b; //Eşit değilmi sorusu sorulur. Haliyle eşit değil ve True sonucu döner.
> > Console.WriteLine(sonuc); // Çıktı : True
> > ```
>
> 



## Diğer Operatörler

### ! Operatörü

> Ünlem ! Operatörü programlamada, tersi, değil, olumsuzluk anlamında kullanılır.
>
> 1. Kullanım : Mantıksal yapılarda olumsuzluk ifade eder.
>
> ```csharp
> Console.WriteLine(true); //Çıktı : True
> Console.WriteLine(!true); // Çıktı : False
> ```
>
> 2. Kullanım : Bir diğer kullanımı ==(Eşitlik) operatörünün başına geldiğinde -> !=(eşit değillik) durumuna gelir.
>
> ```csharp
> Console.WriteLine(true!=false); // Çıktı : True
> int i = 3;
> int i2 = 5;
> Console.WriteLine(i == i2); // Çıktı : False
> Console.WriteLine(i != i2); // Çıktı : True
> Console.WriteLine(!(i == i2)); // Çıktı : True
> ```
>
> > != bu operatörün dışında, sade ve sadece mantıksal değerlerin yanında kullanılabilir.
> >
> > Örnek
> >
> > ```csharp
> > // !(.......bool.......)
> > ```
>
> 3.Kullanım : Null References (C# 8.0) ileride göreceğiz..
>
> 



### Ternary  Operatörü

> Ternary operatörü : Şarta bağlı değer döndüren bir operatördür.
>
> * Bir değişkene / metoda / property'e değer atarken, eğer ki bu değer şarta göre fark edecekse, tek satırda ya da satır bazlı bu şart kontrolünü yaparak duruma göre değeri döndürmemizi sağlayan bir kalıpsal operatördür.
>
> > <img src="https://imgur.com/u4wGS6E.png" align=left>
> >
> > Ternary operatörü ile işlemimizi gerçekleştirelim
> >
> > ```csharp
> > bool medeniHal = true;
> > //string mesaj = ? : ;
> > string mesaj = medeniHal == true ? "Evlilere kampanya.." : "Bekarlara kampanya..";
> > Console.WriteLine(mesaj);
> > ```
>
> 



#### Birden Fazla Condition Uygulamak

> Örnek
>
> ```csharp
> int yas = 25;
> // Yaşı: 25'den küçük olanlara A, 25 olanlara B ve 25'den büyük olanlara C değerini döndüren ternary operatörünü oluşturalım.
> 
> char sonuc = yas < 25 ? 'A' : (yas == 25 ? 'B' : 'C');
> Console.WriteLine(sonuc);
> ```
>
> 



#### Örnek 1

> Kullanıcı tarafından girilen sayının aşağıdaki önergelere göre hesabını gerçekleştiren kodu geliştiriniz.
>
> ```csharp
> /*
> 	sayı < 3                    => sayı * 5
> 	sayı > 3 && sayı < 9        => sayı * 3
> 	sayı >= 9 && sayı % 2 == 0  => sayı * 10
> 	sayı % 2 == 1               => sayı
> 	hiçbiri değilse             => -1
> */
> 
> Console.WriteLine("Lütfen bir sayı giriniz:");
> int sayi = int.Parse(Console.ReadLine()); 
> 
> //--------- Ternary ? : operatörü ile ----------//
> int sonuc = sayi < 3 ? sayi * 5 :
> (sayi > 3 && sayi < 9 ? sayi * 3 :
> (sayi >= 9 && sayi % 2 == 0) ? sayi * 10 :
> (sayi % 2 == 1 ? sayi : -1));
> Console.WriteLine("Sonuç : " + sonuc );
> 
> //----------------------IF Else ile yazmış olsaydık -----------------------//
> if (sayi < 3 )
> {
>     sonuc = sayi * 5;
> }
> else if (sayi >= 9 && sayi % 2 == 0)
> {
>     sonuc = sayi * 10;
> }
> else if (sayi > 3 && sayi < 9)
> {
>     sonuc = sayi * 3;
> }
> else if (sayi % 2 == 1)
> {
>     sonuc = sayi;
> }
> else
> {
>     sonuc = -1;
> }
> Console.WriteLine("If else Sonuç : " + sonuc);
> ```
>
> 

#### Örnek 2

> Hava durumunu tutan string değişkenin değerine göre aşağıdaki önergeleri uygulayan programı yazınız.
>
> ```csharp
> /*
> "Yağmurlu" => "Şemsiye almalısın"
> "Güneşli"  => "Bol bol d vitamini alman dileğiyle.."
> "Kapalı"   => "Yağmur yağabilir"
> */
> string havaDurumu = "Kapalı";
> 
> Console.WriteLine(havaDurumu == "Yağmurlu" ? "Şemsiye almalısın" : (havaDurumu == "Güneşli" ? "Bol bol d vitamini alman dileğiyle.." : "Yağmur yağabilir."));
> ```



### Atama (Assign) Operatörü

> = operatörü : sol taraftaki değişkene sağ taraftaki değeri atamamızı sağlayan operatördür. Sadece değişken değil, field, property vs. de durum aynı şekildedir.
>
> Değişkeni operatörün sağında çağırıyorsak değeri, solunda çağırıyorsak kendisi gelecektir.
>
> İleride yani referans türlü değişkenlerde atama operatörünün sorumluluğunu değişip referans etme operatörü olduğunu konuşacağız.
>
> 



### .(Member Access - Üye Erişim) Operatörü

> . (Member Access) : elimizdeki bir değerin türüne uygun elemanlarını/ fonksiyonlarını/ metotlarını/ propertylerini/ field; erişmemizi, çalıştırmamızı, çağırmamızı sağlayan bir operatördür.
>
> *Member access kodun devamını getirir.*
>
> ```csharp
> int i;
> i.
> ```
>
> <img src= "https://imgur.com/17I8Gxb.png" align=left>
>
> 



### Cast Operatörü

> Şuana kadar birçok kez kullandığımız cast operatörünü ele alalım.
>
> 1. Boxing yapılan değeri Unboxing yaparken kullanıyorduk.
>
>    ```csharp
>    object x = 123; //Boxing
>    int x2 = (int)x; //Unboxing
>    ```
>
> 2. Bilinçli Tür Dönüşümünde kullanıyorduk.
>
>    ```csharp
>    int a = 5;
>    short b = (short)a;//Bilinçli Tür Dönüşümü
>    ```
>
> 3. Char -> int | int -> Char (ASCII) dönüşümlerinde kullanıyorduk.
>
>    ```csharp
>    int ascii = 93;
>    char c = (char)ascii;
>    ```
>
> Genellikle tür dönüşümlerinde kullanılan bir operatördür.
>
> *İleride polimorifzm durumunda base class referansıyla işaretlenen bir nesneyi kendi türünde de elde edebilmemizi sağlamaktadır.*
>
> 



### sizeof Operatörü

> sizeof Operatörü : Metinsel bir keyworddür. Verilen türün bellekte kaç byte'lık yer kapladığını integer olarak geriye döndürür.
>
> ```csharp
> Console.WriteLine("int : " + sizeof(int));
> Console.WriteLine("long : " + sizeof(long));
> Console.WriteLine("decimal : " + sizeof(decimal));
> ```



### typeof Operatörü

> typeof Operatörü : Verilen türün/değerin type'ını/türünü getirir.
>
> O tür ile ilgili bilgileri edinmek için kullanılan bir operatördür.
>
> ```csharp
> Type t = typeof(int); // int türüne ait tüm bilgiler burada t değişkenine atanmıştır.
> Console.WriteLine(t.Name);
> Console.WriteLine(t.IsPrimitive);
> Console.WriteLine(t.IsClass);
> Console.WriteLine(t.IsValueType);
> ```
>
> *İleride (ileri düzey programlama) reflection dediğimiz bir konuda elimizdeki bir türün reflectionına girmek için kullanıldığını göreceğiz.*
>
> 



### default Operatörü

> default Operatörü : Belirtilen türün default değerini döndüren operatördür.
>
> Default değer ne demektir? Default değerler, her tür için yazılım tarafında tanımlanmış bir varsayılan değer demektir.
>
> ```csharp
> //sayisal  = 0
> //bool     = false
> //string   = null
> //char     = \0
> //referans = null
> Console.WriteLine(decimal);
> Console.WriteLine(string); // değersiz null oldukları için NULL diye yazmayacaktır.
> Console.WriteLine(Program); // değersiz null oldukları için NULL diye yazmayacaktır.
> Console.WriteLine(short);
> Console.WriteLine(byte);
> 
> int a1 = default;
> int a2 = default(int);// Her iki kullanımda aynıdır.
> ```



### is Operatörü

> is Operatörü : Boxing'e tabii tutulmuş bir değerin öz türünü öğrenebilmek/check edebilmek / kontrol edebilmek için kullanılan bir operatördür.
>
> is operatörü denetleme neticesinde değeri true ya da false olarak döndürecektir. (bool dönecektir)
>
> ```csharp
> object x = true; //Boxing
> Console.WriteLine(x is bool);
> Console.WriteLine(x is int);
> Console.WriteLine(x is Program);
> ```
>
> *İleride if yapılanmasında vs. çok tercih ettiğimiz bir operatör olacaktır.*
>
> *OOP yapılanmasında polimorfizm is operatörüyle kalıtımsal durumlardaki nesnelerin türlerinide öğrenebileceğiz.*
>
> 



### is null Operatörü

> is null Operatörü : Bir değişkenin değerinin null olup olmamasını kontrol eden ve geriye sonuç olarak bool türde bir değer döndüren operatördür.
>
> ```csharp
> string a = "qwerty";
> Console.WriteLine(a is null); //False
> a = null;
> Console.WriteLine(a is null); //True
> ```
>
> *is null operatörünü sadece null olabilen türlerde kullanabilmekteyiz.*
>
> Değer türlü değişkenler : not nullable, null olamayan değişkenlerdir.
>
> Referans türlü değişkenler : nullable, null olabilien değişkenlerdir.
>
> > Değer türlü değişkenlerde kullanılamaz.
> >
> > ```csharp
> > int b = 123;
> > Console.WriteLine (b is null); //Compiler hata verecektir.
> > ```
>
> 



### is not null Operatörü

> is not null Operatörü : Elimizdeki değerin null olup olmamasıyla ilgilenmekte ve geriye bool türde sonuç döndürmektedir.
>
> is null operatörünün tersidir.
>
> ```csharp
> string a = null;
> Console.WriteLine(a is not null); //False
> ```
>
> *is not null operatörünü sadece null olabilen türlerde kullanabilmekteyiz.*
>
> 



### as Operatörü

> as Operatörü : Cast operatörünün Unboxing işlemine alternatif olarak üretilmiş bir operatördür.
>
> <img src="https://imgur.com/95xG6XB.png" align=left>
>
> as Operatöründe;
>
> * as operatöründe as edilecek tür uygunsa unboxing işlemi başarıyla gerçekleşir, tür uygun değilse hata vermez, null değer döndürür.
> * as operatörünü türün uygun olmadığı taktirde geriye null döndüreceği için nullable türlü değişkenlerde kullanılabilir.
>
> > Cast Operatöründe Örnek
> >
> > ```csharp
> > //Cast Operatöründe;
> > object x = "Ahmet"; //Boxing
> > string x2 = (string)x; //Unboxing işlemi gerçekleşir.
> > Console.WriteLine(x2);
> > ```
> >
> > 
>
> > as Operatöründe Örnek
> >
> > ```csharp
> > //as Operatöründe;
> > object x = "Ahmet";
> > string y = x as string;
> > Console.WriteLine(y);
> > //int y = x as int; //-> int değer türlü değişken yani not nullable olduğu için compiler hata verir.
> > ```
> >
> > 
>
> *Genellikle OOP'de kullanılan bir operatördür.*
>
> 



### ?(Nullable) Operatörü

> ? (Nullable) Operatörü : 
>
> * C# Programlama dilinde değer türlü değişkenler normal şartlarda null değer alamazlar (Not nullable)
>
>   Bir değer türlü değişkenin null değer alabilmesi için (yani nullable olabilmesi için) ? operatörünün kullanılması gerekmektedir.
>
> > Örnek
> >
> > ```csharp
> > int? a = null;
> > bool? b = null; //null dışında kendi türünüde verebiliyoruz.
> > ```
> >
> > Prototip
> >
> > ```csharp
> > // degiskenTuru? degiskenAdi; -> Bu formatta tanımlanan değişkenler null değer alabilirler.
> > ```
> >
> > Kritik
> >
> > ```csharp
> > int? a = null; // nullable
> > Console.WriteLine(a is null);
> > //Bir değer türlü değişken, nullable yapıldıysa eğer; is null, is not null, as gibi null ile çalışan operatörleri kullanabiliriz.
> > 
> > //as Örneklendirme
> > object x = 123;
> > int? y = x as int?; // bu şekilde kullanılabilmektedir.
> > ```
>
> 



### ??(Null-Coalescing) Operatörü

> ??(Null-Coalescing) Operatörü : Elimizdeki değişkenin null olma durumuna istinaden farklı bir değeri göndermemizi sağlayan operatördür.
>
> * ***Null Coalescing operatöründe her iki taraftaki değişken veya değer aynı türde olmalıdır***
>
> ```csharp
> string a = "Ahmet";
> Console.WriteLine(a ?? "Merhaba"); // Eğer ki a null'sa "Merhaba" yı yazdır demiş oluyoruz.
> string b = null;
> Console.WriteLine(b ?? "Dünya"); // b değişkeni null olduğu için şartı yani "Dünya"yı yazdıracaktır. 
> Console.WriteLine(b == null ? "Dünya" : b); // ?: veya if operatörleri ile bu işlemi gerçekleştirmek yerine bu operatör vardır.
> Console.WriteLine(b ?? 3); // Compiler hata verecektir. Sağdaki ve soldaki değerler aynı türde olmalıdır!
> ```
>
> 



### ??= Operatörü (Null-Coalescing Assignment) (C# 8.0)

> ??= Operatörü : Elimizdeki değişkenin null olma durumuna göre farklı bir değer göndermemizi sağlayan, aynı zamanda değeri ilgili değişkene atayan operatördür.
>
> > Örnek 1
> >
> > ```csharp
> > string x = null;
> > Console.WriteLine(x ??= "Merhaba"); // x'in değeri null ise "Merhaba" yazdır ve "Mehaba" değerini x'e ata.
> > Console.WriteLine(x); // 2. kez "Merhaba" yazdırılacaktır.
> > ```
> >
> > Örnek 2
> >
> > ```csharp
> > int? id = null; //null yerine dışarıdan değer geldiğini varsayalım.
> > id ??= 1; //id null ise 1 değerini ata, değilse değerini koru...
> > ```
>
> 

