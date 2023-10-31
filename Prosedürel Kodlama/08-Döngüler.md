# C# Notları (Döngüler)

[TOC]



## Döngüler Nedir?

> Döngüler : Koşula bağlı, belirli sayıda, koşul sağlandığı sürece ilgili kodu tekrarlayan yapılardır.
>
> * for
>
> * while
>
> * do while
>
>   olarak 3 başlık altında ele alacağız.
>
>   *foreach döngü değildir, iterasyondur, ileride başka bir ana başlık altında ele alacağız.*
>
>   

> **Farkındalık**
>
> 'Hangi döngü nerede kullanılır' yanlış bir sorudur!
>
> Doğru soru 'Hangi döngü nereye/hangi sernaryoya daha çok yakışır' olmalıdır.
>
> Döngülerde hepsi birbirinin yerine kullanılabiliyor ancak bazı senaryolara bazı döngüler daha yatkındır.
>
> * Örn. Ardışık bir sayım işlemi oluyorsa for döngüsü daha yatkındır.
> * Örn. Sonsuz bir yapılanma söz konusu ise 'while' ya da 'do while' daha çok yakışacaktır.
> * do while döngüsü ise manevratik takla atacağımız belirli bir mantığa göre işleyen yapılanmadır.
>
> Bu döngülerin hepsi bir kombinasyona bağlı bir şekilde çalıştıkları için nihayetinde birbirlerinin yerine kullanılabilirler.
>
> 



## For Döngüsü

> Prosedürel programlamada döngü yapılarından birisi de for döngüsüdür.
>
> Genellikle ardışık işlemlerde kullanılan bir döngü yapılanmasıdır.
>
> > Prototip
> >
> > ```csharp
> > for (param1;param2;param3)//3 parametremiz olacak ve noktalı virgül ile ayıracağız.
> > {
> >     
> > }
> > //param1 : Genellikle başlangıç değeri ismi verilen değişken burada tanımlanabilir.
> > //param2 : Şart
> > //param3 : Genellikle başlangıç değerinin, değerini arttırmak ya da azaltmak için burası kullanılır.
> > ```
> >
> > * Param1, ardışık algoritmalar genellikle bir ilk değere ihtiyaç duyar. İşte bu ihtiyacı burada tanımlayabiliriz. Bu tanımlama zorunlu değildir!
> >
> > * Param2, Herhangi bir şart/koşul ifadesi tanımlanabilir. Genellikle ilk değer olarak tanımlanan değişken durumu burada kontrol edilir.
> >
> >   Yani bir şarta bağlanır. Şart true olduğu sürece döngü tetiklenecektir.
> >
> > * Param3, herhangi bir değişken üzerinde işlem yapabiliriz. Genellikle başlangıç değeri üzerinde bir arttırma ya da azaltma işlemi yapılır.
> >
> >   Bunun yanı sıra, diğer arttırma ve azaltma işlemleride ihtiyaca göre yapılmaktadır. Ve illa ki kullanmak zorunda da değiliz.
> >
> > * { } ise şart true oldukça bu scope tetiklenecek ve döngü çalıştırılacaktır.
>
> > For döngüsünün işleyişini inceleyelim.
> >
> > <img src="https://imgur.com/x4V3984.png" align=left>
> >
> > 1. Akış ilk olarak başlangıç değişkeni tanımlama kısmına girecektir. Eğer ki bir değişken tanımlama ifadesi varsa ilgili değişkeni tanımlayacaktır.
> >
> > 2. Ardından koşula gidecek ve koşulu değerlendirecektir.
> >
> > 3. Eğer ki koşul true ise döngüye girecektir.
> >
> > 4. Yok eğer koşul true değil ise döngüden çıkacaktır.
> >
> >    3.1. Koşul kontrol edildikten sonra döngü ilgili değeri arttıracak parametreye gidecek ve yapılan aritmetik işlemi değişkene uygulayacaktır.
> >
> >    3.2. Sayısal değeri arttırılmış ya da azaltılmış olan değişkenden sonra yeniden koşulu kontrol edecek ve ardından true ise 3 değilse 4. adımlar tekrar edecektir.
> >
> >    .
> >
> >    .
> >
> >    .
> >
> >    Ta ki koşul false olana kadar buradaki işlemler tekrar edecek ve döngü tetiklenmiş olacaktır.
>
> 



### İnceleme 1

