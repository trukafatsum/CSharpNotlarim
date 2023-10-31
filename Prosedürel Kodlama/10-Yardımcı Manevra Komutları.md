# C# Notları (Yardımcı Manevra Komutları)

[TOC]



## Algoritmada Manevra Yapmamızı Sağlayan Komutlarda Neyin Nesi?

> Yardımcı Manevratik Komutlar : Algoritmada normal gidişata müdahale etmemizi sağlayan ve belirli manevralar yapmamızı sağlayan komutlardır.
>
> Kodu durdurmak, devamını okumamak, var olan bir döngüden çıkış yapmak veya komple metodu sonlandırmak yani kodu yönlendirmek için kullanılan komutlardır.
>
> > Örnek
> >
> > ```csharp
> > //Bildiklerimizden yola çıkarsak,
> > for (int i = 0; i < 100; i++)
> > {
> >     if (i == 22)//Bunu yapabiliriz ama çok da efektif değildir.
> >     {
> >         i = 100;
> >     }
> > }
> > 
> > ```
> >
> > * Manevratik komutlar, yapamayacağımız şeyleri yapmamızı sağlayan komutlar değildir!
> >
> >   Yapabileceğimiz manevraları/kodun yönlendirmelerini daha efektif, daha profesyonel yapmamızı sağlarlar.
>
> Nedir bu komutlar?
>
> 1. break
> 2. continue
> 3. return
> 4. goto
>
> 



## break Komutu/Keywordu

> break Komutu/Keywordu : Kullanıldığı yapıdan çıkış yapılmasını/kullanıldığı yapıyı sonlandırmaya yarayan bir keyworddur.
>
> Kullanım alanları; switch-case ve döngüler
>
> Sadece bu iki yapı içerisinde kullanılabilen bir keyworddur.
>
> > İnceleme 1
> >
> > ```csharp
> > for (;;)
> > {
> >     //...
> >     while (true)
> >     {
> >         break;
> >     }
> > }
> > ```
> >
> > Örnekten de anlayacağınız üzere break komutu kullanıldığı döngüden (yani while döngüsünden) çıkış yapacaktır. for döngüsünü sonlandırmayacaktır.
>
> > İnceleme 2
> >
> > ```csharp
> > switch (10)
> > {
> >     case 5:
> >         break; 
> >     case 10: //durumu kontrol edecek
> >         break; //kodlar çalıştıktan sonra switch yapısından çıkış yapacaktır
> >     case 15:
> >         break;
> > }
> > ```
>
> > İnceleme 3
> >
> > ```csharp
> > foreach (var item in new[] {""})
> > {
> >     break;
> > }
> > ```
> >
> > *Break komutu için her ne kadar döngüler ve switch yapılanmasında kullanılır desek de, foreach iterasyonunu da sonlandıran bir yapılanmadır.*
>
> > İnceleme 4
> >
> > ```csharp
> > do
> > {
> >     if(true)
> >     {
> >         break;
> >     }
> > } while(true);
> > ```
> >
> > * Döngü içerisinde herhangi bir yapılanma varsa onun içerisinde de kullanılabilmektedir.
> >
> > 
>
> > Örnek 1
> >
> > ```csharp
> > while(true)
> > {
> >     if (DateTime.Now.Second == 45)
> >         break;
> >     Console.WriteLine(DateTime.Now);
> > }
> > ```
> >
> > Örnek 2
> >
> > ```csharp
> > for (int i = 0; i < 5; i++)
> > {
> >     for (int j = 0; j < 3; j++)
> >     {
> >         if (j==1)
> >             break;
> >         Console.WriteLine("i : "+ i +"j : " + j);
> >     }
> > }
> > ```
> >
> > Örnekleri çalıştırarak test edelim.
>
> 



### Örnek 1

> Kullanıcıdan 't' harfi girene kadar alınan sınırsız sayıda sayıyı toplayan ve sonucu ekrana yazdıran uygulamayı yazalım.
>
> > ```csharp
> > //Kullanıcı bize n tane sayı verecekse mantıken sonsuz döngüye giriyoruz
> > int toplam = 0;
> > while (true)
> > {
> >     Console.WriteLine("Lütfen bir sayı giriniz : ");
> >     string girilenDeger = Console.ReadLine();
> >     if(girilenDeger == "t")
> >     {
> >         Console.WriteLine("Toplam Sonuç : " + toplam);
> >     }
> >     else
> >     {
> >         toplam += int.Parse(girilenDeger);//girilen değerin ya sayısal değer ya da t olduğunu varsayarak oluşturuyoruz
> >     }
> > }
> > ```
> >
> > Burada "t" girdikten sonra "Lütfen bir sayı giriniz." diyerek devam ediyor.
> >
> > Haliyle if scope aralığına `Console.WriteLine("Toplam Sonuç :" + toplam);`dan sonra break yazmamız gerekiyor.
>
> [Video desteği](https://youtu.be/rq9tE0IqTJA)
>
> 



### Örnek 2

> Kullanıcıdan alınan sonsuz adet sayı değerlerinden 37'nin katı girildiğinde sonlanan uygulamayı yazalım.
>
> > ```csharp
> > while(true)
> > {
> >     Console.WriteLine("Lütfen bir sayı giriniz.");
> >     int sayi = int.Parse(Console.ReadLine());
> >     if(sayi % 37 == 0)
> >     {
> >         Console.WriteLine("Uygulama sonlanmıştır.");
> >     }
> > }
> > ```
> >
> > Uygulama sonlanmıştır diyecektir, lakin break komutu ile sonlandırmadığımız için, hala bizden sayı girmemizi isteyecektir.
>
> [Video desteği](https://youtu.be/tpVYfDJvQZc)
>
> 



## continue Komutu/Keywordu

> contiune Komutu/Keywordu : Döngüde bir sonraki tura geçilmesini sağlar. Yani bir sonraki periyoda direkt geçiş yaptırır.
>
> Sade ve sadece döngülerden erişilebilen ve döngülerde kullanılabilen bir keyworddur.
>
> > Örnek
> >
> > ```csharp
> > for (int i = 0; i < 10; i++)
> > {
> >     if(i % 2 == 0)
> >     	continue;// i'nin çift olmadığı durumlarda bir sonraki duruma geçer.
> >     Console.WriteLine(i);
> > }
> > ```
> >
> > Breakpoint ile debug ederek inceleyelim.
>
> 



### Örnek 1

> Kullanıcıdan girdiği sonsuz adet sayıdan pozitif olanlarını çarpan ve 't' (enter) yapıldığında sonucu ekrana yazdıran kodu yazalım.
>
> ```csharp
> int carpim = 1;
> while(true)
> {
>     Console.WriteLine("Lütfen bir sayı giriniz.");
>     string girilenDeger = Console.ReadLine();
>     if(girilenDeger == "t")
>     {
>         Console.WriteLine(carpim);
>         break;
>     }
>     else
>     {
>         int sayi = int.Parse(girilenDeger);
>         //if (sayi > 0)
>         //	carpim *= sayi;
>         if (sayi < 0)
>             continue;
>         carpim *= sayi;
>     }
> }
> ```
>
> [Video desteği](https://youtu.be/SkL6qqxYeT8)
>
> 



### Örnek 2

> 1 ile 1000 arasında 7'nin katı olmayan sayıları ekrana yazdıralım.
>
> ```csharp
> for (int i = 1; i <= 1000; i++)
> {
>     if(i % 7 == 0)
>         continue;
>     Console.WriteLine(i);
> }
> ```
>
> [Video desteği](https://youtu.be/WPZZdVj8woY)
>
> 



## return Komutu/Keywordu

> return Komutu/Keywordu : Her yerde(metot içerisinde) kullanılabilir, erişilebilir bir keyworddur.
>
> İki işlevi görmektedir;
>
> 1. Nerede çağırılırsa çağırılsın, metottan çıkış yapar. Yani metodu sonlandırır.
> 2. İleride göreceğimiz, metotlar konusunda geriye değer döndürme sorumluluğunu da üstlenen bir keyworddur.
>
> > Örnek metodumuz (Main)
> >
> > ```csharp
> > namespace returnkeyword
> > {
> >     class Program
> >     {
> >         static void Main(string[] args)
> >         {
> >             while(true)
> >             {
> >                 switch (10)
> >                 {
> >                     case 10:
> >                         return;//Uygulama metottan çıkacaktır.
> >                         //return'den sonra hangi komut gelirse gelsin, metot sonlanacağı için işlenmeyecektir!
> >                         break;
> >                 }
> >             }
> >         }
> >     }
> > }
> > ```
>
> [Video desteği](https://youtu.be/KLQ6885SN7g)
>
> 



### Örnek

> Kullanıcı 'c' tuşuna basana kadar sonsuz döngüde dönen uygulamayı yazınız.
>
> ```csharp
> while(true)
> {
>     if(Console.ReadKey().KeyChar == 'c')
>     {
>         Console.WriteLine("Uygulama sona ermiştir.");
>         return;
>     }
>     Console.WriteLine("");
>     Console.WriteLine("Uygulama çalışıyor...");
> }
> ```
>
> [Video desteği](https://youtu.be/MPtfGbdOU6I)
>
> 



## goto Komutu/Keywordu

> goto Komutu/Keywordu : Kodun senkronizasyonunu bozup, akışı ters istikamete almamızı sağlayan bir manevratik komuttur.
>
> Davranışsal olarak, döngülere benzer.
>
> * switch case yapılanmasında dahili olarak kullanılan bu komut, metot içerisinde heryerde kullanılabilir.
>
>   > ```csharp
>   > switch (....)
>   > {
>   >     case n:
>   >         break;
>   >     case m:
>   >         goto case n; //önceden tanımlanmış olan bir case'in kodunu tetikliyordu.
>   > }
>   > ```
>
> > Prototip
> >
> > ```csharp
> > a;//başlangıç referansı
> > .
> > .
> > .
> > goto a;//Akışı tekrar a'ya getirip devam edecektir.
> > //tanımlanmış olan referansa kodun akışını yönlendiriyoruz.
> > ```
>
> Dedikodu :
>
> * Geleneksel coderlar tarafından pek sevilmeyen goto keywordu tavsiye edilmemektedir.
> * Teknik olarak programı yavaşlattığı söylenmektedir. Hatta yapılmış olan performans testlerini incelediğimizde, bir nebze kayıp ve yavaşlık söz konusudur. Yani maliyeti diğer durumlara nazaran oldukça fazladır.
> * goto keywordu ile senkronizasyonu bozup başa dönme durumu bir döngüyle aynı işlemi yapmaya nazaran, daha maliyetli olacaktır.
>
> > Sefer Algan : "İyi bir c# programcısı gerekmediği sürece kesinlikle goto anahtar sözcüğünü kullanmamalıdır."
> >
> > Gençay Yıldız : "Diller geliştikçe ve yüksek seviyede oldukça bu komutun kalkması doğal bir süreçtir."
>
> > Tekrar hatırlamak maksadıyla
> >
> > ```csharp
> > switch(10)
> > {
> >     case 5:
> >         Console.WriteLine("5");
> >         break;
> >     case 10:
> >         goto case 5;
> >     case 15:
> >         break;
> > }
> > //switch dışında kullanabildiğimiz durumda
> > a:
> > //...
> > Console.WriteLine("Merhaba");
> > Console.WriteLine("Dünya");
> > goto a; //senkronizasyon goto'ya geldiği durumda a'ya dönüyor.
> > ```
> >
> > * Böyle bir duruma nazaran önerilen döngü kullanmaktır.
>
> [Video desteği](https://youtu.be/_kXtCE0YYMo)
>
> 



### Örnek

> 1'den 100'e kadar sayalım.
>
> ```csharp
> int i = 1;
> x:
> Console.WriteLine(i++);
> if(i <= 100)
>     goto x;
> ```
>
> [Video desteği](https://youtu.be/up8uKnx8dTo)
>
> 



### Kritik

> ```csharp
> a:
> for(int i =0; i < 190; i++)
> {
>     goto a;
> }
> ```
>
> [Video desteği](https://youtu.be/bYiMyAyCnG8)
>
> 