> 
>
> >
> >
> >```csharp
> >for (int i = 1; i < 10 ; i++)
> >{
> >    Console.WriteLine("Mustafa Kurt");
> >}
> >```
> >
> >* Burada kodumuza bakarsak, öncelikle `int i = 1` şeklinde ilk parametrede bir değişken tanımladık.
> >
> >* Ardından ikinci parametrede ise `i < 10` şeklinde i'nin 10 dan küçük olduğu sürece, diye bir koşul belirledik. Eğer ki tanımladığımız değişken bu şarta uyuyorsa, True olarak koşul dönecek ve for scope alanı tetiklenecektir.
> >
> >* Son parametrede ise `i++` şeklinde i'nin bir artamsı için işlem tanımladık. 
> >
> >* Böylelikle ikinci parametredeki koşul false olana kadar döngü tekrar edecek ve ekrana for scope aralığındaki kodu tetikleyecektir.
> >
> >  Bu durumuda parametreleri adım adım ele alırsak,
> >
> >  Adım 1 : i değişkeni 1, koşul true, i + 1 -> Scope aralığı tetiklenir
> >
> >  Adım 2 : i değişkeni 2, koşul true, i + 1 -> Scope aralığı tetiklenir
> >
> >  .
> >
> >  .
> >
> >  Adım 9 : i değişkeni 9, koşul true, i + 1 -> Scope aralığı tetiklenir
> >
> >  Adım 10 : i değişkeni 10, koşul false -> Döngüden çıkar.
> >
> >  Yani toplamda 9 kere scope aralığındaki `Console.WriteLine("Mustafa Kurt");` kodu tetiklenir.
>
> 



### İnceleme 2

> Hilmi değerini 10 kere ekrana yazdıralım.
>
> > Bu işlemi ameleius yöntemiyle yapabiliriz, yani `Console.WriteLine("Hilmi");` şeklinde 10 kere yazabiliriz.
> >
> > Veya Döngü kullanarak da bu işlemi yapabiliriz.
> >
> > Eğer ki döngü kullanacaksak, bu işlemde, özellikle for kullanacaksak;
> >
> > ```csharp
> > for (int i = 0; i < 10 ; i++) //şartımız i < 10 yani 0'dan 9 a kadar buradaki kombinasyon 10 kere tetiklenecektir
> > {
> >     Console.WriteLine("Hilmi");
> > }
> > ```
> >
> > `i <= 10` eşitlik koyarsak 11 kere döndüreceğinin farkında olmamız gerekir
> >
> > ya da `int i = 1`olarak başlatırsak, şartımızı `i < 11`  veya `i <= 10` şeklinde yazmamız gerektiğinin farkında olmalıyız.
> >
> > Farklı bir kombinasyonla, `int i = 0; i < 50; i +=5` dediğimiz zaman da 10 kere döngüyü tetikleyecektir.
> >
> > Bu inceleme de kombinasyonun önemini inceledik.
>
> 



### İnceleme 3

> Bu inceleme de bir önceki incelemenin tam tersini yapacağız.
>
> > Hilmi değerini 10 kere ekrana yazdıralım.
> >
> > ```csharp
> > for (int i = 10; i > 0 ; i--)//burada her sıfırdan büyük olma durumunda i'den 1 azaltacaktır.
> > {
> >     Console.WriteLine("Hilmi");
> > }
> > ```
> >
> > `int i = 50; i > 0; i -= 5`dediğimizde yine 10 kere döngü tetiklenecektir.
>
> *Eğer ki ardışık işlemlerde artış yapılıyorsa i'nin değeri genellikle küçüklük durumuyla değerlendirilir.*
>
> *Yok eğer ardışık işlem eksiliş gösteriyorsa, i'nin değeri büyüklük durumuyla değerlendirilir.*
>
> 



#### Örnek 1

> 1'den 10'a kadar olan sayıları alt alta ekrana yazdıralım.
>
> > 1.Çözüm
> >
> > ```csharp
> > for (int i = 1; i <= 10; i++)
> > {
> >     Console.WriteLine(i);
> > }
> > ```
>
> > 2.Çözüm
> >
> > ```csharp
> > for (int i = 50; i < 60; i++)
> > {
> >     Console.WriteLine(i -49);
> > }
> > ```
>
> *Değerler bizim için çok da önemli değil, ancak mantıklı olan 1.çözüm'dür. Mümkün mertebe analitik çözüm getirmek önemlidir.*
>
> *Bazen yazılımcılarda, kompleksliği, analitiklik olarak algılayanlar var. Bu böyle değildir. Analitiklik basitlik demektir.*
>
> *Basitlik profesyonel olmayan kod anlamına gelmemektedir.*
>
> 



#### Örnek 2

> 1 ile 40(dahil) arasındaki çift sayıları toplayarak sonucu ekranda gösterelim.
>
> > ```csharp
> > int toplamSonuc = 0; //dışarıda oluşturmamızın sebebi içeride her tetiklenmede, tekrar tekrar tanımlanmaması için.
> > for (int i = 1; i <= 40; i++)
> > {
> >     if(i % 2 == 0)
> >     {
> >         toplamSonuc += i;
> >     }
> > }
> > Console.WriteLine("Toplam sonuç : " + toplamSonuc);
> > ```
>
> 



#### Örnek 3

> Klavyeden girilen sayının faktöriyelini bulan programı yazalım.
>
> Faktöriyeli bilmeyen, hatırlamayanlar için;
>
> örn. 5! : 5 x 4 x 3 x 2 x 1 = 120 
>
> Formülü : n! : n x (n-1) x (n-2)....x 2 x 1
>
> > 1.Çözüm
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > int faktoriyel = 1;//çarpılacak sonuç olacağı için 0 ile tanımlamıyoruz
> > 
> > for (int i = 1; i <= sayi; i++)
> > {
> >     faktoriyel *= i;
> > }
> > Console.WriteLine("Faktöriyel : " + faktoriyel);
> > ```
>
> > 2.Çözüm
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > int faktoriyel = 1;
> > 
> > for(int i = sayi; i > 0 ; i--)
> > {
> >     faktoriyel *= i;
> > }
> > Console.WriteLine("Faktöriyel : " + faktoriyel);
> > ```
>
> > 3.Çözüm
> >
> > Biz bu işlemleri daha ayrıntılı göstermek istersek,
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > int faktoriyel = 1;
> > string sonuc = "";
> > 
> > for (int i = sayi; i > 0 ; i--)
> > {
> >     faktoriyel *=i;
> >     //sonuc += i + (i == 1 ? " = " : " x ");
> >     if(i==1)
> >         sonuc += i + " = ";
> >     else
> >         sonuc += i + " x ";
> > }
> > Console.WriteLine("Faktöriyel : " + sonuc + faktoriyel);
> > ```
>
> 



### Varyasyonları

#### 1.Varyasyon

> ```csharp
> for (int i = 0; i < 10; i++)
> {
>     
> }
> ```
>
> * Bu varyasyonda hiçbir şey zorunlu değil.
> * İstersen başlangıç değerini tanımla
> * İstersen şartı bambaşka bir şey üzerinden ver (illa başlangıç değeri üzerinden vermek zorunda değilsin)
> * Herhangi bir değişkenin değerini arttırıp azaltabilirsin (illa başlangıç değişkeninin değerini arttırıp azaltmak zorunda değilsin)
>
> Burada amaç bakınca tek seferde görebilmek, tek bir çatı altında toplamaktır.
>
> 



#### 2.Varyasyon

> ```csharp
> int i = 0;
> for (;i < 10; i++)
> {
>     
> }
> ```
>
> *i değişkeninin değerinin dışarıta tanımlandığı başka bir varyasyondur.*
>
> 



#### 3.Varyasyon

> ```csharp
> int i = 0;
> for (i = 0; i <10; i++)
> {
>     
> }
> ```
>
> *Dışarıda tanımlanmış bir değerin, yine içeride tanımlanabildiği bir varyasyondur.*
>
> *Eğer ki bu varyasyona göre bir döngü oluşturulacaksa, içeride değişkenin çağırılması halinde yine bir başlangıç değeri verilmesi gerekir.*
>
> 



#### 4.Varyasyon

> ```csharp
> int i = 0;
> for (; i < 10 ;)
> {
>     i++;
> }
> ```
>
> *Varyasyon olarak değişkenin dışarıda tanımlanmasının yanı sıra, ilgili işlemi de içeride tanımlayabilmekteyiz.*
>
> 



#### 5.Varyasyon

> ```csharp
> string adi = "Hilmi";
> for (int i = 0; adi == "ahmet"; i++)
> {
>     
> }
> ```
>
> *Bu şekilde bir döngü tanımlanması da mümkündür.*
>
> veya
>
> ```csharp
> int a = 10;
> for (int i = 0; a != i * 2; i++)
> {
>     Console.WriteLine("Mustafa");
> }
> ```
>
> *Buradaki parametrelerde, illa ki normal yüzeysel tanımlarda olduğu gibi,*
>
> * *illa başlangıç değerin olacak,*
>
>   *illa şartın ona göre olacak,*
>
>   *illa başlangıç değerine göre arttırma işlemi olacak değil.*
>
> *Hepsi opsiyonel, hepsi bizim irademize bağlı.*
>
> 



#### 6.Varyasyon

> ```csharp
> for (;;)
> {
>     Console.WriteLine("Mustafa");
> }
> ```
>
> *Bu varyasyonda yukarıdaki şekilde bir kullanım gerçekleştirirsek, ilgili kod sonsuz bir döngüye girecektir.*
>
> 



#### 7.Varyasyon

> ```csharp
> for (int i = 0; ; i++)
> {
>     Console.WriteLine("asdf");
> }
> ```
>
> *Bu varyasyonda, eğer ki bir şart belirtirseniz ona uygun bir şekilde hareket edecektir. Ama yukarıdaki gibi şartı belirtmediğimiz taktirde yine sonsuz döngüye girecektir.*
>
> 



#### 8.Varyasyon

> ```csharp
> for (int i = 0, i2 = 0; i < 10 && i2 < 5; i++, i2++)
> {
>     Console.WriteLine(i);
>     Console.WriteLine(i2);
> }
> ```
>
> *Başlangıç değişkeni tanımlarken, ilk parametre tanımlama kısmı olduğu için birden fazla değişken tanımlayabilmekteyiz.*
>
> *Şarta ve işleme de bu şekilde eklemeler yapılabilmektedir.*
>
> 



## While Döngüsü

> Prototip
>
> >```csharp
> >while(.........)
> >{
> >    
> >}
> >```
> >
> >* While döngüsü sadece şarta bağlı bir döngüdür. Şart doğrulandıkça tetiklenecektir.
> >* for'a nazaran daha ilkel ve sade bir döngüdür.
> >* while döngüsü programlamanın ilk tasarlanmış döngüsüdür.
>
> Genellikle sonsuz döngülerde veya süreci bilinmeyen durumlarda kullanılan bir döngüdür.
>
> Ama istediğiniz yerde kullanabilirsiniz.
>
> 



### For ile Kıyaslama

> 
>
> ```csharp
> for (int i = 0; i < 10; i++)
> {
>     Console.WriteLine("Mustafa");
> }
> while (true)
> {
>     
> }
> ```
>
> while döngüsünde for gibi çalışabilmek için, kombinasyonu kendimiz oluşturmalıyız.
>
> ```csharp
> int i = 0;
> while (i < 10)
> {
>     Console.WriteLine("Mustafa");
>     i++;
> }
> ```
>
> 



### İnceleme 1

> Ekrana 10 kere "Merhaba Dünya" yazdıran bir program yapalım.
>
> ```csharp
> int i = 1; //Bir değişken tanımladık
> while(i <= 10) //Koşulu yazdık.
> {
>     Console.WriteLine("Merhaba Dünya");
>     i++; //arttırma işlemi ile koşulu daraltarak sonlanmasını sağladık
> }
> ```
>
> 



### İnceleme 2

> Klavyeden girilen sayıdan geriye doğru 0'a kadar sayan bir sayaç hazırlayalım.
>
> ```csharp
> int sayi = int.Parse(Console.ReadLine());
> 
> while(sayi >= 0)
> {
>     //sayi--; // Algoritmada kullanılacak değer, önceden işleme tabii tutulmamalıdır.
>     Console.WriteLine(sayi);
>     sayi--;
> }
> ```
>
> 



### İnceleme 3

> 0 ile 100(dahil) arasındaki tek sayıları toplayarak sonucu ekranda gösteren programı yapalım.
>
> ```csharp
> int i = 0, toplam = 0;
> 
> while(i <= 100)
> {
>     if(i % 2 == 1)
>         toplam += i;
>     i++;
> }
> Console.WriteLine(toplam);
> ```
>
> 



### İnceleme 4

> Klavyeden girilen sayının faktöriyelini hesaplayalım.
>
> ```csharp
> int sayi = int.Parse(Console.ReadLine());
> int faktoriyel = 1;
> 
> while(sayi > 0)
> {
>     faktoriyel *= sayi--;//İçeride tanımlı bir şarta bağlı olmadığı durumlarda bu şekilde de kullanılabilir.
>     //sayi--;
> }
> Console.WriteLine("Faktoriyel : " + faktoriyel);
> ```
>
> 

### İnceleme 5

> 0 anki tarihin saniye değeri 5'in katıysa eğer tarihi ekranda gösteren uygulamayı yazalım.
>
> ```csharp
> while (true)
> {
>     if (DateTime.Now.Second % 5 == 0)
>         Console.WriteLine(DateTime.Now);
> }
> ```
>
> 



## Do While Döngüsü

> while : Şart true oldukça döngü tetiklenecektir.
>
> * while döngüsü önce şarta bakar, sonra kodu çalıştırır.
>   * while ile yapılan kontrolde şart true olursa döngü tetiklenecek, false olursa hiçbir zaman tetiklenmeyecektir.
>
> * do while döngüsü ise önce kodu çalıştırır, sonra şarta bakar.
>   * *do while döngüsü şart true'da olsa, false'da olsa en az bir kere tetiklenecektir.*
>
> > Prototip
> >
> > ```csharp
> > do
> > {
> >     
> > }
> > while(......)
> > ```
>
> * do while : Genellikle öncelikli işlemler yapılıp ardından kontrol edip daha sonra tekrar edecek durum varsa tercih ediyoruz.
>
> 



### While ile Kıyaslama

> ```csharp
> while (false)
> {
>     Console.WriteLine("while döngüsü");
> }
> do
> {
>     Console.WriteLine("do while döngüsü");
> } while(false);
> ```
>
> 



## Scopesuz Döngüler

> Bir döngü de yapılacak işlem tek satırlık, tek konseptlik ise scopesuz oluşturabilmekteyiz.
>
> ```csharp
> for (int i=0; i < 10 ; i++)
>     Console.WriteLine("Mustafa Kurt");
> while (true)
>     Console.WriteLine("");
> do
>     Console.WriteLine("dowhile");
> while (true);
> ```
>
> 



## Sonsuz Döngüler

> Bazen mantık hatasıyla, bazen de kasıtlı olarak kullandığımız bir durumu tarif etmektedir.



### For

> for döngüsünde sonsuz döngüye girmek istiyorsak,
>
> ```csharp
> for (;;)
> {
>     
> }
> ```
>
> Eğer ki, sonsuz döngüden daha sonra çıkmak istiyorsak,
>
> ```csharp
> bool dongu = true;
> for (;dongu;)
> {
>     if(true)
>         dongu = !dongu;
> }
> ```
>
> 



### While

> while döngüsünde,
>
> ```csharp
> while (true)
> {
>     
> }
> ```
>
> İhtiyaç doğrultusunda, bu döngüden çıkabilmek için,
>
> ```csharp
> bool durum = false;
> while (!durum)
> {
>     if(true)
>         durum = !durum;
> }
> ```
>
> 



### Do While

> do while döngüsünde,
>
> ```csharp
> do
> {
>     
> }
> while (true);
> ```
>
> İhtiyaç doğrultusunda, bu döngüden çıkabilmek için,
>
> ```csharp
> bool durum = false;
> do
> {
>     if(true)
>         durum = !durum;
> }
> while (!durum);
> ```
>
> 



## İç İçe Döngüler

> Döngüler içerisinde bir başka döngü tanımlamak mümkün. Bir döngünün sytanx'ını bilmek, diğerleri için de yeterlidir.
>
> Konu olarak buradaki maliyeti ele alacağız.



### For

> * İç içe for döngülerinde değişken isimleri farklı olmalıdır.
>
> ```csharp
> for (int i =0; i < 10; i++) //10 işlem
> {
>     for (int j = 0; j < 5; j++) //5 işlem
>     {
>         for (int o = 0; o < 3; o++) //3 işlem
>         {
>             int p = 0;
>             while (p > 4)// 4 işlem
>                 p++;
>         }
>     }
> }
> //İç içe döngülerde maliyet, tüm döngülerin maliyetinin yani tur sayısının/periyodik çalışmasının çarpımına eşittir.
> // 10 * 5 * 3 * 4 = 600
> ```
>
> 



## Foreach Bir Döngü mü?

> Foreach bir döngü değil, bir iterasyondur.
>
> Döngü : Belirli bir kombinasyon eşliğinde çalışan ve belirli bir şarta bağlı olan periyodik işlemler gerçekleştiren yapılanmalardır.
>
> Iterasyon : Iterasyon mantığında ne kombinasyon ne de şart vardır. Iterasyonda sonraki veri, öteki veri anlamına gelen itere etme fiili vardır. Bir veri kümesi üzerinde işlem yapmamızı, yani verileri elde etmemizi sağlayan yapılanmadır.
>
> 

