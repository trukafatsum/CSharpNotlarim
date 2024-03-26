Github: https://github.com/trukafatsum 

**Buradaki notların tutulması tarafımca yapılmış ve Typora uygulaması üzerinden markdown halinde yazılıp, html formatına da dönüştürülmüştür.**

> Eğitim sürecinde ve notların çoğunda emeği geçen [Gençay Yıldız](https://www.linkedin.com/in/gen%C3%A7ay-y%C4%B1ld%C4%B1z-a1453987/?originalSubdomain=tr) hocama teşekkürü borç bilirim.

[TOC]



## Kaynakça

[Anadolu Üniversitesi Dijital Ders Platformu - Programlamada Yeni Eğilimler : Çevik Yazılım ve Scrum Yöntemi](https://ddp.anadolu.edu.tr/#/course/YBS406U)

[YouTube: Özel Ders Formatında A'dan Z'ye C#10 Programlama Eğitimi - Gençay Yıldız](https://www.youtube.com/watch?v=ag0XfgyBDbU&list=PLQVXoXFVVtp3e_urGZcMNAHx2Eo4Rm5Xk)

[NgAkademi: A'dan Z'ye Temel C#10 Programlama Eğitimi - Gençay Yıldız](https://ngakademi.com/courses/adan-zye-temel-c-programlama-egitimi/)



------

# Başlarken



## C# Nedir?

* Microsoft tarafından .Net çatısı altında geliştirilen ve gelişen modern programlama dilidir.

* Açık kaynak ve ücretsizdir.

* C benzeri bir dildir.

* OOP'yi ve OOP'nin gelişimini destekler.

  > OOP: Object Orianted Programing (Nesne Tabanlı Programlama)

* Orta seviyeli bir dildir.

* Programlama Dillerinin Sınıflandırılması

  * Çok yüksek seviyeli diller (visual basic, vb.net, Foxpro, access..)
  * Yüksek seviyeli diller (pascal, basic, fotran..)
  * Orta seviyeli diller (c,c++,c# , Java, Ada..)
  * Düşük seviyeli diller (assembly..)
  * Makine dilleri (1 ve 0'lardan oluşur)
          

  > Burada kalite mi söz konusu? Hayır bir dil yüksek seviyeli ise beşeri dile daha yakındır, baktığınız zaman makale gibi okursunuz.
  > Bir dil okunabilirliği düşüyorsa sembollerle ifade ediliyorsa ve bir matematiğe mantığa göre yorumlanabiliyorsa o dil düşük seviyelidir.

* Java'dan etkilenmiştir. Java'yı etkilemektedir.

* __cSharp ile neler geliştirilebilir?__
           

  * Web Uygulamaları,
  * Mobil,
  * Web Servis,
  * Servis Mimarileri
  * Konsol,
  * DLL,
  * Windows Forms,
  * Oyun,
  * ERP, Muhasebe, Multi Media, İstatistik, Güvenlik vs.. Yazılımları

* Derlenen bir programlama dilidir.

---

## .NetFramework ve .Net Core Nedir? Farkları Nelerdir?

<img src="https://play-lh.googleusercontent.com/Gs6kFTfe9wy0kp3RvMMhCEejwohHaVUEaY9mda3aweBM9S6BLjLo7Nu4uTNNDN9gPfk" alt="" width=64 height=64>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/.NET_Core_Logo.svg/2048px-.NET_Core_Logo.svg.png" alt="" width=64 height=64>

.Net bir mimaridir ve __framework, core__ olarak ikiye ayrılır.

__.Net Framework Nedir?__

Microsoft'un ilk çıkardığı sürümdür. Ve windows eko-sistemine yönelik çözümler getirir.

Bu çatı altında;

*    WPF
*    Windows Forms
*    Asp.Net (4&5) yazılımları geliştirilir.
            

__.Net Core Nedir?__

Gelişen teknolojiler ve topluluğun farklı işletim sistemleri kullanması neticesinde, çoklu platformlar doğmuştur.

>		Dolayısıyla toplulukların sadece Windows işletim sistemlerini kullanmaması ve farklı işletim sistemlerinde de yazılım ve programlama yapılabilmesine imkan kılan Core gelmiştir.

<img src="https://i.stack.imgur.com/kAGE2.png" alt="" width=auto height=auto>

Bu çatı altında;

*    Asp.Net 5
*    Universal Windows Apps
*    Core CLR
*    .Net Native yazılımları geliştirilir.

*    Cross Platform'dur. Çeşitli işletim sistemlerinde uygulamaları destekler.
*    Modüler'dir.
*    Framework'ü de kapsar.

---

## Compiler Nedir?

Bir programlama dili __derlenen__ bir dilse, bu programlama dilinin __önce derlenmesi sonra çalıştırılıp sonuç alınması gerekir.__

__Peki derlemek ne demek?__

>				Yazdığımız kodları makinenin anlayabileceği koda çevrilmesi gerekmektedir, bu çevrilme işlemi derlemedir.
>						
>			>	Yani kullanıcının çalıştırabileceği yazılım uzantısı .exe'yi derleme ile elde ederiz.


## Kodlar Nasıl Compile Edilir?

Derlemenin nasıl yapıldığından ziyade derleme sonucu nasıl bir çıktı aldığımızı göreceğiz.

> Developer Command Prompt Visual Studio ile birlikte kurulur.

**Developer Command Prompt** ile bir dizin içerisinde;
**deneme isimli** bir dosyamız bulunduğunu ve bu dosyada C# kodlarımızın olduğunu varsayarsak,
dosyamızın bulunduğu adresi öncelikle komut isteminde çağırıyoruz,
kullanacağımız komut aşağıdaki gibidir.

``` csharp
> cd C:\User\MyPC\Desktop\ÖrnekKod //-> dosya konumu çağırma
> csc deneme //-> derleme işlemi
```

Bunun sonucunda derleme işlemi gerçekleştiriliyor.

Devam eden süreçte bunu bu şekilde gerçekleştirmeyeceğiz, Bunu kullanacağımız editörler yada **.net CLI** dediğimiz asistan sayesinde gerçekleştirmiş olacağız.

---

## Proje ve Solution Kavramları

Uygulama oluştururken temelde iki tane kavram vardır.

*	Proje: İçerisinde amaca dair çözümler getirilen kodsal çalışmaların yapıldığı operasyonların yürütüldüğü bir bütündür.
*	Solution: İçerisinde bir veya birden fazla proje barındırabilen bir evrensel kümedir.

<img src="https://www.visualmicro.com/documentation-work/pics/Solution-Explorer-Multiple-Projects.png" alt="" width=180 height=240>

> Bu örnekte gördüğünüz üzere 1 solution; 2 ve 3 ise projelerdir.
>
> > Bir başka örnek vermek gerekirse; bir banka uygulaması yaptığımızı varsayarsak, tek bir solution altında bu banka ile ilgili bankamatik, ödeme gibi alt projeleri olabilir.

## Visual Studio ile Proje Oluşturma ve Derleme

<img src="https://imgur.com/WY8RcMq.png" alt="" width= 180>
<img src="https://imgur.com/UvVwiQo.png" alt="" width= 400>

File menüsünden new project yada açılış ekranında Create a New Project, diyerek oluşturmaya başlayabiliriz.

*	Herhangi bir projenin nasıl ayağa kaldırabildiğini görmek için Consol'u seçerek devam ediyoruz.
  <img src="https://imgur.com/z8wRnQl.png">

*	Gelen ekranda Proje ve Solution ismi yazmamız gerekmekte ve ihtiyaç doğrultusunda isim vererek devam edelim.
  <img src="https://imgur.com/Hq740gA.png" width=500>

*	Proje ve Solution ayrı ayrı derlenebilir.
*	Solution Explorer sekmesinde Projeye veya solution'a sağ tıklayıp build dediğimiz taktirde derleme işlemi gerçekleşir.
*	Solution'a derle dersek bütün projeler derlenecektir.
*	Projeye derle dersek sadece ilgili proje derlenecektir.

  *	__Build__: Derlemeyi yapar.
  *	__Rebuild__: Önceden derlenip çıktı alnan dosyaları siler yeniden üzerine derleme yapar.
  *	__Clean__: Derlenmiş dosyaları siler.

> Bu işlemleri Solution'da gerçekleştirirken, solution'ın altındaki tüm projelerin etkileneceği unutulmamalı!

## CLI Nedir?

__Command Line Interface (CLI)__ : Türkçesi Komut Satırı Arayüzü

*	.NET Komut satırı arayüzüdür.
*	.NET Uygulamaları geliştirmeyi, oluşturmayı, çalıştırmayı ve
  yayınlamayı sağlar.
*	.NET SDK ile birlikte gelir.

### Temel Komutlar

```
> dotnet help 
```

> CLI'da desteklenen komutları detaylı listeler

---

```	
> dotnet new
```

> CLI üzerinden proje oluşturmak istediğimizde 
>
> > dotnet new [project type] --name [project name] + --force --> Proje oluştururken dizinde aynı isimde proje varsa ve bunun üzerine yazmasını istiyorsan ekliyoruz

---

```
> dotnet restore
```

> Proje sürecinde referans edilen yahut referansı kaldırılan paketlerin restorasyonunu sağlar

---

```	
> dotnet build
```

> Projeyi derler ve sonuç olarak .exe ve .dll çıktıları verir
>
> >Derlemeden önce projeyi restore eder.
> >		\bin\Debug\net5.0\ dizinine çıktı verir

---

```			  
> dotnet publish
```

> Projeyi derleyerek, yayınlanabilir dosyaları çıktı olarak verir.
>
> >Çıktı olarak;
> >
> >*	.dll,
> >*	.deps.json (projenin tüm bağımlılıklarını içerir)
> >*	.runtimeconfig.json (runtime konfigürasyonları)
> >*	Uygulama bağımlılıklarının dll'leri
>
> > \bin\Debug\net5.0\publish dizinine çıktı verir

---

```				
> dotnet run
```

> Uygulamayı derler, ayağa kaldırır. Çalıştırır.
>
> > run --no-build (derlemeden ayağa kaldırır)

---

### Proje Modifikasyon Komutları

fiziksel dosyayı eklerken referans

nuget (havuzdan) çekilenler paket olarak adlandırılıyor


yazılan son kod insana kullandırılacaksa çıktı .exe

yazılımı bir başka yazılım kullanacaksa çıktı .dll 

.dll'ler referans


```
> dotnet add package 
```

> Uygulamaya Nuget'ten paket/kütüphane yüklememizi sağlar
>
> >örn. dotnet add package Serilog.Sinks.Seq --version 4.0.0

---

```	
> dotnet add reference
```

> Uygulamaya fiziksel bir dll dosyasını referans etmemizi sağlar
>
> > dotnet add [source project].csproj reference [target project].csproj

---

```
> dotnet remove package 
```

> Uygulamaya yüklenmiş olan paketlerin/kütüphanelerin silinmesini sağlar
>
> > dotnet remove package [package name]

```
> dotnet remove reference
```

> Uygulamaya referans edilmiş .dll'leri kaldırır
>
> > dotnet remove reference [reference name]

---

```						
> dotnet list reference
```

> Uygulamada referans edilen tüm paketleri listeler
>
> > dotnet list reference

---

## Programlamaya Başlarken Temel İlkeler

###    Don't repeat yourself (DRY)

>Kodsal olarak sürekli kendini tekrar etmemen gerekir.
>
>> Hem kod açısından hem ezber açısından yaşadıklarımızı tekrar etmiyoruz.

###    Anlamlı isimlendirme

>örneğin mevsimleri isimlendirirken;
>
>>x,y,z şeklinde değil, mevsim- sonbahar- ilkbahar- kış - yaz şeklinde anlamlı isimler vermemiz gerekir.

###		S.O.L.I.D Prensipleri

__S — Single-responsibility principle__

*	Bir sınıf (nesne) yalnızca bir amaç uğruna değiştirilebilir, o da o sınıfa yüklenen sorumluluktur, yani bir sınıfın(fonksiyona da indirgenebilir) yapması gereken yalnızca bir işi olması gerekir.

__O — Open-closed principle__

*	Bir sınıf ya da fonksiyon halihazırda var olan özellikleri korumalı ve değişikliğe izin vermemelidir. Yani davranışını değiştirmiyor olmalı ve yeni özellikler kazanabiliyor olmalıdır.

__L — Liskov substitution principle__

*	Kodlarımızda herhangi bir değişiklik yapmaya gerek duymadan alt sınıfları, türedikleri(üst) sınıfların yerine kullanabilmeliyiz.

__I — Interface segregation principle__

*	Sorumlulukların hepsini tek bir arayüze toplamak yerine daha özelleştirilmiş birden fazla arayüz oluşturmalıyız.

__D — Dependency Inversion Principle__

*	Üst seviye (High-Level) sınıflar, alt seviye (Low-Level) sınıflara bağlı olmamalıdır, ilişki abstraction veya interface kullanarak sağlanmalıdır,
*	Abstraction(soyutlama) detaylara bağlı olmamalıdır, tam tersi detaylar abstraction(soyutlama)’lara bağlı olmalıdır.

__Avantajları;__

*	Geliştirdiğimiz yazılımın gelecekte gereksinimlere kolayca adapte olması,
*	Yeni özellikleri kodda bir değişikliğe gerek kalmadan kolayca ekleyebileceğimiz
*	Yeni gereksinimlere karşın kodun üzerinde en az değişimi sağlaması,
*	Kod üzerinde sürekli düzeltme hatta yeniden yazma gibi sorunların yol açtığı zaman kaybını da minimuma indirmektir.

## Çevik Yazılım Nedir? (BONUS)

### Yazılım Geliştirme Süreçlerinin Kısa Tarihi

*	1970'li yıllardan itibaren ilk yazılım geliştirme süreç modelleri oluşturulmaya başlanmıştır.

*	1980~2000'li yıllara kadar en yaygın kullanılan model (waterfall)
  - Waterfall : Kat kat fiskiye, yukarıdan aşağı kata kadar dola dola devam eder, ardışık birbirini izleyen geliştirme süreci vardır. Süreç doğrusal olarak işler. Süreç tamamlanınca başa sarar.

*	Çevik modellerin ilk prototipleri 1990'lı yılların başında Ken Schwaber (yazılım geliştirici, ürün yöneticisi) tarafından kendi şirketinde denenmiştir.

*	Schwaber, 1995 yılında Jeff Sutherland ile birlikte çalışarak "Scrum Software Development Process" (Scrum Yazılım Geliştirme Süreci) isimli bir makale yazmıştır.
  - Süreçler ve araçlar --> bireyler ve etkileşimlere
  - Kapsamlı dökümantasyon --> çalışan yazılıma
  - Sözleşme pazarlıkları --> müşteri ile işbirliğine
  - plana bağlı kalma --> değişime karşılık vermeye mottosunu benimsemeyi öngörüyorlar.

### Çevik Yazılım Geliştirme Prensipleri

1. En önemli önceliğimiz, değerli yazılımın erken ve devamlı teslimini sağlayarak müşterileri memnun etmektir.
2. Değişen gereksinimler yazılım sürecinin son aşamalarında bile kabul edilmelidir. Çevik süreçler değişimi, müşterinin rekabet avantajı için kullanılır.
3. Çalışan yazılım, tercihen kısa zamanlı aralıkları belirlenerek birkaç haftada yada birkaç ayda bir düzenli olarak müşteriye sunulmalıdır.
4. İş süreçlerinin sahipleri ve yazılımcılar proje boyunca her gün birlikte çalışmalıdırlar.
5. Projelerin temelinde motive olmuş bireyler yer almalıdır. Onlara ihtiyaçları olan ortam ve destek sağlanmalı, işi başaracakları konusunda güven duyulmalıdır.
6. Bir yazılım takımında bilgi alışverişlerinin en verimli ve etkin yöntemi yüz yüze iletişimdir.
7. Çalışan yazılım, ilerlemenin birincil ölçüsüdür.
8. Çevik süreçler sürdürülebilir geliştirmeyi teşvik etmektedir. Sponsorlar, yazılımcılar ve kullanıcılar sürekli olarak belirli bir tempoyu devam ettirebilmelidirler.
9. Teknik mükemmeliyet ve iyi tasarım konusundaki sürekli özen çevikliği arttırır.
10. Sadelik, yapılmasına gerek olmayan işlerin mümkün olduğunca arttırılması sanatı, olmazsa olmazımızdır.
11. En iyi mimariler, gereksinimler ve tasarımlar kendi kendini örgütleyen takımlar-dan ortaya çıkar.
12. Takım, düzenli aralıklarla nasıl daha etkili ve verimli olabileceğinin üzerinde düşünür ve davranışlarını buna göre ayarlar ve düzenler.

### Çevik Yazılım Geliştirme Yöntemleri

*	Adaptive software development (ASD)
*	Agile modeling
*	Agile Unified Process (AUP)
*	Crystal Clear Methods
*	Disciplined agile delivery
*	Dynamic systems development method (DSDM)
*	Extreme programming (XP)
*	Feature-driven development (FDD)
*	Lean software development -
*	Kanban -web
*	Rapid application development (RAD) -web
*	Scrum -web
*	Scrumban -web


### Çevik Yazılım Geliştirme Pratikleri

*	Test Güdümlü Programlama (Test Driven Development)
*	Kod Yeniden Yapılandırma (Code Refactoring)
*	Sürekli Entegrasyon (Continuous Integration)
*	Eşli Programlama (Pair Programming)

#### Test Güdümlü Programlama (Test Driven Development)

*	Algoritma işlem süreci; Test yazılır -> Test Hata Verir -> Gerekli Kod Yazılır -> Kod Yeniden Yapılandırılır -> Test Yazılır...

  *	Test güdümlü programlama, yazlım geliştirme faaliyetini hedefleyen bir yöntemdir.
  *	Bu yöntemde ilgili kodu yazan yazılımcı, kodu doğrudan yazmaya başlamak yerine, öncelikle koddan bekleneni test edecek olan test kod parçacıklarını yazarak işe başlar.
  *	Gerçekte geliştirilmesi gereken yazılım parçası her defasında ilgili testlere tabi tutulur.
  *	Testler başarısız olduğunda, testleri başarılı hale getirecek biçimde kod güncellemeleri yapılır ve testler tekrar çalıştırılır.
  *	Testler başarılı olana kadar bu işlem devam eder.

#### Kod Yeniden Yapılandırma (Code Refactoring)

-	Algoritma akışını değiştirmeden kodu yapısal olarak revize etmek--
-	Mevcut kodun davranışını değiştirmeden yapısal değişiklik yapma faaliyetidir.
-	Kodda yapılacak yeniden yapılandırma işlemlerinin, kodun okunabilirliğini arttırmak, sürdürülebilirliğini sağlamak, karmaşıklığını azaltmak gibi hedefleri olmalıdır.

#### Sürekli Entegrasyon (Continuous Integration)

-	Yazılım üzerinde yapılan değişikliklerin harhangi bir bozulmaya sebep olup olmadığının önceden belirlenmesini hedefleyen bir pratiktir.
-	Yapılan her değişiklik sonrası yazılım merkezi bir noktada derlenir ve tüm testler çalıştırılır. Eğer derlemede veya testlerde bir problem ortaya çıkarsa yazılım ekibi bilgilendirilir.
-	Böylelikle yazılım gerçek ortama çıkmadan önce erken geri dönüş sağlanmış olur. Yazılımdaki olası hatalar erken yakalanır ve düzeltilir.

### Eşli Programlama (Pair Programming)

-	Eşli programlama iki yazılımcının aynı iş üzerinde aynı iş istasyonunu kullanarak beraber çalışması pratiği olarak tanımlanabilir.
-	Burada iş istasyonu genellikle aynı bilgisayar ve ekran olarak düşünülebilir.
-	Yazılımcılardan bir tanesi kodu yazarken, diğeri gözlemleyerek kodu anında gözden geçirir. Yazılımcılar ara ara rol değişikliği de yaparlar.
-	Bu yöntem tek başına çalışmaya göre daha maliyetli olsa da, yapılan araştırmalara göre hata oranını düşürdüğü ve yazılım kalitesini arttırdığı gözlenmiştir.
-	Ayrıca daha tecrübeli yazılımcıların, yeni yazılımcılara bilgi aktarmasını da kolaylaştırır.

> Sürekli entegrasyon için test güdümlü programlama kullanılması gerekir.
>
> >Kod yeniden yapılandırmanın başarılı olabilmesi için eşli programlama gereklidir.

## SCRUM Yöntemi (BONUS)

### SCRUM Tanımı ve Temel Bileşenleri

Ürün Sahibi --> Ürün İş Listesi -Sprint Planlama-> Geliştirme Ekibi --> Sprint --> Potansiyel Kullanılabilir Ürün

Her sprint sonunda, yazılıma doğru, çalışabilir, ürüne değer katacak bir çıktı üretmek gerekir.

Her sprint için bir döngü planlanır, genellikle bu döngü 1 hafta sürer.

Günlük scrum toplantıları yapılır, bir hafta içerisinde başında ön değerlendirme yapılır, günlük scrumlar, sonrasında bir sprint değerlendirme yapılır. 

Süreç değerlendirilir, sonrasında Sprint Retrospektifi yapılır, bu sprintte neleri doğru yaptık, neler yanlıştı, bir sonraki sprintte nelere dikkat edilecek bu konularda çalışılır.

Toplantılar yatay bir hiyerarşi ile yapılır, herkes görüşünü işin patronuymuş gibi rahatlıkla söylemeli


### SCRUM Ekibi

*	Ürün Sahibi (Product Owner)
  *	Ürünün değeri ve geliştirilmesinden sorumludur. Yapılacak iş listesini oluturur ve önceliklendirir. Ürün iş listesinin herkes tarafından anlaşılabilir olmasını sağlar, yapılan işin bittiğini kabul eden kişi ürün sahibidir.
  *	Bütün bu sorumlulukları kendisi yerine getirebileceği gibi bu görevlerin gereğini Geliştirme Ekibinden birine de yaptırabilir, ancak sorumluluk Ürün sahibindedir.
  *	Bu süreçleri paydaşlarla bilgilendirip onlardan gelen dönütler üzerine kurgulaması gerekir.

*	Geliştirme Ekibi (Development Team)
  *	Her bir tekrarlama (iterasyon) sonrasında, ürünün sürüme çıkabilir bir kısmını teslim etmekten sorumlu kişilerden oluşmaktadır. Geliştirme ekibi kendi kendine organize olur. İş listesindeki işleri ürün haline getirirken birden fazla yazılım geliştirme faaliyeti yapabilirler.
  *	Bunlar tasarım, kodlama ve test olabilir. İdeal geliştirme ekibi 3-9 kişi olabilir. Sprint 9 kişiden fazla iş yüküne sahipse tekrar dizayn edilip yeni bir sprint oluşturulur.

*	Scrum Uzmanı (Scrum Master)
  *	Scrum'ın doğru anlaşılması ve doğru uygulanmasını sağlayan kişidir. Bunun için Scrum kurallarından, rehberlerden ve pratiklerden faydalanır. Ürün iş listesi-nin anlaşılır ve kısa parçalardan oluşması konusunda Ürün Sahibine yardımcı olur.
  *	Scrum Uzmanı ayrıca hizmetkar-lider olarak da isimlendirilir.

### SCRUM Etkinlikleri

*	Sprint
*	Sprint Planlama (Sprint Plannig)
*	Günlük Scrum (Daily Scrum)
*	Sprint Değerlendirme (Sprint Review)
*	Sprint Retrospektifi (Sprint Retrospective)

#### SPRINT

Scrum'ın en temel yapı taşşı olan Sprint, belirli bir zaman aralığını temsil eder. Bu aralığın uzunluğu en fazla bir ay olabilir.

Sprint süresince bir amaca uygun olarak geliştirme yapılır ve amacın başarılmasına olumsuz etki edecek değişikliklerden mümkün olduğunca kaçınılır. Ürün Sahibi ve Geliştirme Ekibi Sprint amaç ve kapsamını revize edebilir.

Bir Sprint biter bitmez hemen diğer Sprint başlar, arada boşluk yoktur. Sprintin uzunluğunun ekibe ve ürüne göre en baştan belirlenerek tüm Sprintlerin aynı uzunlukta olması, çıktıların doğru değerlendirilmesi açısından önem arz eder.

Bu sebeple ekip Sprintleri hangi uzunlukta yapacağına (1 hafta, 2 hafta, 1 ay vb.) karar verir. Sprint dışı bir zaman olmadığı için, diğer Scrum etkinlikleri Sprint içinde yapılır.

Bunlar, Sprint Planlama, Günlük Scrum, Sprint Değerlendirme ve Sprint Retrospektifidir.

#### SPRINT PLANLAMA

> Neyi-Nasıl-Hangi sırayla?
> Bir Sprintin en başında yapılan etkinliktir. Planlamada tüm Scrum Ekibi mevcut Sprint içinde yapılacak işi planlar.

Planlama toplantısının süresi Sprintin uzunluğu ile orantılıdır. Bir aylık Sprint için planlama toplantısı en fazla 8 saat, iki haftalık bir Sprint için ise 4 saat olabilir.

Sprint Planlama toplantısında temel olarak, içinde bulunulan Sprint süresince kullanılabilir ürün parçası olarak neler yapılacağı ve bu ürün parçalarını oluşturmak için yapılacak işlerin nasıl gerçekleştirileceği sorularına cevap aranır.

Ürün İş Listesinde bulunan işler üzerinde tahminleme yapmak için Planlama Kart Oyunu en çok kullanılan yöntemlerden biridir.

Geliştirme Ekibinin ne kadar iş alacağını kendisi seçmesi, kendi kendine organize olabilen ekip olma yolunda önemli bir yöntemdir.

#### Günlük SCRUM (Daily SCRUM)

>Geliştirme Ekibinin son bir gün içinde yaptığı faaliyetler ve planladığı faaliyetler hakkında bilgi alışverişini yaptığı toplantıdır.
>
>>En fazla 15 dakika sürmelidir.

__Üç temel konu dışında başka bir şey konuşulmaz:__

*	Sprint hedefi doğrultusunda dün yapılan işler.
*	Sprint hedefine ulaşmak için bugün yapacağı işler.
*	Sprint hedefine ulaşmayı engelleyen durumlar.


>>Günlük Scrum, Scrum'daki kilit etkinliklerden biridir. Ekip içindeki iletişimi geliştirir ve daha uzun toplantılara olan ihtiyacı ortadan kaldırır. Ekip her gün hedefe ne kadar yaklaştığını şeffaf bir şekilde takip eder.

#### Sprint Değerlendirme (Sprint Review)

Sprint'in en sonunda, ekibin geliştirdiği ürünü kontrol ettiği bir toplantıdır.

Tüm paydaşlar ve ekip geliştirilen ürün üzerinde işbirliği çerçevesinde fikirlerini ortaya koyarlar.

Değerlendirme toplantısı Ürün Sahibinin, Ürün İş Listesindeki işlerden hangilerinin bittiğini açıklaması ile başlar. Sonrasında, Ürün Sahibi veya Geliştirme Ekibi biten işleri gösterir ve soruları yanıtlar.

Ürün Sahibi, Geliştirme Ekibi ve tüm paydaşların katılı ile ortaya güncellenmiş bir Ürün İş Listesi çıkar.

Scrum'ın en önemli özelliklerinden biri olan hızlı geri dönüş ve paydaşların katılımı bu toplantı sayesinde başarılır.


#### Sprint Retrospektifi (Sprint Retrospective)

Bir Sprint içinde en son yapılan etkinliktir. Genellikle Sprint Değerlendirme toplantısından hemen sonra yapılır.

Bu toplantıda Scrum Takımı tüm bir Sprint'in değerlendirmesini yapar.

Toplantı üç saat ile sınırlandırılmalıdır.

Retrospektif toplantısında odaklanılan şey sürekli iyileştirmedir ve temel olarak bir sonraki Sprint sürecinde nelerin daha iyi yapılabileceği tartışılır.

Sprint'in süreç, insan ilişkileri, araçlar vb. konularda nasıl geçtiği gözlemlenir. İyi giden ve verimsiz ilerleyen noktalar belirlenir ve bir sonraki Sprint sürecinde yapılacak iyileştirmeler ile ilgili bir plan çıktısı oluşturulur.

Kızgın-Üzgün-Mutlu en çok tercih edilen yöntemlerden biridir.

### SCRUM Eserleri ve Çıktıları

*	Ürün İş Listesi (Product Backlog)
*	Sprint İş Listesi (Sprint Backlog)
*	Ürün Parçası (Increment)
*	Takım Hızı
*	Bitti Tanımı (Definion of Done)

#### Ürün İş Listesi (Product Backlog)

Ürün İş Listesi değer üreten ürünün, önceliğe göre sıralanmış özellik listesidir.
Üründen beklenen tüm gereksinimler için tek bilgi kaynağı burasıdır.
			
Ürün Sahibi, Ürün İş Listesinden sorumlu tek kişidir. Listenin sıralaması, içeriği ve erişilebilirliğinden sorumludur.
			
Ürün İş Listesi sürekli değişir ve gelişir.

Ürün İş Listesindeki kalemlerin her birinin tanımı, sırası ve tahmin değeri (büyüklük) vardır. İşlerin tahmini değerleri Geliştirme Ekibi tarafından yapılır. Bu tahminleme sırasında Ürün Sahibi ile fikir alışverişi yapılabilir.

Sprint süresince herhangi bir zamanda, Ürün Sahibi ve Geliştirme Ekibi, Ürün İş Listesi üzerinde detaylandırma ve iyileştirme yapabilir. Ancak bu işlem, Geliştirme Ekibinin Sprint içindeki kapasitesinin %10'undan fazla olmamalıdır.

Sprint değerlendirme sonrası kalan işler Ürün Sahibi tarafından gözden geçirilir.


#### Sprint İş Listesi

>Sprint İş Listesinde, Sprint hedefine ulaşmak için gerekli tüm işler bulunmalıdır.
>
>>Bu işlerin hepsinin mevcut tahmini, kalan efor bilgileri açık bir şekilde görülebilmelidir.

Günlük Scrum'da işlerin kalan efor miktarı ekip tarafından güncellenir.

Gerekli durumlarda yeni bir iş eklenebilir veya amaç dışı bir iş tespit edilmiş ise Sprint kapsamından çıkartılabilir.

Sprint gidişatını gözlemlemek için en etkili yöntem, toplam kalan işi gösterek bir grafik kullanmaktır.

#### Ürün Parçası (Increment)

Ürün Parçası bir Sprint sonunda tamamlanan Ürün İş Listesi kalemleri ile daha önce bitirilmiş Sprintlerdeki Ürün Parçalarının değerlerinin toplamıdır.

Her Sprint sonunda bir Ürün Parçası kullanılabilir olarak hazır ve "Bitti" olarak tanımlanmış bir şekilde ortaya çıkmalıdır.

Ürün Sahibi bu Ürün Parçalarını yayına ve kullanıma almak zorunda değildir. Ancak yayına alınacak olsa bile her Sprint sonunda bir Ürün Parçası üretilmiş olmalıdır.


#### Takım Hızı

Bir Sprint boyunca yapılan işlerin toplam puanı kaydedilir. Bu puan Scrum Ekibinin hızı olarak tanımlanır.

Her Sprint için kaydedilen bu değerin ortalaması, ekibin kapasitesi olarak değerlendirilir. Birkaç Sprint geçtikten sonra ekibin hız değeri oturacaktır.

Bu değer daha sonra planlama toplantılarında, Sprint içinde ne kadar işin yapılabileceği ve ne kadar işin Ürün İş Listesinden alınabileceği konusunda yol gösterici olacaktır.

#### Bitti Tanımı (Definion of Done)

Ürün İş Listesi kalemleri "Bitti" olarak nitelendirildğinde tüm ekip aynı şeyi anlamalıdır.

Bitti Tanımı önceden belirlenip, herkesin erişebileceği bir yerde sunulmalıdır.

Örnek olarak her işin tasarım, geliştirme ve birim testi aşamalarından geçmiş olması bir Bitti Tanımı olabilir.

## Main Nedir? Top-Level Statement Özellikleri Nedir?

### Main Nedir?

Uygulamalarda Main (ana) fonksiyon olması gerekir.
	
Program.cs
Uygulamalarda Program.cs dosyası başlangıç kodlarının bulunduğu yani uygulamanın ayağa kalkabilmesi için başlangıç kodlarının bulunduğu bir dosyadır.
	
Başlangıç Kodlarından kastımız, uygulama ayağa kalktığında işletim sistemi ile iletişim kurabilecek metodun ve bu metod içerisinde başlangıca dair komutları barındıracak bir yapılandırmadır.
	

#### Main Fonksiyonu;

Herhangi bir uygulama olsada bu main fonksiyonundan 1 adet olmak zorundadır.

Main fonksiyonu, program.cs dosyası içerisinde main isminde bulunur.

Uygulama ayağa kalktığında ilk tetiklenen fonksiyondur.
	
	

#### dotnet run -value- Yapısı ile Uygulamayı Çalıştırma ve args Parametresine Değer Gönderme

-

#### Top-Level Statements (c# 9.0) Özelliği

Sıradan bir işlem için bile oluşturulan console uygulamasında hiç yoktan boilerplate (basmakalıp) kodların gelmesi gerekmektedir.
Günlük hayatta basit kodlar inşa edebilmek ve test süreçlerinde hızlı denemeler yapabilmek için bu tarz bir kod bloğuna maruz kalmamıza gerek var mı?
	
C# 9.0 ile gelen top level statements özelliği ile main fonksiyonunun zoraki imzasının tanımlanması kaldırılmıştır.
Main fonksiyonunun kullanılması developerın kararına bağlıdır.
	
__Kurallar;__

1. using blokları ile namespace arasında kodlar yazılabilir
2. bu işlem sade ve sadece program.cs dosyasında geçerlidir. Yani main fonksiyonunda yazılacak komutların direkt burada yazılmasına müsade edilmekte lakin farklı bir dosyada bu işlemi gerçekleştirememekteyiz.

Bu şekilde yazılan komutlar derlendikten sonra esasında bir Main fonksiyonu içerisine alınacaktır.
Uygulama derlenirken Program.cs dosyasında varsa top level state. özelliği bu dosyaya özel algılayacak ve ilgili alana yazılan kodları main içerisinde yorumlayacaktır.
Bunun dışında zaten bu özelliği başka bir dosyada kullanamayacağımızdan dolayı sadece Program.cs dosyasına has bir özelliktir.
	
Top-level Statements, genellikle microservices yapılanmasında kodun gelişimi açısından hız kazandırıcı bir niteliğe sahiptir.

## Yorum Satırları ve Region

Kodun niteliğini, anlaşılabilirliğini, kalitesini, arttırabilmek için kullanılır.

Kritik noktalarda ve özet olarak kodları izah etmeliyiz.

Nerede kullanılırlar?

İstediğin her yerde yorum yazabilirsin, lakin kod konsepti ve semantik akışı bozmaman kaydıyla..

``` csharp
// Tek Satırlık

/* 

Çok
Satırlık
Yorum
Alanı

*/
```

Region kod dosyasını kategorik hale getirmemizi sağlayan bir ön işlemci komutudur. Developer'ın yazmış olduğu kodu daha net görmesini ve kategorize etmesini sağlar.

``` csharp
#region A Operasyonu
{
//Kodunuz..
}
#endregion
```

yazarak deneyebilirsiniz.


## Todo Nedir?

``` csharp
//örn.
//todo Burada 1'den 10'a kadar yazılmalıdır.
```

Şeklinde bir not aldığımızı düşünelim, daha sonra bu nota hızlıca erişebilmek için Visual Studio'da View diyerek Task List seçeneğini seçtiğimizde açılan pencerede görüntülenecektir.
Burada todo yorum satırından hemen sonra yazılmalıdır ardından bir boşluk ile açıklama yazılmalıdır.
todo2 veya todo3 vs.. hatalı kullanımdır.

## Debugging Nedir?

* Debugging : Hata ayıklamaktır, programın hatalarını yok etmeye yönelik, yazılan kodu gözden geçirme, düzeltme aktiviteleridir.

İçerisinde bol bol mantıksal çalışma yapılan bir kod inşa ettiğimizi düşünelim..

Bu mantıksal çalışmaların arasında toplama işlemi yerine çarpma işlemi yapacak bir kod yazdıysak, kodun akışı esnasında kodu gözlemleyebilmemizi sağlamaktadır.

Kompleks algoritmalarda zaman alıcıdır.

> Eğer debug olmasaydı dünya tahminen 60 yıl önceki teknolojide olurdu..

## BreakPoint Nedir ve Nasıl Yapılır?

Debugging amacı neydi?

Bir koddaki yapılanmayı daha da efektif hale getirmek, yapılan mantıksal hataları yakalamaktı.

Visaul Studio ortamında yazılan kod çalıştırılırken, varsayılan olarak debug modda çalışır. (Kısayolu F5)

Nasıl yapılır? 

*	Satırın solunda bulunan satır numarası varsa onun da solundaki çizgiye tıklayarak break point ataması yapılır.
  <img src="https://imgur.com/MFI2GQ7.png" width=450>
*	F5 ile veya debug olarak çalıştırdığımız taktirde debug işlemi başlar, ve F10 tuşuna basarak break point ile debug edilen kodun devam edilmesini sağlar.
*	Eğer ki tekrar F5 tuşuna basarsak kodu salmış yani debug'ı sonlandırmış oluruz.


Bu işlemi gerçekleştirmek için aşağıdaki örnek kodu baz alalım;

``` csharp
	for (int i = 0; i > 1000; i++)
	{
		if (i % 2 = 0)
		{
			Console.WriteLine (i * i);
		}
	}
```


## Watch Penceresi

Bir kodun içerisinde yapılan operasyon esnasında eğer ki bu operasyonu debug ediyorsanız, debug edilen operasyon içerisinde değişken denen noktalar var.

Bu değişkenlerin değerlerini veya değişenlerini daha hızlı, daha net, düzgün bir şekilde görebilmek istiyorsanız watch dediğimiz pencereyi kullanabilmekteyiz.

``` csharp
//örn. 
		int a = 5;
		int b = 15;
			
		for (int i = 0; i < 1000; i++)
		{					
			b = i;
			
			if (i % 2 == 0)
			{
				Console.WriteLine (i*i);
			}
		}
```

Burada break point ile çalıştırdıktan sonra a, b veya i 'nin üzerine fare imlecini getirdiğimizde bize o anki almış olduğu değerleri gösterir.

Bu değerleri tek tek görmek yerine, değişkenin üzerine sağ tıklayıp add watch dediğimizde bunu watch penceresi üzerinden akışı takip edebiliyoruz.

<img src="https://imgur.com/mqqk3hH.png" width=450>
<img src="https://imgur.com/PzkhdIu.png" width=450>



------

# Değişkenler



## Giriş


**En temelden ele almamız gerekirse,**

>Bir yazılım çalıştırıldığında, içerisindeki verileri RAM'de tutar. Yazılım veri tutmaz. RAM'den alır ve RAM'e yerleştirir.
>
>>Yazılımda yapılacak işlemlerin en küçük en merkezi noktası olan veriyi biz RAM'de tutarız.

>Bir yazılımda işlenecek veriyi RAM'de tutabilmek için değişkenler kullanılır.

**Değişken Nedir?**

>Değişkenler, verilerin geçici süreliğine depolandığı yerdir. Değişkenler içine verilerimizi istediğimiz şekilde koyabilir, bu verileri istediğimiz yerde çağırabilir ve kullanabiliriz.

**Peki bir programcı neden değişkene ihtiyaç duyar? Verileri veritabanında tutamaz mıyız?**

>İşlenecek veriler veri tabanında tutulabilir ancak işleme esnasında bunları tekrar RAM'e almamız gerekir. 

**Yani işlem boyutundayken veri tabanındaki bir veriyi işleyemeyiz, nerdeki veriyi işleyebiliriz?**

>RAM'deki veriyi işleyebiliriz.

>Yani yazılımın RAM'de çalışabilmesi, RAM'e değer koyabilmesi, RAM'deki bir değeri elde edebilmesi için değişkene ihtiyaç duymaktayız.

**Özetlemek gerekirse;**

Yazılımda işlenecek veriyi yazılım adına RAM'e yerleştirebilmek için biz programcılar değişkenleri kullanırız.


## Value Type | Primitive Type | Değer Türlü Değişkenler

Öncelikle verilerin RAM'deki davranışlarından söz edeceğiz.

**RAM'de veriler nasıl tutulur?**

>(int) (string) (int) (char) gibi RAM işlenecek verileri değişken türleriyle tutar.

```csharp
int sayi1 = 3;
int sayi2 = 15;
string metin1 = "Test";
```



<img src="https://imgur.com/5OwEh4a.png">

>C# programlama dilinde RAM'de veri tutabilmek/depolayabilmek için tanımlanacak olan değişkenin türü/veri türü bildirilmelidir.
><br>Tür elimizdeki veriye göre bildirilmelidir.

>Bir değişkenle RAM'de alan tahsisinde bulunduğumuzda buna **değer türlü değişken** diyoruz. Yani tuttuğu değer bir normal değer olan değişkenlere Değer Türlü denmektedir.

**Value Type (Değer Türlü) değişkenler;**

Sade ve sadece bir değeri tutan değişkenlerdir. Yani adımız, soyadımız, doğum tarihimiz gibi değerleri tutarlar.

**Primitive Typle (En ilkel türdür)**

Türetilmemiş veri, sade, ham veriyi tutar.

Örnek vermek gerekirse, byte: bir primitive türdür. Lakin byte'lardan meydana gelmiş olan decimal türü ise primitive değildir. Lakin Value Type'dır.

Yani Value Type'lar Primitive Type'ları da kapsarlar.

<img src="https://imgur.com/J6iTFtG.png" width=240 align=left>

>Değişken tanımlarken RAM'e tutulacak veriye uygun bir alan tahsisinde bulunulması gerekmektedir. RAM'de alan tahsisinde bulunabilmek için ilgili değişkenin türünden hareket edilir.
>
>Bir türde tanımlanmış alana farklı bir türde değer atayamayız.

### Hangi türlerle bu bildirimde bulunuyoruz?

|                | Tür     | Açıklama ve Bellek Alanı    | Max-Min Değer Aralığı                                        |
| -------------- | ------- | --------------------------- | ------------------------------------------------------------ |
| Mantıksal      | bool    | Doğru - Yanlış (1 Bit)      | 0-1 (true-false)                                             |
| Metinsel       | char    | Karakterler (16 Bit)        | 16 Bit Unicode                                               |
| Sayısal        | sbyte   | İşaretli Tam Sayı (8 Bit)   | -128 ~ 127 arası                                             |
| Sayısal        | byte    | İşaretsiz Tam Sayı (8 Bit)  | 0 ~ 255 arası                                                |
| Sayısal        | short   | İşaretli Tam Sayı (16 Bit)  | -32.768 ~ 32.767 arası                                       |
| Sayısal        | ushort  | İşaretsiz Tam Sayı (16 Bit) | 0 ~ 65.535 arası                                             |
| Sayısal        | int     | İşaretli Tam Sayı (32 Bit)  | -2.147.483.648 ~ 2.147.483.647 arası                         |
| Sayısal        | uint    | İşaretsiz Tam Sayı (32 Bit) | 0 ~ 4.294.967.295 arası                                      |
| Sayısal        | long    | İşaretli Tam Sayı (64 Bit)  | -9.223.372.036.854.775.808 ~ 9.223.372.036.854.775.807 arası |
| Sayısal        | ulong   | İşaretsiz Tam Sayı (64 Bit) | 0 ile 18.446.744.073.709.551.615 arası                       |
| Ondalıklı Sayı | float   | Tek Kayan Sayı (32 Bit)     | ± 1,5 * 10 ^-45^ ~ ± 3,4 * 10 ^38^ arası                     |
| Ondalıklı Sayı | double  | Çift Kayan Sayı (64 Bit)    | ± 5 * 10 ^-324^ ~ ± 1,7 * 10 ^308^ arası                     |
| Ondalıklı Sayı | decimal | Ondalıklı Sayı (128 Bit)    | ±1,5 * 10 ^-28^ ~ ± 7,9 * 10 ^28^ arası                      |



**"string" keyword'u neden burada yer almıyor?**

> String: Metinsel ifadeleri tuttuğumuz değişken türüdür. Referans Türlüdür.

## Değer Türlü Değişkenlerde Primitive Kontrolü - IsPrimitive

Bir türün primitive olup olmayacağını nasıl inceleyebiliriz?

```csharp
//Main içerisinde

//Console.WriteLine(typeof(degiskenTuru).IsPrimitive); 
Console.WriteLine(typeof(int).IsPrimitive);
Console.WriteLine(typeof(char).IsPrimitive);
Console.WriteLine(typeof(decimal).IsPrimitive);
```

kodunu yazdığımız taktirde bizlere türün primitive olup olmadığını getirecektir.

## C# Kuralları 


>Değişken tanımalamaya gelmeden önce C# programlama diliyle ilgili kodlamaya dair bazı kurallardan bahsedelim.

**Biz kodu nerede yazacağız?**

```csharp
using System;

namespace Degiskenler
{
	class Program
	{
		static void Main(string[] args)
		{ //--> scope (faaliyet alanımız)
		
			//C# Dil Özellikleri
			//1. C# programlama dili büyük küçük harf duyarlılığına sahip olan bir dildir.
				//örn. Ahmet AHmet ahmet AHMET -> Farklıdır
				//a, A -> Farklıdır
			
			//2. C# programlama dili tip güvenliği olan bir dildir.
				//Tip güvenliği: Ram'e değişken aracılığıyla koyacağımız verinin türünü önceden bildirmemiz gerekir. 
		}
	}
}
```

###	Değişken Tanımlama

Prototip:

```csharp
/*
degiskenTuru degiskenAdi;
';' kod konseptini kapatan bir operatördür.
*/
string metin;
int sayi;
```

### RAM'in Yapısı (Stack)

>Ram'in yapısı temelde 2 yapılanmadan oluşmakta,
>
>>Bunlardan birisi Stack ve diğeri Heap

**Stack** : İçerisinde değişkenleri, değişken adlarını ve değerlerini tutabildiğimiz bölümdür.
örn.
x=5
y="Ahmet"

**Heap** : Nesneleri tutabildiğimiz bölümdür (Object Orianted Konusu)

<img src="https://imgur.com/nU69wDo.png" align=left>

### Değişkenler RAM'de Nasıl Tutulur?

> Tanımlanan değişkenler **Runtime** da, uygulama çalışırken, stackte tutulmakta ve kod ile senkronize bir şekilde alan tahsisi yapılmaktadır.

---

### Değişken Tanımlama Kuralları

#### Anlamlı İsimlendirme

*	Değişken isimleri süreçte developer açısından bir karışıklılığa sebep olmaması için anlamlı olmalıdır.
  * örn. int a; int b; yerine sayi1, sayi2 gibi isimlendirilmelidir.

#### Özel Karakterler

*	Değişken isimleri ',. vs.. gibi özel karakterler barındıramazlar!
*	_ karakteri istisnadır.

#### Sayısal ifadeler

*	Değişken isimleri sayısal ifadelerle başlayamaz!
*	Lakin sayısal ifade barındırabilir.

---

### İsimlendirme Kuralları (Name Convention)

#### Pascal Case

*	Her kelimenin ilk harfi büyük yazılmalıdır.
  *	AdSoyad
  *	TcKimlikNo
  *	Satislar
  *	DogumTarihi
*	Kısaltma iki harfliyse her iki harfte büyük yazılmalıdır.
  *	In/Out = IO
  *	InOutStream = IOStream

#### Camel Case

*	İlk kelime haricindeki tüm kelimelerin baş harfi büyüktür.
  *	satisDurumu
  *	personelAdi
  *	orderId
  *	userName
  *	user

#### Snake Case

*	Tüm kelimeler küçük olarak başlamalı ve araları _ karakteri ile ayrılmalıdır.
  *	kullanici_adi
  *	isim_soyisim
  *	personel_giderleri

---

### Değişken İsimlerini @ Operatörüyle Tanımlama

```csharp
string @x; // string x; ile aynı kapıya çıkar.
/*Değişken isimlerinde programatik keyword kullanılamaz! 
Eğer ki bir değişken isminde programatik olarak kullanılan bir keyword'ü vermek istiyorsanız.
Bunu @ operatörü ile ezebilir ve öyle verebilirsiniz
*/
//örn.
string @static;
```

---

### Tanımlanmış Değişkene Değer Atama

#### Tanımlarken Değer Atama

> Integer türünde x isimli bir değişken tanımlayalım,

```csharp
int x;
```

> Tanımladığımız bu değişken belleğin "STACK" kısmında tutuluyordu.
>
> >Hatırlatma : Belleğin STACK kısmında değer türlü değişkenler, değerleri ve tür bilgileri tutulur.

<img src="https://imgur.com/tE3viXo.png" align=left>

> Eğer ki tanımlama esnasında bu değişkene değer atamak istersek;
>
> > Konsepti kapatmadan önce '=' assign(atama) operatörünü kullanarak ilgili değişkenin türüne uygun bir değer (9) göndereceğiz.

```csharp
int x = 9 ;
```

> Burada sol tarafta bir değişkenimiz var,
>
> > Arada '=' assign(atama) operatörümüz var
> >
> > > sağ tarafta ise atanacak değer yer alıyor.

>Not: Assign Operatörü sağ tarafta verilen değeri sol tarafta ilgili değişkene (veya field,property vs..) atar.

>Kodumuza dönecek olursak;

```csharp
int x = 9 ;
```

> Compiler bu kodu işlerken daha sonlandırmadan 9 değerini bu alana atar.<img src="https://imgur.com/xHccWkX.png" align=left>

### Başka bir örnek ile devam edelim

```csharp
int sayi1;
int yas = 26;
string ad = "Metin";
string soyad;
```

>Anlattıklarımızdan yola çıkarak, buradaki işlemi şu şekilde düşünebiliriz;

<img src="https://imgur.com/2cjU9Cq.png" align=left>

> sayi1 ve soyad değişkenlerine tanımlarken değer atamadığımız için herhangi bir değerleri bulunmuyor.
>
> > Daha sonra değer atamaya örnek vererek devam edelim,

### Tanımlandıktan Sonra Değer Atama

```csharp
int sayi1;
int yas = 26;
string ad = "Metin";
string soyad;

/*
...Burada devam eden kodlarımız olduğunu düşünelim..
*/

sayi1 = 123;
ad = "Ali";
soyad = "Yılmaz";
```

> Bu durumda ise STACK yapısı şu şekilde gelişecektir;

<img src="https://imgur.com/mV3DJ6o.png" align=left>

>**Burada dikkat etmemiz gereken çok önemli bir nokta var.**
>
>> Eğer ki bir değişken ismi assign operatörünün solunda çağırılıyorsa o alana değişkenin kendisi gelecektir.

> > Değişken ismi assign'ın sağında çağırıldığı zaman ise değişkenin değeri gelecektir.

<img src="https://imgur.com/YgBWHVj.png">

#### Dikkat !

> Bir değişkene atanan en son değer geçerlidir.

```csharp
int a;
int b = 30;
a = 15;
a = 20;
a = b;
```

<img src="https://imgur.com/0gYC0zz.png">


### Değişkene Değer Atama Kuralları

> 4 farklı türde değerlerimizi kategorize edelim,

1. Metinsel Değerler

   * string : Metinsel ifadeler çift tırnak içerisinde yazılmalıdır "..."

     ```csharp
     string isim = "Metin";
     string mSayi = "1234";
     /*
     "Metin","1234" -> Bir sayısal ifade metinsel olarak tutuluyorsa eğer, yazılım açısından metinsel bir ifadedir. Yani üzerinde matematiksel işlem yapılamayan ve "Ali","Ahmet" vs. gibi metinsel ifadelerden farkı olmayan bir değerdir.
     */
     Console.WriteLine(mSayi+10);//Dediğimizde bize çıktı olarak 123410 gösterilecektir.
     
     //"Ali 26 yaşındadır." : string -> çift tırnak içerisine yazılan tüm değerler string keyword'ü ile karşılanmalıdır. => string x = "qwdfqwf"
     ```

2. Karaktersel Değerler

   * char : Karaktersel ifadeler tek tırnak içerisine yazılmalıdır. '.'

     ```csharp
     char karakterA = 'A';
     string metinA = "A";
     /* 'A',"A" -> Dikkat : Tek tırnak içerisine yazılan ifade karakterdir, çift tırnak içerisindeki string dir. Tek bir karakterlik değer tutulması gereken yerde string kullanılırsa (bellek optimizasyonu açısından) boş yere alan tahsisinde bulunulmuş olur.
     */
     /*Gerçek hayattan örnek vermek gerekirse; 1 tane çiçek için saksı (char) yeterli olacak iken 1 dönüm tarla(string) kiralanmış olarak düşünebilirsiniz.*/
     
     char karakter = 'AB'; // Hatalı : Tek bir karakter atanabilir. Compiler hata verecektir.
     
     
     ```

3. Mantıksal Değerler

   * bool : Mantıksal ifadeler direkt olarak true ya da false ile belirtilir.

     ```csharp
     bool medeniHal = true; yada = false; // true : 1 // false : 0
     ```

4. Sayısal Değerler

   * Sayısal ifadelere değer atarken direkt olarak değeri göndeririz.

     ```csharp
     int sayi = 1000;
     ```

     

   > Sayısal ifadelerde bir değer(tamsayı) default (varsayılan) olarak **int** türünde kabul edilir.

   * Ondalıklı Sayılar: Tüm ondalıklı sayılar tamsayıları karşılayabilirler.

     * float : Float türünde bir küsüratlı değer tutarken ilgili değerin sonuna f ya da F getirilmelidir.

     ```csharp
     float sayi1 = 3.14f;
     ```

     * double : Double türünde bir küsüratlı değer tutarken ilgili değerin sonunda d ya da D getirilmelidir.

       ```csharp
       double sayi2 = 3.14d;
       ```

     * decimal : Decimal türünde bir küsüratlı değer tutarken ilgili değerin sonuna m ya da M getirilmelidir.

       ```csharp
       decimal sayi3 = 3.14m;
       ```

   > Ondalıklı türlerde bir değer örn 3.14 default(varsayılan) olarak **double** türünde kabul edilir.
   > <br>Ondalıklı bir değeri double da tutarken d ya da D'yi kullanmak zorunda değiliz!
   >
   > ```csharp
   > double sayi4 = 3.14;
   > ```
   >
   > 

### (_a,_b)=(a,b) Tuple Türüyle Değer Atama

> Tuple : Tek bir syntax üzerinde birden fazla değişken tanımlamamızı sağlayan bir nesnedir.

`(int a, int b, type c, type d...) z;` -> Tuple değişken, çünkü z içerisinde int, int, type vs.. olmak üzere birden fazla farklı yahut benzer türde değişken tanımı mevcuttur.

`(int a, string b) c = (5, "metin");` -> Tanımlamamız bu şekilde

>Peki c içerisindeki bir değişkene erişmek istersek
>
>> İleride göreceğimiz modifier access operatörü '.' c içerisindeki bir değişkene erişmemizi sağlar.

```csharp
(int a, string b) c = (5, "metin");
//c.a -> bize integer değişkeni getirecektir.
//c.b -> string değişkeni getirecektir.

```

> Not : Tuple nesnesi, tek bir değişken içerisinde birden fazla değişken tutuyor.
>
> O değişkenlerin de kendilerine ait değerleri var.

```csharp
(int yas, string adi, bool medeniHal) kisi = (27, "Mustafa", false);
```

>Nesnenin değerden farkı, değerlerle bir araya gelmesidir. Tek bir değer değildir.

#### Değer Atarken

```csharp
(int yas, string adi, bool medeniHal) kisi;
//kisi.yas = 24;
//kisi.adi = "Fatma";
//kisi.medeniHal = false;

// veya

kisi = (24, "Fatma", false); // Tuple oluştururken/tanımlarken değişken türleri hangi sırada
				//verildiyse, değerler aynı sıra ile atanabilir.
```

---

### Literal Düzenlemeler (C# 7.0)

>Kompleks sayısal ifadeleri _(Alt Tire) ile düzenlememizi sağlayan özelliktir.

```csharp
int sayi = 9_876_543; // 9876543 yerine _ kullanarak daha okunabilir halde kullanabiliriz.
```

### Default Literals - Değişken Türüne Uygun Default Değer Atama

>İleride OOP dediğimiz yaklaşımı gördüğümüzde class içerisinde tanımlanan değişkenlerin otomatik atandığını konuşacağız.

>Metinsel ifadelerde string : null değeri atanır.
>
>> Null : değersiz, değeri yok anlamına gelir. Boş demek değildir.
>>
>> >Boşluk space dediğimiz boştur ama yine bir karakterdir.

*	string : null
*	char = '0'
*	sayısal ifadelerde : 0
*	bool : false

>Main içerisinde atanmaz, class içerisinde yazdığımızı varsayarak *default* keyword'ünü bir değişkene atayalım.

```csharp
//default keywordü : içerisine verilen türün varsayılan değerini geri döndürür.
bool x = default(bool); //false değerini atar
int y = default(int); //0 değerini atar
string z = default(string); //null değerini atar
char c = default(char); // \0 varsayılan değer atanır

```

>**! Dikkat !** : *Main* içerisinde oluşturulan değişkenlerin *ilk değerlerini manuel atamaya özen gösteriniz.*
>
>> Main içerisinde oluşturulan değişkenlerin ilk değerlerini compiler kendisi veremez.

## Tanımlanmış Değişkenin Değerini Okuma

>Bir değişkenin değerini elde edebilmek için değişkenin adından faydalanmaktayız.
>
>> Bir değişkenin adı assign(=) operatörünün sağında veya metotların parametrelerinde çağırılıyorsa, ilgili değişkenin değeri gönderilir.

<img src ="https://imgur.com/kdE2vkM.png">

### Kritik 1

```csharp
int sayi1 = 5;
int sayi2 = 10;
int sayi3 = sayi2;
int sayi4 = sayi1;
sayi2 = sayi1;
sayi3 = sayi2;
```

> Kodlarımızı **STACK** üzerinde düşünecek olursak sırasıyla atanacak değerler şu şekilde olacaktır.
>
> sayi1 : Tanımlanırken verilen değer 5  atanır.
>
> sayi2 : Tanımlanırken verilen değer 10 atanır.
>
> sayi3 : sayi2 değişkeninin değeri yani 10 atanır.
>
> sayi4 : sayi1 değişkeninin değeri yani 5 atanır.
>
> > sayi2 : sayi1 değişkeninin değeri (5) çağırılır ve atanır.
> >
> > sayi3 : sayi2 değişkenine atanan **son değer (5)** çağırılır ve atanır.

<img src="https://imgur.com/xXIsYQf.png" align=left>

> Son haliyle değerlerin hepsi 5 olacaktır.

### Kritik 2

```csharp
int sayi = 5;
sayi = sayi;
```

> Kodlarımızı tekrar STACK üzerinde düşünecek olursak;
>
> sayi değişkeni tanımlanır ve 5 değeri atanır.
>
> > Ardından sayi değişkenine kendi değeri tekrar çağırılır ve atanır.

<img src="https://imgur.com/R4uW7n4.png" align=left>

## Değeri Olmayan Değişkenler

> Class içerisinde tanımlanan değişkenlerde varsayılan değer otomatik atanmaktadır.

```csharp
class Deneme
{
    int a; // Default : 0
    Console.WriteLine(a);
    int b = a;
}
```

> Main içerisinde tanımlanan değişkenlerde varsayılan değer atanmadığı için, böyle boş tanımlanan değişkenlerde ilk değeri manuel vermediğimiz sürece işlem yapamayız.

```csharp
static void Main(string[]args)
{
	int a;
    Console.WriteLine(a); // Compiler hata verecektir.
    int b = a;
}
```

> Bir metot içerisinde tanımlanan değişkenlerin ilk değerlerini manuel olarak vermeyi alışkanlık haline getiriniz.
>
> > Çünkü programın rahatça işlenebilir ve kodlanabilir olması için.

## Değişken Davranışları Genel Bakış (ref için farkındalık)

```csharp
int a = 5;

metot (a)
{
//...    
}

```

> Bir değişken tanımladığımızda STACK de bellek alanı tahsis ediliyordu. Burada integer(tamsayı) türünde a diye bir değişken tanımladık ve 5 değerini atadık.
>
> > Değişken ismi sol tarafa geldiğinde STACK deki bellek adresi çağırılır, sağ tarafa geldiğinde ise değeri çağırılır demiştik.
> >
> > > Metotlarda/ Fonksiyonlarda ise değerinin geldiğinden bahsetmiştik.
> >
> > Davranışsal olarak baktığımızda ise x ve y diye bir değişken tanımladığımızı farz edelim. Burada sol tarafta olan y (bellek adresi çağırılır), sağ tarafta ise 30 değeri mevcut.
> >
> > > assign(=) operatörü ile soldaki y(bellek adresine), sağdaki 30 değerini atamamızı sağlıyordu.
> >
> > Değişkenin değerini çağırmak ile kendisini(bellek adresini) çağırmak arasındaki farkı anlamamız çok önemli.

<img src="https://imgur.com/RzjzkSl.png" align=left>

> Davranışlarımız bu şekilde, ileride göreceğimiz ref keyword'üne hazırlık olması açısından incelemiş olduk.

## Değişkenlerin Faaliyet Alanları (Scope Kavramı)

### Scope Nedir?

> Scope : Faaliyet alanıdır, bir başka deyişle kapsam.
>
> > Değişken ve fonksiyonların erişilebilirlik sınırlarını belirleyen alandır.
> >
> > Tanımlamalarda ve algoritmik çalışmalarda karışıklılığı önleyen bir sınır çizer.
>
> C# : Süslü parantez { } ile ifade edilir.



> Bir değişken tanımlandığı scope aralığı ve içerisindeki scope'lar erişilebilir.

```csharp
{
    int a = 5;
    b = False; // Erişilemez!
    {
        a = 10; // Erişilebilir.
        bool b;
    }
}
{
    a = 15; // Erişilemez.
    b = False; // Erişilemez!
}
```

> Bir scope aralığında aynı isimde birden fazla değişken tanımlanamaz.

```csharp
{
    int a;
    {
        string a; //Tanımlanamaz.
        {
            char a; // Tanımlanamaz.
        }
    }
}
{
    bool a; //Farklı scope aralığında olduğu için tanımlanabilir.
}
```



## Custom Scope Oluşturmak

>Kullanım alanları:
>
>* namespace'lerde
>* class'larda
>* metotlarda
>* karar yapılarında ve döngülerde kullanıyoruz.
>
>Bu alanlar dışında kendimiz de scope oluşturabiliyoruz.
>
>Metodu faaliyet alanlarına bölebiliyoruz.

```csharp
namespace Degiskenler
{
    class Program
    {
        static void Main(string[]args)
        {
            #region Custom Scope Örnek
            {
                //a değişkenine buradan erişilemez!
                {
                        int a = 5;
                    {
                        a = 1; // buradan erişilebilir.
                    }
                    a = 3; // buradan da erişilebilir.
                }
                {
                    //a değişkenine buradan da erişilemez!
                }
            }
            //region başlangıcından itibaren oluşturduklarımız custom scope'dur.
            #endregion
        }
    }
}
```



## Sabitler (const)

* Sabitler; değişmeyen değerleri tutmak için oluşturulmuş yapılardır.

  Süreçte var olan değeri değiştirilemez, değiştirilmeye çalışıldığı taktirde compiler tarafından hata verilir.

**const keyword'ü**

* İngilizce deki constant (sabit) kelimesinden gelir.
* Değişmeyendir.
* Prototip olarak değişkenlere çok benzer lakin davranışsal olarak değeri bir daha değiştirilemez.
  * *Değeri tanımlanırken verilir, daha sonradan değiştirilemez veya tanımlanamaz.*
* Özünde static yapılanmadır.
  * Static: Uygulama bazlı veri depolayabildiğimiz bellekte bir alandır. 

**Static ile const arasındaki fark**

* static değişkenler adı üzerinde değerleri değişebilir; const'lar sabittir.

**readonly keyword'ü**

* Sadece okunabilir değişkenler tanımlamaktadır.

* const'tan farkı sadece tanımlandığı yerde değil, ayrıca constructor içerisinde de değeri atanabilir. 

  Dependency Injection deseninde çok sık tercih edilir.

* Ayrıca static değildirler.

**Kod üzerinden inceleyelim**

```csharp
double pi = 3.14;
/*
... Kodlarımız olduğunu düşünün.
*/
/*
... Bilmeyerek bir yerde pi değişkenine yeni değer atayarak değiştirirseniz.
*/
pi = 123; // Hata vermez ancak mantıksal hatalara sebep olabilir, bölye durumlarla karşılaşmamak için const kullanırız.
```

**veya**

> Bizim oluşturduğumuz bir koddaki değişkenin değerini,  aynı kodu kullanan başka bir developer'a değiştirtmememiz gerektiği durumlarda onu const yaparız.

```csharp
//const degiskenTipi degiskenAdi; 
//Bir const tanımlandığında STACK'te ilgili türde alan tahsis edilecektir ve ilk atanan değer dışında bir daha değer kabul edilmeyecektir.
//const'lar değiştirilemez lakin istenildiği kadar okunabilir, değerleri elde edilebilir...
```

```csharp
const double pi = 3.14;
const double r; //Compiler hata verir, ilk değer tanımlanırken atanmak zorundadır.
/*
... Kodlarımız olduğunu düşünün.
*/
pi = 123; // Compiler hata verir, ilk değer atandıktan sonra değeri değiştirilemez.
```



## Global Değişkenler

```csharp
namespace GlobalDegisken
{
    class Program
    {
        //Bir değişken class scope içerisinde tanımlanıyorsa (class elemanıysa) buna global değişken diyoruz...
     static void Main(string[] args)
     {
         //Metot içerisinde tanımlanıyorsa local olarak ele alınır.
         int a;
         {
             
         }
         {
             {
                 
             }
         }
     }
    }
}
```



## Değişken Tanımlama Varyasyonları

> Değişken tanımlarken, 2 varyasyon üzerinden tanımlama yapılabilmektedir.
>
> > Kod üzerinden inceleyelim.

```csharp
#region Varyasyon 1
    //int a = 5;
    //int b = 10;
    //int c;
    //int d;
#endregion
#region Varyasyon 2
    //Aynı türden birden fazla değişken oluşturulacaksa eğer bu değişkenleri tek imzada aşağıdaki gibi tanımlayabiliriz.
    int a = 5, b = 10;
    int c, d;
#endregion
```

> Dikkat edilmesi gereken husus **aynı türden** olmaları gerekiyor.

## Değişkenler Arası Değer Atama

* Değişkenler arası değer atanırken verisel açıdan iki davranış söz konusudur.
  * Deep Copy
  * Shallow Copy

### Deep Copy  (Derin Koplayalama)

> A ve B olarak 2 değer türlü değişkenimiz olduğunu düşünelim.

```csharp
int A = 5;
int B;
```

<img src="https://imgur.com/lJjxwnb.png" align=left>

* Değer türlü değişkenler birbirlerine atanırken ***default*** olarak **deep copy** geçerlidir. Yani veri otomatik olarak türetilir.

  Kod üzerinden inceleyelim.

  ```csharp
  int a = 5;
  int b = a;
  
  //Eğer ki değer türlü değişkenlerde default olarak deep copy geçerli ise, a'da yapacağımız değişikliklerin b'ye yansımaması gerekir.
  a = a * 5;
  Console.WriteLine(a);
  Console.WriteLine(b);
  
  /*
  Çıktı:
  25
  5
  */
  ```

  

### Shallow Copy (Yüzeysel Kopyalama)

> A ve B olmak üzere 2 referans türlü değişkenimiz olduğunu düşünelim.

* <img src="https://imgur.com/F1qKQmk.png" align=right>Değişkenler arası değer atamalarında değeri türetmek/çoğaltmak/klonlamak yerine var olanı birden fazla referansla işaretlemeye dayalı kopyalama yöntemidir.

* Bellekte birden fazla referansın tek bir veriyi işaret etmesidir.

* Neticede ilgili değer bir değişikliğe uğradığında tüm işaretleyen referanslara bu değişiklik yansıyacaktır.

  Normalde Değer Türlü değişkenler default olarak Deep Copy edilirler.

  Bu eğitimin ilerideki konusu olan 'ref keyword'ü ile Değer Türlü değişkenlerde nasıl Shallow Copy yapıldığını ele alacağız.

  Shallow Copy OOP derslerinde ele alacağımız nesne ve referans arasındaki ilişkide varsayılan davranış olarak kabul edilmektedir.

  Bu konuyla ilgili eğitimlerimizde değinirken, nesneler üzerinde de Deep Copy'nin nasıl gerçekleştirileceğini de ele alacağız.

## Object

**object Nedir?**

> Bildiklerimizden yola çıkarsak,
>
> >```csharp
> >int yas = 23; //Sağdaki 23 değeri integer olduğu için karşılayabilir
> >string babaAdi = "Ahmet"; //Sağdaki değer string(metinsel) bir değer olduğu için karşılayabilir
> >
> >bool soyad = "Duman"; // Sağdaki değer matıksal bir tür olmadığı için karşılayamaz!!
> >```
>
> > <img src="https://imgur.com/PbZhwWJ.png" align=left>
>
> Tüm türler varsayılan olarak object'ten türerler.
>
> > <img src="https://imgur.com/CLWJEyN.png" align=left>
> >
> > Dolayısıyla object tüm türleri karşılayabilen bir türdür diyebiliriz.
> >
> > ```csharp
> > int yas = 23;
> > string ad = "Ahmet";
> > 
> > object objYas = yas;
> > object objAd = ad;
> > ```
>
> > <img src="https://imgur.com/WNCL8wK.png" align=left>
> >
> > * Object değişkenler ilgili verileri RAM'de object türünde tutarlar. Lakin verinin öz türünü de içerisinde bozmadan saklarlar. (Boxing)
> >
> > * Yani object içerisindeki veri kendi öz türünde tutulur.
> >
> >   Bu durum object içerisindeki veriyi kendi türünde tekrar elde edebiliriz anlamına gelmektedir. (Unboxing)

### Boxing

> Object türdeki bir değişkene herhangi bir türdeki değeri göndermek Boxing olarak nitelendirilmektedir.

```csharp
int yas = 28;
object _yas = 28; // Boxing
```

<img src="https://imgur.com/x3ARKfn.png" align=left>

> Boxing işlemi neticesinde ilgili değer objectin içerisinde kendi türüyle saklanır.
>
> Lakin! _yas değişkeni artık 28 değerini bizlere object türünde getirecektir.
>
> > Burada dikkat ederseniz, object türünden elde edilen değer üzerinde türüne özgü işlemler gerçekleştirilemez.
> >
> > Örneğin; sayısal bir değer varsa o değer object olarak geleceğinden dolayı matematiksel işlemler yapılamaz!
>
> * Object bir değişkenin içerisindeki değer üzerinde  türüne özgü işlemler yapabilmek için o object'in içerisindeki değeri kendi/has/özgün türünde
>
>   elde etmemiz gerekmektedir. İşte bu işleme de Unboxing diyeceğiz..
>
> * Herhangi bir değer object türüne assign ediliyorsa eğer bu işlem Boxing'dir.

### Cast Operatörü

> Cast operatörü : Boxing edilmiş bir veriyi kendi türünde elde etmemizi sağlayan bir operatördür.
>
> > Tür dönüşümlerinde 'bilinçli tür dönüşümü' konusunda Cast operatörünü kullanacağız..
> >
> > Kalıtımsal durumlarda da karşımıza çıkacaktır.
>
> * '(T)' cast operatörü parantezdir.
>
>   Cast operatörü, object olan değişkenin solunda o object'i hangi türe Unboxing etmek istiyorsak parantez içerisine hedef türü bildirerek kullanılır.
>
>   ```csharp
>   int a = 5;
>   object b = a;
>         
>   (int)b; //-> Cast operatörü b değişkeni/objesi içerisindeki değeri bana int olarak ver demektedir.
>   ```
>
> 

### Unboxing - Casting

```csharp
object _yas = 28; // Boxing

#region Casting
//Console.WriteLine(_yas * 5); //-> Dediğimizde compiler bize hata verecektir. Bunu yapabilmek için objedeki değeri unboxing etmemiz gerekir
int yas = (int)_yas; // Unboxing
Console.WriteLine(yas * 5);
#endregion
```

> * Unboxing esnasında Boxing edilmiş verinin orjinal türü ne ise o bildirilmelidir.
>
>   Yani int türünde boxing edilmiş bir değeri int türünde unboxing etmeliyiz.
>
>   Gidipte int türünde boxing edilmiş bir veriyi char türünde unboxing etmeye çalışıyorsanız compiler hata verecektir.

* ***Boxing ve Unboxing işlemleri runtime'da gerçekleşir.***

## var

> var keyword'ü : Genellikle değişken türü olarak bilinir, halbu ki alakası yoktur. var bir keyword'dür ve belirli bir işlemi yapan keyword'dür.

> Örneğin, medeni hali tutmak istiyoruz.
>
> ```csharp
> bool medeniHal = true;
> ```
>
> * Neye göre türü belirttik?
>
>   Tutacağımız değere göre türünü belirttik.
>
> * Eğer ki tutacağımız değere göre türünü Compiler'a belirletmek istiyorsak, işte o zaman var keyword'ünü kullanabiliriz.
>
>   ```csharp
>   //Tutulacak değerin türüne uygun bir değişken tanımlayabilmek için kullanılan keyworddür.
>   var medeniHal = true; // Boolean olduğundan dolayı var, bool türüne bürünecektir.
>         
>   //var keyword'ü, compiler tarafından değerin türüne göre otomatik olarak büründürülen bir keyworddür. Lakin bir tür DEĞİLDİR!
>   ```
>
>   Genellikle, yazacağımız değişkenlerin türlerini yazmaktan üşendiğimiz için kullanmaktayız! 
>
>   Halbuki esas olma sebebi ise, farklı diller arasında desteklenmeyen türlerdeki verileri karşılayabilmek için oluşturulmuş ortak bir keyworddür.
>
>   Diller arasındaki entegrasyonda kullanılıyordu...
>
> ```csharp
> var yas = 25; //-> Türünü bilebildiğimiz verilerin değişken türlerini var ile compiler'a yaptırmak ufak da olsa bir maliyettir.
> 				//Onun için bizler bu maliyetten kaçınmak adına bildiğimiz türleri mümkün mertebe üşenmeden belirteceğiz..
> ```
>
> 1. var keywordüyle tanımlanan değişkenin değeri tanımlanma aşamasında verilmelidir. Verilmelidir ki türü belirleyip direkt ona dönüşebilsin o türde davranış sergileyebilsin.
>
> 2. var keywordüyle tanımlanan değişkene ilk değer verildikten sonra o değerin türüne bürüneceği için sonraki durumlarda değeri farklı türlerde verilemez!!!
>
> 3. var - object arasındaki fark;
>
>    ```csharp
>    var x = 5; //operasyonel bir keyworddür.
>    object y = 15; //object bir türdür.
>             
>    //var atanan değerin türüne bürünürken, object atanan değeri Boxing yaparak object'e dönüştürür.
>    ```
>
> 



## dynamic

> dynamic keyword'ü : var 'a çok benzer, sadece var 'ın runtimedaki versiyonudur.

```csharp
//Compile Süresinde/Development Aşamasında;
var a = 5;
/*
.
.
.
a int davranışı sergileyecektir...
*/

//Ne zaman ki uygulama derlenip çalıştırılır(runtime'da) o zaman dynamic ilgili değerin türüne bürünmüş olacaktır..
dynamic _a = 5;
/*
.
.
.
development aşamasında a'nın hala dynamic olduğu gözlemlenecektir.
*/
```

> * var; derleme aşamasında değerin türüne bürünürken, dynamic ise; runtime'da verilen değerin türüne bürünecektir.
>
> * dynamic keywordü runtime'da türü belirleyecektir lakin kararlı davranmayacaktır.
>
>   ```csharp
>   dynamic x = "Ahmet";
>   Console.WriteLine(x.GetType());
>   x = 3.14D;
>   Console.WriteLine(x.GetType());
>         
>   /*
>   Çıktı:
>   System.String
>   System.Double
>   */
>   ```

**Dynamic Nerelerde Kullanılır?**

> Dynamic keywordünü uzaktan gelen verileri karşılarken kullanırız. (int, bool, Personel, Insan, Satis vs..)
>
> * Uzaktan gelen veriler var keyword'ü ile karşılanamaz!!
>
>   Çünkü var keywordü tanımlandığı esnada verinin atanmasını ister!!



------

# Kod Konsepti



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
> class Program
> {
>   static void Main(string[] args)
>   {
>       int a = 5;
> 			string b = "Mustafa";
>   }
> }
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



------

# Tür Dönüşümleri (Type Conversion)



## Tür Dönüşümü Nedir? Neden Verilerin Türlerini Değiştirmek/Dönüştürmek İsteriz?

> Konumuzun mahiyeti şudur, varsayalım elimizde T1 türünde n isminde değerimiz olsun, bunu biz süreçte T2 türünde veriye dönüştürebiliyoruz.
>
> * Yazılım sürecinde elimizdeki değerlerin türlerini değiştirebilmekteyiz.
>
>   <img src ="https://imgur.com/Poj11oX.png" align=left>
>
> >  Peki bir yazılımcı neden verilerin türlerini değiştirmek/dönüştürmek isteyebilir?
> >
> >  * Diyelim ki elimizde bir elma var, biz bunu elma türünde tutabiliriz ya da meyve türünde de tutabiliriz.
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
> > `(byte)a ` artık byte türünde olacağı için short'a atanırken de bilinçsiz tür dönüşümü gerçekleşecektir.
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



------

# Operatörler



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
>  sonuc = sayi * 5;
> }
> else if (sayi >= 9 && sayi % 2 == 0)
> {
>  sonuc = sayi * 10;
> }
> else if (sayi > 3 && sayi < 9)
> {
>  sonuc = sayi * 3;
> }
> else if (sayi % 2 == 1)
> {
>  sonuc = sayi;
> }
> else
> {
>  sonuc = -1;
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



------

# Akış Kontrol Mekanizmaları



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
> >  case "Mehmet": //Bunlar değişken olamaz!
> >      Console.WriteLine("Adı Mehmet");
> >      break;
> >  case "Ayşe":
> >      Console.WriteLine("Adı Ayşe");
> >      break;
> >  case "Hilmi":
> >      Console.WriteLine("Adı Hilmi");
> >      break;
> >  default : //case bloklarından hiçbiri eşleştirmeye uymuyorsa eğer, varsa default bloğu tetiklenir
> >      Console.WriteLine("Hiçbiri değil.")
> >      break;
> >      //default bloğu yoksa, ve hiçbiri eşleştirmeye uymuyorsa switch case'den çıkar.
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
> >  case 1000 when (3 == 5): //Konseptin içindeki şart doğrulandığı zaman buradaki blok tetiklenecektir.
> >      Console.WriteLine("Case doğrulanır, ikinci şart doğrulanmadığı için sonraki case'e geçer!");
> >      break;
> >  case 1000 when (3 == 3):
> >      Console.WriteLine("Case doğrulanır, ikinci şart da doğrulandığı için yazdırılır.");
> >      break;
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
> >  case "a":
> >      //A islemini uygula
> >      break;
> >  case "b":
> >      //B islemini uygula
> >      break;
> >  case "c":
> >      //A islemini uygula (tekrar kod)
> >      break;
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
> >  case 5:
> >      Console.WriteLine(i * 10);
> >      break;
> >  case 6:
> >      Console.WriteLine(i / 5);
> >      break;
> >  case 7:
> >      Console.WriteLine(i * 10);//Tekrar
> >      break;
> >  case 10:
> >      Console.WriteLine(i * 10); //Tekrar
> > }
> > ```
> >
> > Bu şekilde kod tekrarının olduğu durumlarda goto keywordunu şöyle kullanabilmekteyiz;
> >
> > ```csharp
> > int i = 10;
> > switch(i)
> > {
> >  case 5:
> >      Console.WriteLine(i * 10);
> >      break;
> >  case 6:
> >      Console.WriteLine(i / 5);
> >      break;
> >  case 7:
> >      goto case 5; //Case 5'deki kodu çalıştır demiş oluyoruz, goto kullanılan case'de break komutunu kullanmıyoruz!
> >  case 10:
> >      goto case 5; //Case 5'deki kodu çalıştır demiş oluyoruz, goto kullanılan case'de break komutunu kullanmıyoruz!
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
>   >      DayOfWeek.Monday => "Bugün Pazartesi",
>   >      DayOfWeek.Tuesday => "Bugün Salı",
>   >      DayOfWeek.Wednesday => "Bugün Çarşamba",
>   >      DayOfWeek.Thursday => "Bugün Perşembe",
>   >      DayOfWeek.Friday => "Bugün Cuma",
>   >      DayOfWeek.Saturday => "Bugün Cumartesi",
>   >      DayOfWeek.Sunday => "Bugün Pazar"
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
>   >  case 5:
>   >      isim = "Hilmi";
>   >      break;
>   >  case 7:
>   >      isim = "Rıfkı";
>   >      break;
>   >  case 10:
>   >      isim = "Mustafa";
>   >      break;
>   > }
>   > */
>   > 
>   > //Switch Expression (Yeni Yöntem)
>   > int i = 10;
>   > string isim = i switch
>   > {
>   >      5 => "Hilmi",
>   >      7 => "Rıfkı",
>   >      10 => "Mustafa"
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
>
>>```csharp
>>int i = 10;
>>string isim = i switch
>>{
>>   5 when 3 == 3 => "Hilmi", //case durumu yani 5'i ye eşitse ve ikinci şart olan 3 == 3 true ise çalışacaktır.
>>   7 when 5 == 3 => "Rıfkı", //case durumu yani 7'i ye eşitse ve ikinci şart olan 5 == 3 true ise çalışacaktır.
>>   10 when 10 > 9 => "Mustafa" //case durumu yani 10'i ye eşitse ve ikinci şart olan 10 > 9 true ise çalışacaktır. 
>>};
>>```
>
>> 2.Kullanım
>
>> ```csharp
>> int i = 10;
>> string isim = i switch
>> {
>>      //5 when 3 == 3 => "Hilmi", olarak kullanılabilmesinin yanında bir değişken tanımlayarak da kullanılabilir.
>>      var x when x == 5 && x % 2 == 1 => "Hilmi",
>>      var x when x == 7 && x % 2 == 1 => "Rıfkı",
>>      var x when x == 10 && x % 2 == 1 => "Mustafa",
>>      var x => "Hiçbiri" //default : Hiçbir eşleştirmenin olmadığı durumda default tanımlamasına karşılık gelecektir.
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
>   >      ("Hüseyin", 20) => mesaj = "Hoşgeldin Hüseyin",
>   >      ("Cansu", 37) => mesaj = "Hoşgeldin Cansu",
>   >      ("Nalan", 21) => mesaj = "Hoşgeldin Nalan",
>   >      ("Nevin", 27) => mesaj = "Hoşgeldin Nevin",
>   >      ("Hilmi", 35) => mesaj = "Hoşgeldin Hilmi",
>   >      (_,_) => "Hoşgeldin" //Default
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
>   >  case (5, 10):
>   >      mesaj = "5 ile 10 değerleri";
>   >      break;
>   >  case (10,20):
>   >      mesaj = "10 ile 20 değerleri";
>   >      break;
>   >  default :
>   >      mesaj = "Değer bulunamadı";
>   >      break;
>   > }
>   > Console.WriteLine(mesaj);
>   > //Daha gelişmiş bir yapılanma ile ise;
>   > string mesaj2 = (s1, s2) switch
>   > {
>   >      (5,10) => mesaj = "5 ile 10 değerleri",
>   >      (10,20) => mesaj = "10 ile 20 değerleri",
>   >      (_,_) => "Değerler bulunamadı"
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
>      (5,10) when (true) => "5 ile 10 değerleri",
>      var x when x.s1 % 2 == 1 || x.s2 == 10 => "10 ile 20 değerleri"
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
>  class Program
>  {
>      static void Main(string[]args)
>      {
>          Ogrenci ogrenci = new Ogrenci
>          {
>              Adi = "Mustafa",
>              Soyadi ="KURT",
>              Meslek = "Öğrenci"
>          };
>          /*
>          double maas = 0;
>          switch (ogrenci.Meslek)
>          {
>              case "Kasap":
>                  maas = 8000;
>                  break;
>              case "Tesisat Ustası":
>                  maas = 7500;
>                  break;
>              case "Otobüs Şöförü":
>                  maas = 7800;
>                  break;
>              case "Öğrenci":
>                  maas = -2000;
>                  break;
>          }
>          Console.WriteLine(maas);
>      *///-> Burada yapılan işlemleri switch expression ile bu şekilde gerçekleştirebiliyoruz.
>          double maas = ogrenci switch
>          {
>                  { Meslek: "Kasap" } => 8000, //Meslek propertysine bu şekilde erişebiliyoruz.
>                  { Meslek: "Tesisat Ustası" } => 7500,
>                  { Meslek: "Otobüs Şöförü" } => 7800,
>                  { Meslek: "Öğrenci" } => -2000
>          };
>          Console.WriteLine(maas);
>      }
>  }
>  class Ogrenci
> 	{
>  	public string Adi {get; set;}
>  	public string Soyadi {get; set;}
>  	public string Meslek {get; set;}
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
>  class Program
>  {
>      static void Main(string[]args)
>      {
>          Ogrenci ogrenci = new Ogrenci
>          {
>              Adi = "Mustafa",
>              Soyadi ="KURT",
>              Meslek = "Öğrenci"
>          };
> 
>          double maas = ogrenci switch
>          {
>                  { Meslek: "Kasap" } => 8000, //Meslek propertysine bu şekilde erişebiliyoruz.
>                  var x when x.Meslek == "Tesisat Ustası" => 7500,
>                  { Meslek: "Otobüs Şöförü" } when !true => 7800,
>                  var x when x.Meslek == "Öğrenci" } => -2000,
>                  var x => 0 //ya da _ => 0 //Default
>          };
>          Console.WriteLine(maas);
>      }
>  }
>  class Ogrenci
> 	{
>  	public string Adi {get; set;}
>  	public string Soyadi {get; set;}
>  	public string Meslek {get; set;}
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
>  class Program
>  {
>      static void Main(string[]args)
>      {
>          Ogrenci ogrenci = new Ogrenci
>          {
>              Adi = "Mustafa",
>              Soyadi ="Kurt",
>              Meslek = "Öğrenci"
>          };
> 
>          var isim = ogrenci switch
>          {
>                  ("Ahmet", "Yıldırım") => "Ahmet Yıldırım",
>                  ("Hilmi", "Celayir") => "Hilmi Celayir",
>                  ("Semih", "Fidan") => "Semih Fidan",
>                  ("Mustafa", "Kurt") => "Mustafa Kurt",
>                  (_,_) => "Hiçbiri",
>                  _ => "Hiçbiri"
>          };
>      }
>      class Ogrenci
> 	    {
>  		public string Adi {get; set;}
>  		public string Soyadi {get; set;}
>  		public string Meslek {get; set;}
>      	public void Deconstruct (out string adi, out string soyadi)//Geriye Tuple gibi bir değer dönüyor
>      	{
>          	adi = Adi;
>          	soyadi = Soyadi;
>      	}
> 	    }
>  }
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
>  class Program
>  {
>      static void Main(string[]args)
>      {
>          Ogrenci ogrenci = new Ogrenci
>          {
>              Adi = "Mustafa",
>              Soyadi ="Kurt",
>              Meslek = "Öğrenci"
>          };
> 
>          var isim = ogrenci switch
>          {
>                  ("Ahmet", "Yıldırım") => "Ahmet Yıldırım",
>                  var x when x.Adi == "Hilmi" && x.Soyadi == "Celayir" => "Hilmi Celayir",
>                  ("Semih", "Fidan") when 3 == 5 => "Semih Fidan",
>                  var x when x.Adi == "Mustafa" && x.Soyadi == "Kurt" => "Mustafa Kurt",
>                  (_,_) => "Hiçbiri",
>                  _ => "Hiçbiri"
>          };
>          Console.WriteLine(isim);
>      }
>      class Ogrenci
> 	    {
>  		public string Adi {get; set;}
>  		public string Soyadi {get; set;}
>  		public string Meslek {get; set;}
>      	public void Deconstruct (out string adi, out string soyadi)//Geriye Tuple gibi bir değer dönüyor
>      	{
>          	adi = Adi;
>          	soyadi = Soyadi;
>      	}
> 	    }
>  }
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
>  //Kod bloğu
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
>  Console.WriteLine("Allah tek yastıkta kocatsın.");
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
>  Console.WriteLine("Merhaba");
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
>  Console.WriteLine("Hayırlı olsun..");
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
> >  Şart true ise buradaki kodlar devreye girer
> > }
> > else
> > {
> >  false ise burası tetiklenecektir.
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
>  Console.WriteLine("i değeri 10");
> }
> else
> {
>  Console.WriteLine("i değeri 10 değil");
> }
> //Eşitlik durumuna göre tersi (manevratik ! operatörü ile kullanım)
> if (i != 10)
> {
>  Console.WriteLine("i değeri 10 değil");
> }
> else
> {
>  Console.WriteLine("i değeri 10");
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
>  Console.WriteLine("i değeri 10");
>  Console.WriteLine("Merhaba");//Tekrar
> }
> else
> {
>  Console.WriteLine("i değeri 10 değil");
>  Console.WriteLine("Merhaba");//Tekrar
> }
> ```
>
> *Her iki durumda da ortak çalıştırılacak olan komutları if else bloğunun dışına yazmamız olayı çözecektir.*
>
> ```csharp
> int i = 10;
> if (i == 10)
> {
>  Console.WriteLine("i değeri 10");
> }
> else
> {
>  Console.WriteLine("i değeri 10 değil")
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
> >  Console.WriteLine(sayi * 5);
> > }
> > else if (sayi > 10 && sayi <= 20)
> > {
> >  Console.WriteLine(sayi * 10);
> > }
> > else if (sayi > 20 && sayi <= 30)
> > {
> >  Console.WriteLine(sayi * 20);
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
> >  Console.WriteLine("100'den küçük");
> > }
> > else if (i > 100)
> > {
> >  Console.WriteLine("100'den büyük");
> > }
> > else
> > {
> >  Console.WriteLine("100'e eşit");
> > }
> > ```
>
> 



### Scopesuz If  Yapısı

> If yapılanmalarının (if-else if-else vs..) hepsi için geçerlidir.
>
> ```csharp
> if (true)
>  Console.WriteLine("Merhaba Dünya"); //If yapılanması tek satırlık bir işlem gerçekleştiriyorsa eğer, bunu scope içerisine yazmak mecburiyetinde değiliz. // Tek satırdan kastımız konseptlik 
> if (true)
> {
>  Console.WriteLine("Merhaba");//Eğer ki birden fazla konspet/işlem/operasyon barındıracaksa bunları kesinlikle scope içerisine almamız gerekir.
>  Console.WriteLine("Dünya");//Aksi taktirde scopesuz çalışırsa ilk işlemi if bloğu içerisine alacak, diğerini almayacaktır.
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
>  //int toplamSonTutar = birinciUrunFiyati + (ikinciUrunFiyati * 3 / 4); -> Sonradan kullanmayacağımız için gereksiz.
>  //Console.WriteLine(toplamSonTutar);
>  Console.WriteLine("Ödenecek Tutar : " + toplamFiyat - (ikinciUrunFiyati * 1 / 4));
> }
> else
> {
>  Console.WriteLine("Ödenecek Tutar : " toplamFiyat);
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
> >  Console.WriteLine("Giriş Başarılı.");
> > else
> >  Console.WriteLine("Girdiğiniz kullanıcı adı veya şifre hatalıdır.");
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
> >  Console.WriteLine("Girdiğiniz kullanıcı adı veya şifre hatalıdır.");
> > else
> >  Console.WriteLine("Giriş Başarılı.");
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
> >      ("Mustafa","12345") => "Giriş Başarılı.",
> >      _ => "Girdiğiniz kullanıcı adı veya şifre hatalıdır."
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
> >  Console.WriteLine(sayi1 + sayi2);
> > }
> > else if (islem == "-")
> > {
> >  Console.WriteLine(sayi1 - sayi2);
> > }
> > else if (islem == "*")
> > {
> >  Console.WriteLine(sayi1 * sayi2);
> > }
> > else if (islem == "/")
> > {
> >  Console.WriteLine(sayi1 / sayi2);
> > }
> > else
> > {
> >  Console.WriteLine("İşlem bulunamadı!");
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
> >  case '+':
> >      Console.WriteLine(sayi1 + sayi2);
> >      break;
> >  case '-':
> >      Console.WriteLine(sayi1 - sayi2);
> >      break;
> >  case '*':
> >      Console.WriteLine(sayi1 * sayi2);
> >      break;
> >  case '/':
> >      Console.WriteLine(sayi1 / sayi2);
> >      break;
> >  default:
> >      Console.WriteLine("İşlem bulunamadı!");
> >      break;
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
> >      '+' => sayi1 + sayi2,
> >      '-' => sayi1 - sayi2,
> >      '*' => sayi1 * sayi2,
> >      '/' => sayi1 / sayi2,
> >      _ => 0
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
> >  Console.WriteLine("sayı yanlış");
> > }
> > ```
>
> > Kritik 2
> >
> > ```csharp
> > int sayi = int.Parse(Console.ReadLine());
> > if (sayi != 10)
> > {
> >  Console.WriteLine("sayı yanlış");
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
> >  Console.WriteLine("Negatif");
> > else
> >  Console.WriteLine("Pozitif");
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
> >  sonuc = "Negatif";
> > else
> >  sonuc = "Pozitif";
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
> >  string xx = x as string;
> >  Console.WriteLine($"x değişkeni string tipindedir.");
> > }
> > else if (x is int)
> > {
> >  int xx = (int)x;
> >  Console.WriteLine($"x değişkeni int tipindedir.");
> > }
> > //Type Pattern haliyle
> > if (x is string xx)
> >  Console.WriteLine($"x değişkeni string tipindedir.");
> > else if (x is int xx)
> >  Console.WriteLine($"x değişkeni int tipindedir.");
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
> >  string _x = (string)x;//Dolayısıyla bunu cast ediyoruz.
> > }
> > //C# 7.0'dan sonra
> > if (x is string a)
> > {
> >  a = "Metin";
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
> >  Console.WriteLine($"Mustafa");
> > else if (x is null)
> >  Console.WriteLine($"null");
> > //Veya
> > object y = 125;
> > if(x is 128)
> >  Console.WriteLine($"y değişkeninin değeri 128");
> > else if (x is 125)
> >  Console.WriteLine($"y değişkeninin değeri 125");
> > else if (x is 120)
> >  Console.WriteLine($"y değişkeninin değeri 120");
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
> >  Console.WriteLine(a);
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
> >  switch (instance)//instance, int, string, char gibi bir yapılanma değil, farklı bir değer türü
> >  {
> >      case SqlConnection connection:
> >          connection.ConnectionString = "Server=.;Database...";
> >          break;
> >      case SqlCommand command when (command.Connection.Conntected)://when şartı da kullanılıyor
> >          command.CommandText = "Select * from ...";
> >          break;
> >      case StreamWriter stream:
> >          stream.Write("....");
> >          break;
> >      case null://statik değer kontrolü
> >          break;
> >  }
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
>   >      Technologic _ => "Teknolojik",
>   >      Computer _ => "Bilgisayar",
>   >      Goggles _ => "Gözlük"
>   > };
>   > ```
>   >
>   > ```csharp
>   > string GetProduct(IProduct p) => p switch
>   > {
>   >      Technologic => "Teknolojik",
>   >      Computer => "Bilgisayar",
>   >      Goggles => "Gözlük"
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
>      Technologic or Computer => "Teknolojik",
>      Goggles => "Gözlük"
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
>      Technologic => "Teknolojik",
>      Computer => "Bilgisayar",
>      not Goggles => "Gözlük"
> };
> ```
>
> ```csharp
> object obj = new Goggles();
> if (obj is not Technologic)
> {
>  //...
> }
> ```
>



------

# Hata Kontrol Mekanizmaları



## Hata Kontrol Mekanizmaları Nedir? Ne Amaçla Kullanılır?

> Yazılım geliştirme sürecinde en çok karşılaştığımız ve önemli bir unsur olan hata, yazılımcıların işlerini etkileyen ve çözüm gerektiren bir durumdur. Her ne kadar özenli ve dikkatli bir şekilde kodlarımızı yazsak da, beklenmedik hatalar, gözden kaçan ayrıntılar veya yanlış hesaplamalar nedeniyle birçok noktada hatalarla karşılaşmamız kaçınılmazdır.
>
> Hata ile karşılaştığımızda, paniklemek yerine nasıl yöneteceğimizi öğrenmeliyiz. Başlangıçta hataları yorumlama ve değerlendirme konusunda belki bilgisiz olabiliriz, ancak öğrendikçe, fark ettikçe ve farklı hata türlerini gözlemledikçe, bu hataları daha iyi anlayabilir ve daha etkili bir şekilde çözebiliriz.
>
> Yazılımcılar olarak, yapıları öğrendikten sonra amaca hizmet edecek algoritmayı tasarlayarak ve problemleri çözerek projeleri inşa ederiz. Ancak, algoritmayı oluşturduğumuzda ortaya çıkan hataları temizlemek ve çözmek de işimizin bir parçasıdır. Mimarileri öğrenmek ve teknik detayları öğrenmek önemlidir, ancak hata çözme yeteneği ve hataları yönetme becerisi de yazılımcılar için aynı derecede önemlidir.
>
> Bu başlık altındaki konularda, yazılım sürecindeki hataların manipülasyonunu, yönetimini ve bir hataya nasıl yaklaşılması gerektiğini ele alacağız. Yazılımcılar olarak, hataları etkin bir şekilde çözebilmek için stratejiler ve yöntemler üzerinde duracağız. Bu konu, yazılımcılar için önemli bir konudur, çünkü hatayı anlamak ve yönetmek, projelerin başarısını etkileyebilir ve geliştiricilerin yeteneklerini geliştirmelerine yardımcı olabilir.
>
> Hata kontrol mekanizmaları, yazılım sürecindeki hataların önemini vurgulayarak, yazılımcıların hataları nasıl manipüle edeceklerini, nasıl yöneteceklerini ve bir hataya nasıl yaklaşacaklarını ele almayı amaçlamaktadır.
>
> Hata kontrol mekanizmalarında değerlendireceğimiz başlıklar;
>
> 1. Derleyici syntax(sözdizimi) hataları
> 2. Runtime (çalışma zamanı) hataları
> 3. Mantıksal hatalar



## Derleme - Syntax (Sözdizimi) Hatası

> * Programlama dili kurallarına aykırı olan hatalardır.
> * Özellikle gelişmiş editörler(VS) sayesinde söz dizimi hataları derlemeye gerek bile kalmaksızın fark edilebilmektedirler.
> * Hatanın bulunduğu satır derleyici tarafından rapor edilir.
> * O yüzden fark edilmesi ve çözülmesi en kolay hata türüdür.
>
> Örneğin class scope'lu olmalıdır.
>
> ```csharp
> class Program
>     static void Main(string[]args)
> 	{
> 
> 	}
> ```
>
> Devam edersek, static keywordu static diye yazılmalıdır, buradaki keywordu stat_ic diye yazarsak, yine syntax error alacağız.
>
> ```csharp
> class Program
> {
>     stat_ic void Main(string[]args)
>     {
> 
>     }
> }
> ```
>
> Yine başka bir örnekle,
>
> ```csharp
> class Program
> {
>     static void Main(string[]args)
>     {
>         int isim.soyisim;
>     }
> }
> ```
>
> Bu tür noktalarda, fark edilmesi ve çözülmesi en kolay hatalardır.
>
> 



## Çalışma Zamanı (Runtime) Hatası

> Herhangi bir syntax problemi yok, kodun semantiği kusursuz ancak çalışma zamanında patlamaya sebep veren bir hata varsa bu hatalara *Çalışma Zamanı (Runtime) Hatası* diyeceğiz.
>
> <img src ="https://www.mobil13.com/wp-content/uploads/2019/10/Runtime-Error.png" align=left width=400>
>
> * Yazılım ayaktayken ortaya çıkan bir takım aykırı durumlardan işletim sistemi tarafından kesilmesiyle/sonlandırılmasıyla sonuçlanır.
>
> * Çalışma zamanı hataları programın işleyişinin ortasında direkt kullanıcıyla temas edebilecek hatalardır.
>
>   Ve hiçbir yazılımcı son kullanıcının hatayla karşılaşmasını istemez..
>
> * Genellikle kültürden kültüre boyutu değişsede bir hatayla karşılaşan son kullanıcı derinden kulak kaşındırabilir.
>
> * Böyle bir durumda çalışma zamanında alınabilecek "olası" hataları yönetmemiz ve bir şekilde manipüle etmemiz gerekmektedir.
>
> <img src="https://imgur.com/9KpG0Hr.png" align=left width=400>
>
> * Olması gereken ise çalışma zamanı hatalarının önceden tespit edilip programcı tarafından daha anlaşılabilir bir şekilde düzenlenmesidir.
> * Tabi bunun için çalışma zamanı hatalarının sağlam bir öngörüyle tespit çalışması yapılması gerekmektedir.
> * Çalışma zamanı hatalarını önceden kestirmek oldukça zor olabilmektedir.
> * Bu hataları öngörebilmek genellikle testerların işidir.
> * Uygulamada mümkün mertebe test edilerek çalışma zamanı hataları tespit edilmeli ve programcı tarafından tanımlanmalıdır.
> * Tüm bunlara rağmen gözden kaçan durumlar olması oldukça normaldir. Dolayısıyla bir programın gelişimi sahadaki belli bir sürece bağlıdır.
> * Bu süreçten toplanan loglar ve son kullanıcı dönütleri değerlendirilerek çalışma zamanı hataları tespit edilip arındırılabilir.
>
> * Tespit edilen çalışma zamanlarının manipülasyonunun oldukça önemli olduğunu söyledik.
>
> 
>
>   **Peki bunu nasıl yapacağız?**
>
>   Yazılımdaki hata kontrol mekanizmalarını devreye sokarak...
>
> Hata kontrol mekanizmaları, çalışma zamanı hatalarını kullanıcıya hissettirmeden yakalayabilmek ve ilgili hatayı manipüle edebilmek için vardır.
>
> İlerleyen süreçte göreceğimiz **try catch bloğu** ile bu hataları manipüle edebileceğiz. Ancak *try catch bloğu* sözdizimi veya mantıksal hataların çözümü için kullanılabilir bir kontrol mekanizması değildir. Aklınızda bulunsun.
>
> 



### Çalışma Zamanı (Runtime) Hata Durumlarına Örnekler

> * Olmayan bir dosyayı açmaya yahut üzerine yazmaya, okumaya vs. çalışmak
> * Olmayan değer üzerinde işlem yapmaya çalışmak
> * Uygun olmayan formatlarda çalışmak
> * Veritabanı bağlantısının kopması
>
> > Örnek
> >
> > Varsayalım ki kullanıcıdan aldığımız 2 değer üzerinde herhangi bir aritmetik işlem yapalım.
> >
> > ```csharp
> > Console.WriteLine("Lütfen birinci sayıyı giriniz : ");
> > int sayi1 = int.Parse(Console.ReadLine());
> > Console.WriteLine("Lütfen birinci sayıyı giriniz : ");
> > int sayi2 = int.Parse(Console.ReadLine());
> > 
> > Console.WriteLine("Toplam : " + (sayi1 + sayi2));
> > ```
> >
> > Kullanıcıdan gelecek olan değerler, dikkat ederseniz integer'a parse edilebilir değerler olması gerekir.
> >
> > ​	Eğer ki kullanıcı integer'a parse edilemeyecek bir değer verirse, program patlayacaktır.
> >
> > <img src="https://imgur.com/JleMijj.png" align=left>
> >
> > Bu hata bizim mimarimiz tarafından tanımlanan bir hata olduğu için bunu veriyor. Eğer ki mimaride tanımlanmamış bir hata olsaydı, işletim sistemi seviyesinden bir hata fırlatacaktı. 
> >
> > Dolayısıyla biz yazılımcılar çalışma zamanındaki bu tarz parametrik değerler üzerinde olası hataları tespit edip, bunlara göre önlem almamız gerekiyor.
>
> 



### try-catch Yapılanması

> try-catch Yapılanması, çalışma zamanında alınan hataları manipüle etmemizi karşılamamızı, kontrol etmemizi sağlayan bir programatik yapıdır. 
>
> Programlama dilinin dahilindedir.
>
> * try-catch yapılanması uygulama sürecinde yaşanan olası hatayı kullanıcıya hissettirmeksizin, farklı bir durum ya da olağan bir mesaj gibi göstermemizi sağlayan, bunun yanında patlamaya/hataya dair bizlere bilgi sunan ve böylece bu bilgiler eşliğinde kayıtlar/log oluşturmamızı sağlayan bir programatik yapılanmadır.
>
>   Amaç : 
>
>   1. Kullanıcıya alınan hatayı hissettirmemek
>
>   2. Alınan hatanın nedenine dair kullanıcıyı bilgilendirmek
>
>   3. İşletim sistemleri aykırı durum yaşandığında uygulamayı sonlandırmak ister ve sonlandırırlar.
>
>      try catch yapılanması ile alınan hataya dair bir manipülasyon gerçekleşitiriliyor ve uygulamanın kapanmadan devam edebilmesi sağlanabiliyor...
>
> > Prototip
> >
> > ```csharp
> > try
> > {
> >  //Olası çalışma zamanı hatalarını verebilecek kodlarımızı buraya yazıyoruz.
> > }
> > catch
> > {
> >  //try içerisinde olası hata söz konusuysa, kodun akışı orada kesilecek ve akış catch bloğundan devam edecektir.
> > }
> > ```
>
> 



#### try-catch Yapılanması Pratik Yapalım

> > Örnek
> >
> > ```csharp
> > try
> > {
> >  //Olası çalışma zamanı hatalarını verebilecek kodlarımızı buraya yazıyoruz.
> >  Console.WriteLine("Lütfen birinci sayıyı giriniz : ");
> >  int sayi1 = int.Parse(Console.ReadLine());
> >  Console.WriteLine("Lütfen birinci sayıyı giriniz : ");
> >  int sayi2 = int.Parse(Console.ReadLine());
> > 
> >  Console.WriteLine("Toplam : " + (sayi1 + sayi2));
> > }
> > catch
> > {
> >  //try içerisinde bir hata söz konusu olduğunda catch bloğu tetiklenecektir.
> >  //hataya dair; long, kullanıcı bilgilendirme, kontrollü kapanış vs..
> >  Console.WriteLine("Lütfen doğru bir ifade giriniz.");
> > }
> > ```
> >
> > Öneri : *Breakpoint ile debug modda gözlemleyin.*
>
> 



#### Kritik

> try-catch Yapılanmasında, olası hata verebilecek kodlar try bloğuna, hata neticesinde çalışacak kodları catch bloğuna yazıyorduk.
>
> * try-catch yapılanması, olası hatanın ihtimal olduğu kodları durmadan kontrol eden maliyetli bir yapıdır.
>
>   Dolayısıyla, try içerisinde kontrol edilen kodlar lüzumsuz yere, tüm kodlar olmamalıdır.
>
> * Sadece olası hata verebilecek kodları barındıran bir yaklaşım sergilemeniz kontrol maliyeti açısından daha verimli ve performanslı olacaktır.
>
> > Örnek
> >
> > ```csharp
> > Console.WriteLine("Lütfen birinci sayıyı giriniz.");
> > int sayi1 = 0, sayi2 = 0;
> > try
> > {
> >  sayi1 = int.Parse(Console.ReadLine());
> >  Console.WriteLine("Lütfen ikinci sayıyı giriniz.");//Normalde dışarıya yazmamız gerekir ancak akış gereği burada tutacağız.
> >  sayi2 = int Parse(Console.ReadLine());
> > }
> > catch
> > {
> >  Console.WriteLine("Lütfen doğru bir ifade giriniz.");
> > }
> > Console.WriteLine("Toplam : " + (sayi1 + sayi2));
> > ```
>
> 



#### try-catch : Hata Parametreleri

> Çalışma zamanında alınan hataya dair bizlere bilgi veren, taşıyan parametrelerdir.
>
> Birkaç örnek ile başlayalım.
>
> > Örnek 1
> >
> > Bir sayının 0'a bölümü, matematiksel olarak tanımsızdır. Yazılımsal olarak ise bu durum hata fırlatacaktır.
> >
> > ```csharp
> > int s1 = 0, s2 = 10;
> > int sonuc = s2 / s1; // Hata verecektir. | Exception Unhandled | System.DivideByZeroException : 'Attempted to divide by zero.'
> > ```
> >
> > * Runtime da hata alındığında bunu editör üzerinde görebilmekteyiz. Burada görülen DivideByZeroException, bizim aldığımız/karşılaştığımız hatanın türünü ifade etmektedir.
> >
> > * Alınan hatanın yapısına göre hata türü fırlatılacaktır.
>
> > Örnek 2
> >
> > Herhangi bir null olan bir değişken üzerinde işlem yapmaya çalışıyorsak, bir tutarsızlığa sebep olacaktır.
> >
> > ```csharp
> > object x = null;
> > x.ToString(); // Exception Thrown | System.NullReferenceException: 'Object reference not set to an instance of an object.'
> > ```
> >
> > * Bu durumda da NullReferenceException türünde bir hata ile karşılaştık.
>
> > Örnek 3
> >
> > Elimizdeki herhangi bir metinsel ifadeyi, sayısal ifadeye convert ya da parse ederken,
> >
> > ```csharp
> > int deger = int.Parse("metin");// Exception Unhandled | System.FormatException: 'Input string was not in a correct format.'
> > ```
> >
> > * Uygun olmayan format hatası ile karşılaştık. Hata türü olarak FormatException.
>
> > try-catch yapılanmasında, bizlere hatayı yakalayan try bloğuydu. Haliyle hata bilgisini bize getirecek olan catch bloğudur.
> >
> > ```csharp
> > try
> > {
> > 
> > }
> > catch (Exception ex)// Exception Parametresi
> > {
> > 
> > }
> > ```
> >
> > * Exception : Bizlere fırlatılan hata ile ilgili tüm bilgileri getirecek olan bir üst türdür. Yani bütün hataları karşılayabilen bir türdür.
> > * Bu parametre üzerinden bizler alınan hataya dair bilgiler edinebilmekte ve gerekli loglama vs. gibi operasyonları gerçekleştirebilmekteyiz.
> > * Bu parametre catch bloğuna yazılmak/tanımlanmak zorunda değildir.
>
> > Örnek 4
> >
> > ```csharp
> > try
> > {
> >  int s1 = 0, s2 = 10;
> >  int sonuc = s2/s1;
> > }
> > catch (Exception ex)
> > {
> >  Console.WriteLine("Mesaj : " + ex.Message);
> > }
> > ```
>
> 



#### try-catch : Hata Türleri

>Çalışma zamanında alınabilecek hata türleri aşağıda tabloda verilmiştir.
>
>* Bunlar sistemde/mimari de tanımlanmış istisnai sınıflardır yani exception sınıflarıdır.
>
>* Burada amacımız bunların ne olduğunu bilmek değil, böyle hata türlerinin olduğunu bilmek.
>
>* Dolayısıyla bir hata ile karşılaştığımızda hangi türe ait bir hata olduğunu bilmemiz şuan için yeterli olacaktır.
>
>| Exception                                                    | Condition                                                    |
>| ------------------------------------------------------------ | ------------------------------------------------------------ |
>| [ArgumentException](https://learn.microsoft.com/tr-tr/dotnet/api/system.argumentexception?view=net-8.0) | A non-null argument that is passed to a method is invalid.   |
>| [ArgumentNullException](https://learn.microsoft.com/tr-tr/dotnet/api/system.argumentnullexception?view=net-8.0) | An argument that is passed to a method is `null`.            |
>| [ArgumentOutOfRangeException](https://learn.microsoft.com/tr-tr/dotnet/api/system.argumentoutofrangeexception?view=net-8.0) | An argument is outside the range of valid values.            |
>| [DirectoryNotFoundException](https://learn.microsoft.com/tr-tr/dotnet/api/system.io.directorynotfoundexception?view=net-8.0) | Part of a directory path is not valid.                       |
>| [DivideByZeroException](https://learn.microsoft.com/tr-tr/dotnet/api/system.dividebyzeroexception?view=net-8.0) | The denominator in an integer or [Decimal](https://learn.microsoft.com/tr-tr/dotnet/api/system.decimal?view=net-8.0) division operation is zero. |
>| [DriveNotFoundException](https://learn.microsoft.com/tr-tr/dotnet/api/system.io.drivenotfoundexception?view=net-8.0) | A drive is unavailable or does not exist.                    |
>| [FileNotFoundException](https://learn.microsoft.com/tr-tr/dotnet/api/system.io.filenotfoundexception?view=net-8.0) | A file does not exist.                                       |
>| [FormatException](https://learn.microsoft.com/tr-tr/dotnet/api/system.formatexception?view=net-8.0) | A value is not in an appropriate format to be converted from a string by a conversion method such as `Parse`. |
>| [IndexOutOfRangeException](https://learn.microsoft.com/tr-tr/dotnet/api/system.indexoutofrangeexception?view=net-8.0) | An index is outside the bounds of an array or collection.    |
>| [InvalidOperationException](https://learn.microsoft.com/tr-tr/dotnet/api/system.invalidoperationexception?view=net-8.0) | A method call is invalid in an object's current state.       |
>| [KeyNotFoundException](https://learn.microsoft.com/tr-tr/dotnet/api/system.collections.generic.keynotfoundexception?view=net-8.0) | The specified key for accessing a member in a collection cannot be found. |
>| [NotImplementedException](https://learn.microsoft.com/tr-tr/dotnet/api/system.notimplementedexception?view=net-8.0) | A method or operation is not implemented.                    |
>| [NotSupportedException](https://learn.microsoft.com/tr-tr/dotnet/api/system.notsupportedexception?view=net-8.0) | A method or operation is not supported.                      |
>| [ObjectDisposedException](https://learn.microsoft.com/tr-tr/dotnet/api/system.objectdisposedexception?view=net-8.0) | An operation is performed on an object that has been disposed. |
>| [OverflowException](https://learn.microsoft.com/tr-tr/dotnet/api/system.overflowexception?view=net-8.0) | An arithmetic, casting, or conversion operation results in an overflow. |
>| [PathTooLongException](https://learn.microsoft.com/tr-tr/dotnet/api/system.io.pathtoolongexception?view=net-8.0) | A path or file name exceeds the maximum system-defined length. |
>| [PlatformNotSupportedException](https://learn.microsoft.com/tr-tr/dotnet/api/system.platformnotsupportedexception?view=net-8.0) | The operation is not supported on the current platform.      |
>| [RankException](https://learn.microsoft.com/tr-tr/dotnet/api/system.rankexception?view=net-8.0) | An array with the wrong number of dimensions is passed to a method. |
>| [TimeoutException](https://learn.microsoft.com/tr-tr/dotnet/api/system.timeoutexception?view=net-8.0) | The time interval allotted to an operation has expired.      |
>| [UriFormatException](https://learn.microsoft.com/tr-tr/dotnet/api/system.uriformatexception?view=net-8.0) | An invalid Uniform Resource Identifier (URI) is used.        |
>
>> Hatayı tanımlarken hatırlarsanız Exception ex olarak yani 'Exception' ile tanımlamıştık.
>
>> <img src="https://www.tutorialsteacher.com/Content/images/csharp/exception-classes.png" align=left>
>
>> * Exception : Tüm hata türlerinin atasıdır.
>
>
>
>



#### try-catch : Exception Dışında Farklı Bir Tür ile Hata  Yakalama

>
>
>```csharp
>try
>{
>int s1 = 0, s2 = 10;
>int sonuc = s2/s1; //0'a bölme hatası
>}
>catch (DivideByZeroException ex) //(Exception ex) yerine yakalayacağımız hataya göre farklı bir tür verebiliriz.
>{
>Console.WriteLine("Mesaj : " + ex.Message);
>}
>```
>
>* Yukarıdaki örnekte DivideByZeroException hatası almazsak ve başka bir hata alırsak, bu durumda catch bloğu bu hatayı yakalamayacaktır.
>
> catch bloğu, bir parametre tanımlanmazsa eğer, tüm hataları karşılayabilen bir bloktur.
>
> Ayrıca parametre tanımlanır ve bu parametrenin türü exception'sa yine tüm hataları karşılayabilmektedir.
>
> *Eğer ki, parametre exception değil, özelleştirilmiş bir hataya indirgenmişse böyle bir durumda sadece ilgili türe ait hataları yakalayabilecek, karşılaştırabilecektir.*
>
>
>
> > Örnek
> >
> > ```csharp
> > try
> > {
> >  int islem = int.Parse("metin");//format hatası
> > }
> > catch (DivideByZeroException ex) //0'a bölme hatası yakalama
> > {
> >  Console.WriteLine("Mesaj : " + ex.Message);
> > }
> > ```
> >
> > * Bu senaryoda try-catch bloğu kullanıldığı halde fiziksel olarak patlama meydana gelmiş ve uygulama sona ermiştir.
> >
> >   Çünkü, catch bloğu eğer ki bir türe özgü ise(genel olmayan) böyle bir durumda sadece o türden hataları yakalayabilen bir yapı haline gelmektedir.
> >
> >   Dolayısıyla try-catch bloğu hangi parametre tanımlandıysa o parametrenin yakalayabileceği türdeki hataları manipüle etmekte, eğer ki parametrenin dışında farklı bir türde hata fırlatılırsa try-catch bloğu ilgili hatayı manipüle etmeyecek ve fiziksel olarak uygulamayı patlatıp sonlandıracaktır.
> >
> > * Çözüm olarak bu durumda birden fazla catch bloğu ile diğer türdeki parametreleri kontrol etmek olacaktır. Bu da bir sonraki konumuzda yer alacaktır.
>
>* Catch bloğu, tanımlanan hata yakalama türüne uygun olacak şekilde tetiklenmektedir.
>
>



#### Birden Çok Catch Durumu

> Bir try-catch yapılanmasında, çalışma zamanında birden fazla farklı türde hata verebileceği için, birden çok catch tanımlamamız gerekebilir.
>
> > Örnek
> >
> > ```csharp
> > int s1 = 0, s2 = 10;
> > try
> > {
> >  int sonuc = s2 / s1; //DivideByZeroException
> >  int islem = int.Parse("metin");//Format exception
> > }
> > catch (Exception ex) //Her iki hatadan birinin bile olması durumunda catch bloğu tetiklenecektir.
> > {
> > 
> > }
> > ```
> >
> > * Exception olarak genel bir tanım yaptığımızda, catch bloğu her iki ihtimalde de aynı davranışı sergileyecektir.
> >
> >   Dolayısıyla farklı türlerdeki hata durumlarında bu şekilde bir fark yaratamayız.
> >
> > ```csharp
> > int s1 = 0, s2 = 10;
> > try
> > {
> >     int sonuc = s2 / s1; //DivideByZeroException
> >     int islem = int.Parse("metin"); //Format exception
> > }
> > catch (DivideByZeroException ex0)//DivideByZeroException hatası aldığında bu hatayı karşılayacak olan catch tanımlanmış oldu.
> > {
> >     Console.WriteLine("Sıfıra bölme işlemi gerçekleştirilemez.");
> > }
> > catch (FormatException ex1)//FormatException hatası aldığında bu hatayı karşılayacak olan catch tanımlanmış oldu.
> > {
> >     Console.WriteLine("Lütfen doğru bir ifade giriniz.");
> > }
> > catch (Exception ex2)
> > {
> > 
> > }
> > //Bu catchlerin dışında farklı bir türde hata alınırsa eğer, o hatayı da karşılayan farklı bir catch bloğu tanımlanmalıdır.
> > ```
> >
> > * catch bloklarının en sonuna Exception türünde parametre(catch) tanımlanırsa, alınan hata üstteki türlerden herhangi biri değilse kesinlikle bu Exception tarafından karşılanabilir olacağından dolayı en kötü buraya girecektir.
> >
> > * Anlaşılıyor ki; try-catch yapılanması olası runtime hatası aldığında catch sıralamasına göre kontrol etmektedir. Bu sıralama önemlidir.
> >
> >   *Eğer ki birden fazla catch bloğunun tanımlanmasında Exception kullanılacaksa bu Exception'ın en sona tanımlanması gerekmektedir!*
>
> 



#### try-catch : finally Bloğu

> try-catch yapılanmasında, finally bloğu : Hata alınsa da alınmasa da, her iki durumda da çalıştırılması gereken kodları yazdığımız bloktur.
>
> ```csharp
> try
> {
>  //hata verebilecek kodlar buraya
>  Console.WriteLine("try");
> }
> catch
> {
>  //hata aldıktan sonra yapılacak işlemler buraya
>  Console.WriteLine("catch");
> }
> finally
> {
>  //her iki durumda da çalışmasını istediğimiz kodlar
>  Console.WriteLine("finally");
> }
> ```
>
> 



#### when Yapısı ile Hata Filtreleme (C#6.0)

> try-catch bloklarına when keywordü ile şart uygulayabilmekteyiz.
>
> > Örnek
> >
> > ```csharp
> > string x = "a";
> > try
> > {
> >  int s1 = 0, s2 = 10;
> >  int sonuc = s2 / s1;
> > }
> > catch (DivideByZeroException ex) when(x == "a") //şartlı kullanım 1
> > {
> >  Console.WriteLine("Mesaj : " + ex.Message);
> > }
> > catch (DivideByZeroException ex) when(x == "b") //şartlı kullanım 2
> > {
> >  Console.WriteLine("Mesaj : " + ex.Message);
> > }
> > ```
> >
> > * Diyelim ki DivideByZero geldi, her iki şartıda karşılamıyorsa, program yine patlayacaktır.
>
> 



## Mantıksal Hatalar (Logic Error)

> Programın mantığında, akışında, algoritmasında, stratejisinde bir takım şeylerin yanlış hesaplanması, düşünülmesi, tasarlanması neticesinde alınan hatalardır.
>
> * Syntax'ta, kodun derlenmesinde ve hatta çalışma zamanında hata yoktur!
>
>   Kod çalışır, sonuç verir.
>
> * Lakin sonuçlar hatalıdır.
>
>   Beklenen sonuçlar elde edilemez!
>
> * Anlaşılan kodun mantığında ve hesapta bir yanlış var.
>
> Mantıksal hatalar ancak test süreçlerinde veya müşteri kullanımında tespit edilebilir.
>
> Bazen hesaplanması gereken bir değerin eksik hesaplanmasıyla, bazen yanlış katsayının kullanılmasıyla, bazen de mantıksal işlemdeki yapılan bir hatayla ortaya çıkabilir.
>
> Günlük hayattaki karşılığı 'Bug' dur.
>
> Tespiti çok zor olduğu için hata türleri arasında en tehlikeli hatadır.
>
> Mantıksal hatalarda bazen tek çözüm debug'dır.
>
> 



### Mantıksal Hata Örnek 1

> 2 ile 5'i çarpalım ve ekrana yazdıralım.
>
> ```csharp
> Console.WriteLine(2 * 6); //Çıktı: 12 // 5 yerine 6 yazmışız işte bu Mantıksal Hatadır.
> ```



### Mantıksal Hata Örnek 2

> Bir evlilik durumunu tutan değişkeni check edelim, kişi evliyse ona bir promosyon gönderelim, değilse göndermeyelim.
>
> ```csharp
> bool medeniHal = true;
> if (!medeniHal)
> {
>  Console.WriteLine("Hediye gönder...");
> }
> else
> {
>  Console.WriteLine("Hediye gönderme");
> }
> ```
>
> 



### Mantıksal Hata Örnek 3

> Elimizdeki iki sayının aritmetik ortalamasını yapan bir uygulama yapalım.
>
> ```csharp
> int i = 10, i2 = 20;
> Console.WriteLine(i + i2);
> ```
>



------

# Döngüler



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
> >Console.WriteLine("Mustafa Kurt");
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
> > Bu durumuda parametreleri adım adım ele alırsak,
> >
> > Adım 1 : i değişkeni 1, koşul true, i + 1 -> Scope aralığı tetiklenir
> >
> > Adım 2 : i değişkeni 2, koşul true, i + 1 -> Scope aralığı tetiklenir
> >
> > .
> >
> > .
> >
> > Adım 9 : i değişkeni 9, koşul true, i + 1 -> Scope aralığı tetiklenir
> >
> > Adım 10 : i değişkeni 10, koşul false -> Döngüden çıkar.
> >
> > Yani toplamda 9 kere scope aralığındaki `Console.WriteLine("Mustafa Kurt");` kodu tetiklenir.
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
> >  Console.WriteLine("Hilmi");
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
> >  Console.WriteLine("Hilmi");
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
> >  Console.WriteLine(i);
> > }
> > ```
>
> > 2.Çözüm
> >
> > ```csharp
> > for (int i = 50; i < 60; i++)
> > {
> >  Console.WriteLine(i -49);
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
> >  if(i % 2 == 0)
> >  {
> >      toplamSonuc += i;
> >  }
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
> >  faktoriyel *= i;
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
> >  faktoriyel *= i;
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
> >  faktoriyel *=i;
> >  //sonuc += i + (i == 1 ? " = " : " x ");
> >  if(i==1)
> >      sonuc += i + " = ";
> >  else
> >      sonuc += i + " x ";
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
>  i++;
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
>  Console.WriteLine("Mustafa");
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
>  Console.WriteLine("Mustafa");
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
>  Console.WriteLine("asdf");
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
>  Console.WriteLine(i);
>  Console.WriteLine(i2);
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
>  Console.WriteLine("Mustafa");
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
>  Console.WriteLine("Mustafa");
>  i++;
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
>  Console.WriteLine("Merhaba Dünya");
>  i++; //arttırma işlemi ile koşulu daraltarak sonlanmasını sağladık
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
>  //sayi--; // Algoritmada kullanılacak değer, önceden işleme tabii tutulmamalıdır.
>  Console.WriteLine(sayi);
>  sayi--;
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
>  if(i % 2 == 1)
>      toplam += i;
>  i++;
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
>  faktoriyel *= sayi--;//İçeride tanımlı bir şarta bağlı olmadığı durumlarda bu şekilde de kullanılabilir.
>  //sayi--;
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
>  if (DateTime.Now.Second % 5 == 0)
>      Console.WriteLine(DateTime.Now);
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
>  Console.WriteLine("while döngüsü");
> }
> do
> {
>  Console.WriteLine("do while döngüsü");
> } while(false);
> ```
>
> 



## Scopesuz Döngüler

> Bir döngü de yapılacak işlem tek satırlık, tek konseptlik ise scopesuz oluşturabilmekteyiz.
>
> ```csharp
> for (int i=0; i < 10 ; i++)
>  Console.WriteLine("Mustafa Kurt");
> while (true)
>  Console.WriteLine("");
> do
>  Console.WriteLine("dowhile");
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
>  if(true)
>      dongu = !dongu;
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
>  if(true)
>      durum = !durum;
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
>  if(true)
>      durum = !durum;
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



------

# Konseptli Konseptsiz Keywordler



## Keyword Nedir? Operatörden Farkı Nedir?

> Keyword : Programlama dilinin en atomik parçalarıdır.
>
> Derleyici için ön tanımlı olan, nerede hangi amaca hizmet edeceği belli ve kod içerisinde hangi noktalarda çağırılabileceği/kullanılabileceği kurallarla sınırlandırılmış olan anahtar sözcüklerdir.



> Keywordlerin operatörlerle ne farkı vardır?
>
> Operatörler esas olarak belirli bir operasyonu/eylemi üstlenen yapılardır.
>
> Keywordler daha geniş kavramdırlar.
>
> Operatörler esasında bir keyworddur lakin her keyword bir operatör değildir.
>
> 



## Konseptli Keywordler Genel Bakış

> Konspetli keywordler : Yapısal olarak tek başına kullanılmayan, bir bütün olarak konspete bağlı olan keywordlerdir.
>
> Örneğin namespace keywordu
>
> ```csharp
> namespace
> ```
>
> Tek başına kullanıldığında bir anlam ifade etmeyen keywordlerdir.
>
> Ancak namespace'yi bir isim vererek scope açarak kullandığımız taktirde, bir anlam ifade edecektir, derleyici açısından konsepte uygun bir şekilde yorumlanacaktır.
>
> ```csharp
> namespace keywords
> {
> 
> }
> ```
>
> Bu kapsamda ele alabileceğimiz diğer keywordlerden bir kısmı;
>
> * namespace
> * class
> * for
> * while
> * do while
> * switch
> * if
> * try-catch
> * değişken türleri
> * ...
>
> > **Dikkat **: Konseptli keywordlerde dikkat edilmesi gereken, konspete hakim olmamız gerektiğidir.
> >
> > Bir keywordun konseptine hakim olabilmek için de editörün bize sağlamış olduğu kolaylıklardan uzaklaşmamız (tab-tab gibi), Gençay Yıldız hocamızın tavsiyesidir.
>
> 



## Konseptsiz Keywordler Genel Bakış

> Konseptsiz Keywordler : Herhangi bir bütüne, konspete ihtiyaç duymaksızın, tek başına anlam ifade eden keywordlerdir.
>
> Bunlar daha azınlıkta olsa da belirli noktalarda kullanılan keywordlerdir.
>
> Örneğin;
>
> ```csharp
> return;
> break;
> continue;
> goto;
> //...
> ```
>



------

# Yardımcı Manevra Komutları



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
> >  if (i == 22)//Bunu yapabiliriz ama çok da efektif değildir.
> >  {
> >      i = 100;
> >  }
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
> >  //...
> >  while (true)
> >  {
> >      break;
> >  }
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
> >  case 5:
> >      break; 
> >  case 10: //durumu kontrol edecek
> >      break; //kodlar çalıştıktan sonra switch yapısından çıkış yapacaktır
> >  case 15:
> >      break;
> > }
> > ```
>
> > İnceleme 3
> >
> > ```csharp
> > foreach (var item in new[] {""})
> > {
> >  break;
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
> >  if(true)
> >  {
> >      break;
> >  }
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
> >  if (DateTime.Now.Second == 45)
> >      break;
> >  Console.WriteLine(DateTime.Now);
> > }
> > ```
> >
> > Örnek 2
> >
> > ```csharp
> > for (int i = 0; i < 5; i++)
> > {
> >  for (int j = 0; j < 3; j++)
> >  {
> >      if (j==1)
> >          break;
> >      Console.WriteLine("i : "+ i +"j : " + j);
> >  }
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
> >  Console.WriteLine("Lütfen bir sayı giriniz : ");
> >  string girilenDeger = Console.ReadLine();
> >  if(girilenDeger == "t")
> >  {
> >      Console.WriteLine("Toplam Sonuç : " + toplam);
> >  }
> >  else
> >  {
> >      toplam += int.Parse(girilenDeger);//girilen değerin ya sayısal değer ya da t olduğunu varsayarak oluşturuyoruz
> >  }
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
> >  Console.WriteLine("Lütfen bir sayı giriniz.");
> >  int sayi = int.Parse(Console.ReadLine());
> >  if(sayi % 37 == 0)
> >  {
> >      Console.WriteLine("Uygulama sonlanmıştır.");
> >  }
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
> >  if(i % 2 == 0)
> >  	continue;// i'nin çift olmadığı durumlarda bir sonraki duruma geçer.
> >  Console.WriteLine(i);
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
>  Console.WriteLine("Lütfen bir sayı giriniz.");
>  string girilenDeger = Console.ReadLine();
>  if(girilenDeger == "t")
>  {
>      Console.WriteLine(carpim);
>      break;
>  }
>  else
>  {
>      int sayi = int.Parse(girilenDeger);
>      //if (sayi > 0)
>      //	carpim *= sayi;
>      if (sayi < 0)
>          continue;
>      carpim *= sayi;
>  }
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
>  if(i % 7 == 0)
>      continue;
>  Console.WriteLine(i);
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
> >  class Program
> >  {
> >      static void Main(string[] args)
> >      {
> >          while(true)
> >          {
> >              switch (10)
> >              {
> >                  case 10:
> >                      return;//Uygulama metottan çıkacaktır.
> >                      //return'den sonra hangi komut gelirse gelsin, metot sonlanacağı için işlenmeyecektir!
> >                      break;
> >              }
> >          }
> >      }
> >  }
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
>  if(Console.ReadKey().KeyChar == 'c')
>  {
>      Console.WriteLine("Uygulama sona ermiştir.");
>      return;
>  }
>  Console.WriteLine("");
>  Console.WriteLine("Uygulama çalışıyor...");
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
>   >  case n:
>   >      break;
>   >  case m:
>   >      goto case n; //önceden tanımlanmış olan bir case'in kodunu tetikliyordu.
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
> >  case 5:
> >      Console.WriteLine("5");
> >      break;
> >  case 10:
> >      goto case 5;
> >  case 15:
> >      break;
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
>  goto x;
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
>  goto a;
> }
> ```
>
> [Video desteği](https://youtu.be/bYiMyAyCnG8)
>
> 



------

# Ekstra Bilgi



## Döngülerde Boş Scope Kullanmak İstemedğimiz Durumlarda ;(Noktalı Virgül) Operatörü ile Temiz Kod Yazımı

> Sonsuz döngüye nasıl giriyorduk
>
> ```csharp
> while (true)
> {
> 
> }
> for (;;)
> {
> 
> }
> do
> {
> 
> }while(true);
> ```
>
> Eğer ki sonsuz döngüye ihtiyacımız var ve içinde işlem yapmayacaksak, bunu şu varyasyonlarla da yapabilmekteyiz;
>
> ```csharp
> //Bazen(ki ileride asenkron programlamada) içi boş sonsuz döngülere ihtiyacımız olabilir.
> //Bu durumlarda normal döngü gövdelerini kullanabileceğimiz gibi, scopesuz bu şekilde de kullanabilmekteyiz.
> while(true);
> 
> for(;;);
> 
> do;
> while(true);
> ```
>
> 



## if  Yapısında Boş Scope Kullanmak İstemediğimiz Durumlarda ;(Noktalı Virgül) Operatörü ile Temiz Kod Yazımı

> ```csharp
> if (true)
> {
> 
> }
> if (true);
> ```
>
> [Video desteği](https://youtu.be/D2HP2Ta51J0)
>



------

# Diziler



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
>
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
>
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



------

# String Tipi Analizi ve String Fonksiyonları



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



------

# Dizilerde Verisel Performans



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



------

# Regular Expressions- Düzenli İfadeler



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
>
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



------

# Koleksiyon Yapıları



## Koleksiyonlar

### Koleksiyonlar Nelerdir? Diziler Varken Neden Koleksiyon Yapıları İnşa Edilmiştir?

> Dizilerdeki sınırlılıklar:
>
> * Dizilerde tanımlama yaparken eleman sayısının bildirilmesi zorunluluğu bir sınırlılıktır.
> * Diziler tanımlandığında kullansakta kullanmasakta bellekte belirtilen eleman sayısı kadar alan tahsisinde bulunurlar. Bu durum bellek boyutunda ekstradan maliyete sebep olacağı için bir sınırlılıktır.
> * Dizilerde eleman sayısının başta belirlenmesi durumunda, ihtiyaca binaen daha fazla değer atamak istediğimizde bu değerleri atayamayacağımız ve dizinin aralığını genişletemeyeceğimizden dolayı bu durum bir sınırlılık olarak karşımıza çıkmaktadır.
> * Tanımlanmış bir dizide elemanlara değer atarken [ ] indexer operatörüyle değer atanması bir sınırlılıktır.

Dizilerle koleksiyonların amacı aynı, birden fazla veriyi yönetmek. Dizilerde sınırlılıklarımız vardı, "bu sınırlılıkları ortadan kaldırmak için üretilmiştir" diyelim.



> Koleksiyonların dizilerden farklı bazı özellikleri ve avantajları şunlardır :
>
> 1. Boyut Esnekliği: Dizilerin boyutları oluşturulduktan sonra genellikle sabittir. Koleksiyonlar ise dinamik olarak boyutlandırılabilir, eleman eklendiğinde veya çıkarıldığında boyutları otomatik olarak ayarlanabilir.
> 2. Veri Ekleme ve Çıkarma Kolaylığı: Koleksiyonlar, veri eklemek, çıkarmak veya düzenlemek için çeşitli yöntemler ve işlevler sağlar. Bu, programcılara esneklik ve kolaylık sağlar.
> 3. Fonksiyonellik Farklılığı: Koleksiyonlar, özel gereksinimlere yönelik farklı fonksiyonelliklere sahip olabilir. Örneğin, List<T> dizilere benzeyebilirken, Stack<T>, Queue<T>, Dictionary<K, V> gibi farklı koleksiyon türleri farklı amaçlara hizmet edebilir.
> 4. Performans ve İşlem Farklılığı: Bazı durumlarda, koleksiyonlar belirli işlemlerde dizilere kıyasla daha etkin olabilir. Örneğin, bir List<T> kullanarak dinamik boyutlanabilir bir yapı oluşturmak, dizilerle karşılaştırıldığında daha fazla işlem kolaylığı sağlayabilir.



## ArrayList

### ArrayList Koleksiyonu Tanımlama

```csharp
//Diziler tanımlanırken kaç eleman tutacakları bildirilmek zorundadır.
int[] yaslar = new int[10]; //Dizi
ArrayList _yaslar = new ArrayList();//Koleksiyon
```



### ArrayList Koleksiyonu Değer Atama

```csharp
//Dizilerde indexer ile belirtilerek atama yapılırken, koleksiyonların genel çoğunluğunda Add() fonksiyonu üzerinden gerçekleştirilir.
yaslar[5] = 123;
_yaslar.Add(123);
```



### ArrayList Koleksiyonu Değer Okuma

```csharp
int[] yaslar = new int[17];
ArrayList _yaslar = new ArrayList();

for (int i = 0; i < 17; i++)
{
    yaslar[i] = i + 10;
    _yaslar.Add(i + 10);
}
//Diziler
Console.WriteLine(yaslar[5]);
//Koleksiyonlar
Console.WriteLine(_yaslar[5]);
```



### ArrayList Kullanılırken Boxing-Unboxing Durumları

> ArrayList, verilen datayı boxing işlemine tabii tutar.
> ArrayList içerisindeki herhangi bir veriyi talep ettiğimizde o veri object olarak gelecektir. Dolayısıyla kendi türünde işlem yapabilmek için unboxing işlemine tabii tutmamız gerekir.

```csharp
ArrayList _yaslar = new ArrayList();
//...
int toplam = 0;
for (int i = 0; i < _yaslar.Count; i++)
{
    toplam += (int)_yaslar[i]; //Unboxing
}
```



### ArrayList Collection Initializers(Koleyksiyon İlklendirici) İle Değer Ekleme

```csharp
ArrayList arrayList = new ArrayList(){
"Ahmet",
123,
true //Object türde tutulduğu için farklı türdeki değerleri de içerebilir.
};
```





------

# Foreach Iterasyonu



## Iterasyon Nedir?

> İtere etmek, fiilinden gelmektedir.

* Mantıksal açıdan her tahminin altında bir iterasyon mantığı yatar.

  1,3,5... dedikten sonra 7'nin aklınıza gelmesi itere etmektir.

  f(5) = 10

  f(10) = 20

  f(15) = 30

  f(100) = ? dediğimizde bunun cevabını(200) verebilmeniz iterasyondur.

  Bir kelime eğer ki içerisinde tekrar eden bir hece barındırıyorsa bu iterasyonel bir kelime olarak geçer:

  örn. Mermer, baba, berber...

* Bu iterasyon mantığı bilgisayar bilimlerinde de kullanılmaktadır.

  Elimizdeki verileri(dizi,koleksiyon) tek tek elde ederek işlem yapmamızı sağlayan mantıktır.



## Iterasyon ile Döngü Arasındaki Fark Nedir?

```csharp
//Foreach(iterasyon) bir döngü değildir!
int[] sayilar = { 3, 213, 423, 42, 34, 234, 234, 234 };
//Tüm değerleri elde edelim.

for (int i = 0; i < sayilar.Length; i++) //Döngülerde bir sonraki işlem önemli değildir, kombinasyon önemlidir. Sonsuza kadar çalışabilir.
{
    
}

//Veri kaynağı olmadığı sürece foreach ile işlem yapılamaz!
foreach (int sayi in sayilar) //Iterasyon elindeki veri kümesi kadar işlem yapar.
{
    
}
```

> Döngülerde herhangi bir bağımlılık yoktur, foreach ise veri kümesine bağımlıdır.
> Veri kümesi değiştiği taktirde foreach patlar.



## Foreach Iterasyonu Nasıl Kullanılır?

```csharp
//Prototip : foreach ( degisken..in..collection.. ){..işlem..}
ArrayList sayilar = new ArrayList { 123, 123, 325, 2, 534, 5, 345, 345 }; //Veri kümesi olması gerekir (Dizi veya Koleksiyon)
foreach (object item in sayilar) //Sayilar koleksiyonu içerisinde gelecek olan değerler object olduğu için değişken object olarak belirtilir.
{
    Console.WriteLine(item);
}
```

```csharp
ArrayList sayilar = new ArrayList { 123, 123, 325, 2, 534, 5, 345, 345 };
foreach (object item in sayilar)
{
    sayilar.Add(123123); // Kaynak değişecekse veri kümesinde değişiklik olacaksa iterasyon patlar. Bu tür durumlarda döngülerde çalışılmalıdır.
    Console.WriteLine(item);
}
```



------

# Hazır Sınıflar ve Fonksiyonlar



## Math Sınıfı

### Abs Fonksiyonu

> Abs : Mutlak değer ve sonucu parametre içerisinde bildirilen türe pozitif döndürür.

```csharp
int i = Math.Abs(-5); // Çıktı : 5
```



### Ceiling Fonksiyonu

> Ceiling : Ondalıklı değeri yukarıya yuvarlar.

```csharp
int i = Math.Ceiling(3.14); // Çıktı : 4
```



### Floor Fonksiyonu

> Floor : Ondalıklı değeri aşağıya yuvarlar.

```csharp
int i = Math.Floor(3.14); // Çıktı : 3
```



### Round Fonksiyonu

> Round : Ondalıklı değeri en yakın olan tamsayıya yuvarlar.

```csharp
Console.WriteLine(Math.Round(3.4)); // 3
Console.WriteLine(Math.Round(3.5)); // 4 : Birşeyin yarısı tamamına genellenebilir.
Console.WriteLine(Math.Round(3.6)); // 4
```



### Pow Fonksiyonu

> Pow : Değerin üssünü almamızı sağlar.

```csharp
//Console.WriteLine(Math.Pow(x,y)); xᵞ
Console.WriteLine(Math.Pow(7,9));
```



### Sqrt Fonksiyonu

> Sqrt : Karekök fonksiyonu, elimizdeki değerin karekökünü almamızı sağlar.

```csharp
Console.WriteLine(Math.Sqrt(4));
Console.WriteLine(Math.Sqrt(25));
Console.WriteLine(Math.Sqrt(121));
Console.WriteLine(Math.Sqrt(55));
```



### Truncate Fonksiyonu

> Truncate : Elimizdeki değerin yuvarlama yapmadan tam sayı değerini elde etmemizi sağlar.

```csharp
Console.WriteLine(Math.Truncate(3.14));
```



## DateTime Struct'ı

### Now Özelliği

> Now : Çalıştığı işletim sisteminin tetiklendiği andaki tarih zaman dilimini döndüren property'dir.

```csharp
Console.WriteLine(DateTime.Now);
```



### Today Özelliği

> Today : Çalıştığı işletim sisteminin tetiklendiği andaki tarih bilgisini döndüren property'dir.

```csharp
Console.WriteLine(DateTime.Today);
```



### Compare Fonksiyonu

> Compare : İki tarihsel zaman arasında karşılaştırma yapmamızı sağlayan fonksiyondur.
>
> Geriye int türünde değer döndürür. -1 0 1

```csharp
DateTime tarih1 = new DateTime(2021, 01, 01);
DateTime tarih2 = new DateTime(2023, 10, 28);
int result = Datetime.Compare(tarih1,tarih2);
if (result < 0)
{
    Console.WriteLine($"{tarih1} küçüktür {tarih2}");
}
else if (result == 0)
{
    Console.WriteLine($"{tarih1} eşittir {tarih2}")
}
else
    Console.WriteLine($"{tarih1} büyüktür {tarih2}");
```



### Tarihsel Zamana Saat, Gün, Ay,Yıl Ekleyerek Sonucu Hesaplama

> AddDays, AddHours, AddMonths, AddMiliseconds vs..

```csharp
Console.WriteLine(DateTime.Now.AddSeconds(999));
Console.WriteLine(DateTime.Now.AddMonths(999));
Console.WriteLine(DateTime.Now.AddDays(999));
```



## TimeSpan Struct'ı

### TimeSpan Türü ile İki Tarih Farkının Karşılanması

```csharp
DateTime t1 = DateTime.Now;
DateTime t2 = new DateTime(2000, 1, 1);
TimeSpan span = t1 - t2;
Console.WriteLine(span.Days);
Console.WriteLine(span.Minutes);
```



## Random Sınıfı

> Rastgele sayısal değer oluşturmamızı sağlayan bir sınıftır.

### Next Fonksiyonu

```csharp
Console.WriteLine(random.Next()); //0 - ....
Console.WriteLine(random.Next(100)); //0 - 100
Console.WriteLine(random.Next(50,100)); //50 - 100
//Belirtilen maximum değer bu aralığa dahil değildir yani üretilecek olan değer 0 ile 99 arasında olacaktır.
//Negatif değer üretmeyecektir.
```



### NextDouble Fonksiyonu

> 0 ile 1 arasında rastgele değer üretir.

```csharp
Console.WriteLine(random.NextDouble());
```



------

# Metotlar - Functions



## Metot Nedir?

> Yöntem, yordam, function...
>
> Yazılımda gerçekleştirdiğimiz, fiili olarak gerçekleştirdiğimiz tüm operasyonlar bir metottur.
>
> Metot, prosedürel programlamanın temel elemanıdır. Bir iş/fiiliyat/operasyon yapan en küçük program parçacıklarıdır.



### İşlevsel Açıdan Metot Bize Ne Kazandırır?

> Bir kodun içerisinde operasyon gerçekleştiren en küçük parçadır.
>
> Hem operasyon gerçekleştirmemizi sağlar hem de kodun içerisinde tekrar eden kodları tek seferlik tanımlayıp, ihtiyaca binaen çağırılabilen yapılardır.
>
> Haliyle gerçekleşecek operasyonda yönetilebilirlik metot olmadığı durumda zorlaşacaktır.

```csharp
//İşlem A
int[] sayilar = new int[10];
for (int i = 0; i < sayilar.Length; i++)
{
    sayilar[i] = new Random().Next;
}
foreach (var sayi in sayilar)
{
    Console.WriteLine(sayi);
}
//İşlem B
int[] sayilar = new int[10];
for (int i = 0; i < sayilar.Length; i++)
{
    sayilar[i] = new Random().Next;
}
foreach (var sayi in sayilar)
{
    Console.WriteLine(sayi);
}
//İşlem C
int[] sayilar = new int[10];
for (int i = 0; i < sayilar.Length; i++)
{
    sayilar[i] = new Random().Next;
}
foreach (var sayi in sayilar)
{
    Console.WriteLine(sayi);
}
```

> Yazılmış olan bir kodu tekrar çağırmakla, tekrar yazmak arasında fark vardır!

> Metotlar, içerisine yazılan kodun, tekrarlı bir şekilde kullanılmasını sağlarlar.
> Ve bunu yaparken kaynak kodun tekrar etmesini de engellemiş olurlar. Böylece ideal kodlamaya erişmiş oluruz.



## Metot Anatomisi Nasıldır?

* Metotlar sınıf elemanlarıdır, dolayısıyla sınıf içerisinde çalışmamız gerekmektedir.

  ```csharp
  //[erişim belirleyicisi] [geri dönüş değeri] [metodun adı] () --> İmza
  //{ --> Gövde
  //..
  //}
  ```

  - **Erişim belirleyicisi :** İleride göreceğimiz Access Modifier yapılardır. Oluşturulmuş olan bir yapının dışarıdan erişilip erişilmeyeceğini belirtmemizi sağlayan komutlardır. *Public* : Erişilsin | *Private* : Erişilmesin | devamını sonra göreceğiz.

  - **Geriye dönüş değeri :** Metotlar yaptıkları operasyonlar/algoritmalar/işlemler neticesinde geriye değerler döndürebilmektedirler. Bu değer kodun içerisinde yakalanabilir ve programatik olarak işlemlere tabii tutulabilir. Geri dönüş değerini ekran çıktısıyla karıştırmamak gerekmektedir!
  - **Metodun adı :** Metotlarda diğer yapılarda olduğu gibi bir isim almaktadırlar. Temel isimlendirme kuralları geçerli olacaktır.
  - **(parametre) :** Metot dediğimiz bu yapılanmalar dış dünyadan parametreler alabilmekte ve bu parametrelerdeki değerler üzerinde işlemler gerçekleştirebilmektedir. İşte bu parametreleri parantez içerisinden alabilmekteyiz. Bir metot illaki parametre almak zorunda değildir. (int sayi1) (int sayi1, int sayi2) ()
  - **{ } :** Metodun gerçekleştireceği operasyonu/fiiliyatı/eylemi/algoritmayı oluşturduğumuz, kodladığımız faaliyet alanıdır.

> Erişim belirleyici belirtilmediği taktirde C#'ta default olarak private varsayılır.



### İşlevine Göre Metot Türleri Nelerdir?

> Yapacağımız işlemlere göre 4 farklı türde/varyasyonda metot oluşturulabilmektedir.
>
> * Geriye Değer Döndürmeyen, Parametre Almayan
> * Geriye Değer Döndürmeyen, Parametre Alan
> * Geriye Değer Döndüren, Parametre Almayan
> * Geriye Değer Döndüren, Parametre Alan
>
> Tüm varyasyonlarda imza olacaktır. [Erişim Belirleyici] [Geri Dönüş Değeri] [Metodun Adı] (Parametre) {Gövde}



### Metot Tanımlama/Oluşturma Varyasyonları

#### Geriye Değer Döndürmeyen Parametre Almayan Metot

```csharp
//[erişim belirleyicisi] [geri dönüş değeri] [metodun adı] () { }
//Bir metot geriye değer döndürmüyorsa void olarak bildirilmesi zorunludur.
private void Metot1()
{
    Console.WriteLine("Geriye değer döndürmeyen, parametre almayan metot oluşturuldu.");
}
```



#### Geriye Değer Döndürmeyen Parametre Alan Metot

```csharp
//[erişim belirleyicisi] [geri dönüş değeri] [metodun adı] () { }
public void Metot2(int sayi) // Metotlardaki parametreler değişkenlerin kendisidir.
{
    
}
public void Metot3(int a, bool b)
{
    
}
public void Metot4(int a, bool b, char c)
{
    
}
```

> Bir değişken metodun parametresinde tanımlanıyorsa biz buna parametre diyeceğiz. Yok eğer dışında tanımlanıyorsa, buna değişken diyeceğiz.
>
> OOP'ye geçtiğimizde göreceğiz ki, değişken class içerisinde tanımlanıyorsa buna da field diyeceğiz. Yani tanımlandığı yere göre ismi, sorumluluğu davranışı değişmektedir.



#### Geriye Değer Döndüren Parametre Almayan Metot

```csharp
private char Metot5()
{
    return 'a'; //Geriye değer döndüren fonksiyonlarda, bildirilen türde bir değer döndürebilmek için return keyowrdunu kullanmamız gerekmektedir.
}
//Metot5 isminde, dışarıdan erişilemeyen, geriye char türünde değer döndüren ve parametre almayan bir değişken tanımlamış olduk.
```

> Eğer ki bir metot geriye herhangi bir türde değer döndüreceğini ifade ediyorsa, kesinlikle o türde bir değer döndürmelidir. Aksi taktirde hata verir.
>
> > Hatırlatma : return nerede işlenirse orada ilgili fonksiyondan/metottan çıkılır.

```csharp
private int Metot6()
{
    if(DateTime.Now.Second > 10)
        return 5;
    else
        return 0;
}
```

> İçeride bir condition kullanılıyorsa eğer tüm durumlara göre return bildirilmesi gerekmektedir. Aksi taktirde compiler seviyesinde hata verir.



#### Geriye Değer Döndüren Parametre Alan Metot

```csharp
public bool Metot7(int x)
{
    return true || false;
}
```



### Metodun Geriye Değer Döndürmesi Ne Demektir?

```csharp
class Program
{
    static void Main(string[] args)
    {
        int sonuc = Topla(3, 5);
        if (sonuc > 10)
            Console.WriteLine("Sonuç 10'dan büyük");
        bool sonuc2 = PersonelEkle("Rıfkı","Cümbül",25);
        if (sonuc2)
            //..
        else
            //..
    }
    static public bool PersonelEkle(string adi, string soyadi, int yas)
    {
        if (yas >= 20)
        {
            //.. Veritabanına eklendi
            return true;
        }
            
        else
            Console.WriteLine("Personel 20'den küçük olamaz.")
            return false;
    }
    static public int Topla(int sayi1, int sayi2)
    {
        int sonuc = sayi1 + sayi2;
        Console.WriteLine(sonuc);//Metodun geriye değer döndürmesi, yaptığı işlem neticesinde üretilen değeri ekrana/console/veritabanına/herhangi bir log ekranına çıktı vermesi DEĞİLDİR!
        return sonuc;//Metodun geriye döndürdüğü değer, programatik olarak yakalanıp algoritmanın akışında farklı yönlendirmelere sebebiyet verebilen değerdir!
    }
}
```

> Metodun geriye döndürdüğü değer, algoritmanın akışında kullanılabilir değerdir.



## Metotlarda Optional Parameters(İsteğe Bağlı Parametreler)

> Parametreli bir metot çağırılırken, kullanılırken, tetiklenirken parametrelerine türlerine uygun değerler gönderilmek ZORUNLUDUR!
>
> Eğer ki bir metodun parametrelerine zorunlu bir şekilde değer göndermek istemiyorsak, parametreye değeri isteğimize göre/opsiyonel olarak göndermek istiyorsak o parametrenin bu durumu karşılayabilecek bir özellikte olması gerekmektedir. İşte bu özelliğede opsiyonel parametreler denmektedir.
>
> Bir parametrenin opsiyonel olması demek, o parametrenin varsayılan default değeri olması demektir.

```csharp
static void Main(string[] args)
{
    X(15,20);
    X(15);
    X();
    Y(5,15);
    Y(5);
}
//Tüm parametreler opsiyonel olabilir.
static public void X(int a = 5, int b = 20) // Metot parametrelerini asign operatörü ile bir değer atanırsa eğer o parametreye varsayılan değeri atanmış olur, haliyle opsiyonel parametre haline getirilmiş olur.
{
    
}
//Birden fazla parametre içerisinde bir kısmı opsiyonel parametre olabilir mi?
//Birden fazla parametre durumunda opsiyonel olanlar sağ tarafta TANIMLANMALIDIR!
static public void Y(int a, int b = 0, bool x = false)
{
    
}
```



## Tanımlanmış Metodun Kullanımı(Tanımlandığı Sınıf İçerisindeki Metotlar Tarafından Kullanımı)

```csharp
class Program
{
    
	static void Main(string[]args)
    {
        //Tetikleme = Çağırma = Kullanım
        //Bir metot tanımlandığı sınıf içerisindeki farklı bir metot içerisinden çağırılacaksa eğer tek yapılması gereken sadece isminin 		çağırılmasıdır.
    	X();
    }
    	
	static void X()
    {
        
    }
}
class Ornek
{
    public void A()
    {
        B();
    }
    public void B()
    {
        C(15);
    }
    private int C(int a)
    {
        return a;
    }
}
```



### Başka Sınıfta Tanımlanmış Metotların Erişimi-Referans ve Nesne İlişkisine Hafiften Temas Edelim

> Referans ve Nesne İlişkisine Hafiften Temas Edelim :
>
> * int = 3;
>   string = "Ahmet";
>   bunlar ayrı ayrı birer değişkendir.
>
> * adi, soyadi, yasi, medeniHali, gozRengi vs.. kompleks değerleri bir arada tutan yapıya nesne demekteyiz.
>
> * Nesne dediğimiz yapıyı oluşturmamızı sağlayan yapının adı da class'tır.
>
> * Class bir modelse, nesne class'ın verisidir.
> * Class'ın içerisinde tanımlamış olduğumuz metot, o class'tan üretilecek olan her bir nesnenin elemanı olacaktır.
> * Farklı class'larda oluşturulmuş metoda erişebilmemiz için o sınıflardan nesne oluşturmamız gerekiyor.
> * Nesne new Keyword'ü ile oluşturuluyor.
> * Referans, oluşturulmuş nesnenin işaretlenmesini sağlayıp o nesneye de erişmemizi sağlayan bir değişken.

```csharp
//Sınıf (Class) yer yüzündeki herhangi bir olguyu modellememizi sağlayan yapılanmadır. İçerisinde ilgili olguya dair alanları (field) barındıran ve bu alanlar üzerinde işlem yapmamızı sağlayacak olan (metotları) barındıran bir yapıdır.
//Nesne : Class'tan üretilen değer/veri
//Referans : Class'tan üretilen değeri kullanmamızı sağlayan yapıdır.
class Program
{
    static void Main(string[]args)
    {
        Ogrenci ogr = new Ogrenci(); //ogr referansı ile bir nesne oluşturduk.
    }
}
class Ogrenci
{
    string adi;
    string soyadi;
    int yasi;
    int sinif;
    //...
}
```

> Sonuç olarak, başka sınıfta tanımlanmış bir metoda erişebilmek için o sınıftan oluşturulmuş bir nesneye ihtiyacımız vardır.



### Başka Sınıfta Tanımlanmış Metotların Erişimi

```csharp
class Program
{
    static void Main(string[]args)
    {
        Matematik matematik = new Matematik();
        Console.WriteLine(matematik.Topla(15,2));
        Console.WriteLine(matematik.Cikar(15,2));
        Console.WriteLine(matematik.Carp(15,2));
        Console.WriteLine(matematik.Bol(14,2));
        //Console.WriteLine(matematik.ModAl(15,2)); --> Matematik içerisinde ModAl private olduğu için Program sınıfından erişilemez.
    }
}
class Matematik
{
    public int Topla(int sayi1, int sayi2)
    {
        return sayi1 + sayi2;
    }
    public int Cikar(int sayi1, int sayi2)
    {
        return sayi1-sayi2;
    }
    public int Carp(int sayi1, int sayi2)
    {
        return sayi1*sayi2;
    }
    public int Bol(int sayi1, int sayi2)
    {
        return sayi1/sayi2;
    }
    private int ModAl(int sayi1, int sayi2)
    {
        return sayi1%sayi2;
    }
}
```

> Tanımlanmış bir metodun başka sınıfta çağırılabilmesi için erişim belirleyicisinin public olması gerekmektedir.



### Metotlarda Non Trailing Named Arguments Özelliği

> Non Trailing Named Arguments :
> Çağırılan metodun parametrelerine değer gönderirken, sıralı bir şekilde değil de, isimsel bazda kullanım sergilememizi sağlayan bir özelliktir.

* Kullanım alanları
  * Hangi parametreye hangi değerlerin gönderildiğini direkt görebilmek için bu özelliği kullanırız.
  * Göreceli bir şekilde çok parametreli fonksiyonlarda hedef parametrelere değer göndermemizi sağlayan bir özelliktir.

```csharp
static void Main(string[]args)
{
    X(3,5,"abc");//Normal kullanım
    X(c:"abc",a:5,b:15);//Non Trailing Named Arguments
}
static void X(int a, int b, string c)
{
    
}
```

> Dikkat! Eğer ki non trailing named arguments kullanıyorsanız, tüm parametreler için kullanmaya özen gösteriniz. Yoksa karışıklığa sebep olabilmektedir.



### Metotlarda In Parametreleri (C# In Keyowrdü)

```csharp
//1. parametrenin değerini metodun içerisinde herhangi bir yerde çağırıp kullanabiliriz.
//2. metot içerisinde üretilen herhangi bir değeri tutacak değişken oluşturmaktansa parametre üzerinde bu değeri tutabiliriz. Yani parametrenin değerini değiştirebiliriz. (Çünkü parametreler özünde değişkendir.)
static void X(int a)
{
    a = 123;
}
//In komutu sayesinde parametreye verilen değeri sabit tutabilmekteyiz.
//In komutu metodun parametresini readonly(sadece okunabilir) hale getirir.
static void Y(in int a)
{
    a = 123; // Derleyici hatası vermektedir.
}
//In komutunun kullanıldığı parametrelerde eğer ki metot içerisinde farklı bir assign durumu söz konusu olursa derleyici hatası verecektir.
static void X(in int a, int b, in char c)
{
    b=353;
}
```



## Local Functions(Metot İçerisinde Tanımlanabilir Yerel Metotlar)

> Local functions : Bir metot içerisinde tanımlanmış olan metotlardır!
>
> Metotlar sadece class'lar içerisinde tanımlanabilir demiştik. Halbuki OOP'de göreceğimiz struct, abstract class, interface, record yapılanmalarında da metotlar tanımlanmaktadır. Metotlar bu saydıklarımızın dışında KESİNLİKLE başka bir yerde tanımlanamaz!
>
> Metotlar kesinlikle metotların içerisinde tanımlanamaz demiştik. Halbuki C# 7.0'da gelen local function özelliği sayesinde metot içerisinde metot tanımlanabilmektedir.

```csharp
public void X() //Metot Prototip : [erisim belirleyici][geri donus degeri][metot adi]{.....}
{
    Y();
    void Y() // Local Function Prototip : [geri donus degeri][metot adi]{....}
    {
        System.Console.WriteLine("Merhaba");
    }
    Y();
}
//Local Function Tanımlama Kuralları
//1. Erişim belirleyici(Access Modifier) yazılmaz!
//2. Local function olarak tanımlanan fonksiyon adı tanımlandığı fonksiyonun adından farklı olmalıdır! Aksi taktirde derleyici hatası VERMEZ!

//Kullanım Kuralları
//- Bir local function sade ve sadece tanımlandığı metodun içerisinde kullanılabilir.
//- Local function tanımlandığı metodun içerisinde her yerden erişilebilir.

//Amacı
//Local function, sadece tek bir metotta tekrarlı bir şekilde kullanılacak bir algoritmayı/kod parçacığını/işlemi o metoda özel bir şekilde tek seferlik tanımlamamızı ve kullanmamızı sağlamaktadır.

//Muadilleri
//Anonim, Delegate, Func
```



## Static Local Functions(Metot İçerisinde Tanımlanabilir Statik Yerel Metotlar)

> Static local function kullanmak local function kullanmaktan daha performanslıdır.

```csharp
public void X(int a)
{
    int b = 0;
    void Y() //local functionlarda içerdeki metotun, ana metotta tanımlanmış verilerine erişebilmesi mümkündür.
    {
        System.Console.WriteLine(a);
        System.Console.WriteLine(b);
    }
}
public void A(int a)
{
    int b = 0;
    static void B(int _a, int _b)
    {
        // a; b; --> çağırmak istediğimizde, statik olan local function bu aradaki erişimi ve maliyeti ortadan kaldırmıştır.
        System.Console.WriteLine(_a);
        System.Console.WriteLine(_b);
    }
    B(a,b);
}
```



## Metotlarda Overloading (Çoklu Yükleme)

> Overloading : Çoklu Yükleme
>
> Bir sınıf içerisinde belirli kurallar dışında, aynı isimde birden fazla metot tanımlanamaz!
>
> Method Overloading : 
>
> Bir class içerisinde belirli kurallar çerçevesinde aynı isimde birden fazla metot oluşturmaya Method Overloading denir.

```csharp
//Overloading Kuralları:
    //Bir sınıf içerisinde birden fazla aynı isimde metot tanımlayabilmek için şu kurallara dikkat edilmesi gerekmektedir.
    //Metot Overloading işlemi yapaiblmek için metotların isimleri aynı olmalıdır.
    //Bu metot içerisinde fark yaratmamız gerekmektedir.
    //Bu fark bizzat metot imzalarında olmalıdır!
    //Metotlar arasında farkı yaratırken, erişim belirleyicileri, geri dönüş değerleri aktif rol oynamamaktadır.
    // *Parametre sayıları ya da parametre türleri farklı olmalıdır!*

class Matematik
{
    public int Topla(int sayi1, int sayi2)
    {
        return sayi1 + sayi2;
    }
    public int Topla(int sayi1, int sayi2, int sayi3)
    {
        return sayi1 + sayi2 + sayi3;
    }
    public int Topla(double sayi1, int sayi2)
    {
        return (int)(sayi1 + sayi2);
    }
}

```



## Recursive (Tekrarlamalı/Özyinelemeli) Metotlar

Recursive metot : 

* Kendi içerisinde kendisini çağıran/tetikleyen metottur, bir yaklaşımdır.
  Recursive metotlar, özel bir yapılanma değildir! Normal bildiğimiz metot yapılanmasından ayrı birşey değildir.

> Anlaşılması, kullanılması ve anlatılması zordur!

Amacı :

* Öngörülemeyen, derinliği tahmin edilemeyen, sonu bilinmeyen durumlarda tercih edilebilir.

> Döngülerin kullanıldığı heryerde recursive fonksiyon kullanılabilir, lakin recursive kullanılan heryerde döngü kullanılamaz!

```csharp
void X()
{
    for (int i = 0; i <20; i++)
    {
        Console.WriteLine("qwdqwdqwd");
        while (true)
        {
            X(); // Kendi içerisinde herhangi bir yerde en az bir kere çağırıldığı taktirde bu bir recursive fonk. olmaktadır.
        }
    }
}
```

> İnceleme1 : X metodu tanımlayalım ve nasıl bir tepki vereceğini gözlemleyelim.
>
> ```csharp
> void X()
> {
>  Console.WriteLine("Merhaba");
>  X();
>  Console.WriteLine("Dünya");
> }
> ```
>
> Bu metot tetiklendiğinde sonsuza kadar Merhaba yazdıracaktır. Peki neden Dünya yazmadı?
> Çünkü kendi içerisinde tekrar tetiklendiği noktada, bir sonraki metoda geçiş yaptı ve bu şekilde kısır bir döngüye girdi.

> İnceleme2 : Yukarıda tanımladığımız (İnceleme1'deki) metot üzerinde bu metodu yönetebilmemiz gerekir.
> 3 Kere Merhaba yazan bir uygulama geliştirelim.
>
> ```csharp
> void X(int a = 3)
> {
>  Console.WriteLine("Merhaba");
>  if(a > 1)
>      X(--a);
> }
> ```
>
> 

> İnceleme3 : Yukarıda tanımladığımız (İnceleme2'deki) metot üzerinde 7 kere Merhaba ve Dünya yazan bir uygulama geliştirelim.
>
> ```csharp
> void X(int a = 7)
> {
>  Console.WriteLine("Merhaba");
>  if (a > 1)
>      X(--a);
>  Console.WriteLine("Dünya");
> }
> ```
>
> Bu metodu tetiklediğimizde karşımıza çıktı olarak;
> Merhaba
> Merhaba
> Merhaba
> Merhaba
> Merhaba
> Merhaba
> Merhaba
> Dünya
> Dünya
> Dünya
> Dünya
> Dünya
> Dünya
> Dünya 
> şeklinde bir çıktı gelmektedir.
> Peki bu algoritma nasıl çalıştı ve neden Merhaba Dünya şeklinde bir çıktı vermedi?
>
> <img src =https://i.imgur.com/h1ESEHS.png width=55% align= left />
>
> Öncelikle ilk metot tetiklenir, Merhaba yazdırır, ardından metot kendisini tetikler ve yeni metot merhaba, diye koşul sağlandığı sürece devam eder.
>
> Son metotta(7) Merhaba yazdırılır ve koşul sağlanmadığı için yeniden kendisini çağırmaz ve Dünya yazdırılır ve konspeti tamamlar. Metot 6'ya döner ve Dünya yazdırarak konsepti tamamlar. Metot 5'e döner ve Dünya yazdırarak konsepti tamamlar.. diye ilk tetiklenen metota kadar bu durum devam eder.
> İlk tetiklenen metot Dünya yazdırır ve konsepti tamamlar.

Örnek 1 :
Belirli bir değer aralığındaki 5'in katı olan tüm sayıları toplayan rec. fonk. yazalım.

```csharp
/*
int s1 = 100, s2 = 200;
for (int i = s1; i < s2; i +=5)
{
    //..
}
*/
Console.WriteLine(Topla(10,20));

int Topla(int baslangic, int bitis)
{
    if(baslangic % 5 == 0)
        return baslangic + Topla(++baslangic, bitis);
    if (baslangic < bitis)
        return Topla(++baslangic, bitis);
    return 0;
}
```



Örnek 2 :
Bir klasör dizinindeki bütün klasörleri ekrana getir. (Klasör içerisinde klasör varsa hepsini getireceği için derinliğini bilemiyoruz)

```csharp
List<FileInfo> files = DosyaYazdir("C:/Users/Guest/Desktop")
List<FileInfo> DosyaYazdir(string path)
{
    List<FileInfo> fileInfos = new();
    DirectoryInfo directoryInfo = new(path);
    DirectoryInfo[] directoryInfos = directoryInfo.GetDirectories();
    if (directory.Any())
    {
        foreach ( DirectoryInfo directory in directoryInfos)
        {
            fileInfos.AddRange(DosyaYazdir(directory.FullName));
        }
    }
    else
        directoryInfo.AddRange(directoryInfo.GetFiles());
    return fileInfos;
}
```



## C#'ta ref Keywordü Nedir?

> Ref keywordü, referanstan gelmektedir.
> Referans, OOP kavramıdır.
> OOP'de nesneler(object) RAM'de Heap bölgesinde tutulmaktadır.
> OOP'de referanslar = operatörü ile itelişime geçebilmektedirler. Bir referans, işaretlediği herhangi bir nesneyi = operatörü sayesinde farklı bir referansla işaretletebilir.
> Yani, referanslar da = operatörü neticesinde herhangi bir verisel/nesnel türeme söz konusu olmamakta, işaretlenmiş nesne diğer referans tarafından işaretlenmektedir.
>
> ref Keywordü :
> Değer türlü değişkenlerde referans operasyonları yapmamızı sağlayan bir keyworddür.
> ref keywordü, değer türlü değişkenlerin referanslarını çağırmamızı/kullanmamızı sağlayan bir keyworddür.
>
> ```csharp
> int a = 5
> int b = a; //Dediğimizde deep copy yapmaktayız. Peki shallow copy yapmak istersek, yani a'yı b referans etsin istersek.
> ref b = ref a;//Değer türlü değişkenlerde shallow copy yapmamızı sağlayan bir keyworddür.
> //Ref keywordü, değer türlü değişkenlerin referans türlü değişkenler gibi çalışmasını sağlayan bir komuttur.
> ```
>
> ```csharp
> //Örnek 1
> int a = 5;
> ref int b = ref a;
> 
> Console.WriteLine(a);
> Console.WriteLine(b);
> 
> a += 5;
> Console.WriteLine(b);
> 
> b += 10;
> Console.WriteLine(a);
> ```
>
> ```csharp
> //Örnek 2
> int y = 10;
> Console.WriteLine(X(y)); //Değer türlü değişkenlerde bir metoda assing operatörü ile değerini göndermekteyiz.
> Console.WriteLine(X(ref y)); //ref keywordü ile y'nin işaretlediği değişkeni a olarak bildirmiş oluyoruz.
> Console.WriteLine(X(y)); //
> int X(int a)
> {
>  a = 15;
>  return a;
> }
> int X(ref int a)
> {
>  a = 25;
>  return a;
> }
> ```



## C#'ta Ref Returns Özelliği Nedir?

> Ref Returns :
> Metotlarda geriye değer döndürebilen yapılardır. Ayrıca metotlarda geriye nesnelerde döndürebilmekteyiz. Ayrıca ref returns özelliği sayesinde değer türlü değişkenlerin referanslarını da geriye döndürebilmekteyiz.
>
> ref returns özelliği sadece metotlarda geçerlidir.

```csharp
int a = 5;
int b = X(ref a);
Console.WriteLine(a);
Console.WriteLine(b);

ref int X(ref int y)
{
    y = 25;
    return ref y;
}
```

<img src=https://i.imgur.com/R349BAM.png width=75% align=left />



## C#'ta out Keywordü Nedir?

> out Keywordü :
> Metotların parametreleri üzerinden dışarıya değer göndermemizi sağlayan bir keyworddür.
> Bir metodun parametreleri varsayılan olarak INPUT'tur. Haliyle metotlarda tanımlanmış parametreler direkt içeriye değer almaya odaklanırlar..
> Eğer ki bir metodun parametresi dışarıya değer çıkaracaksa o parametrenin out keywordüyle işaretlenmesi gerekmektedir.

Kullanım 1 :

```csharp
//Output parametre barındıran bir metodu kullanırken, out parametrelerden gelecek olan değerleri karşılayacak değişkenler tanımlanmalıdır!
int _b = 0;
int a = X(out _b);

int X(out int b)
{
    //Bir metot out parametre(ler) barındırıyorsa, o parametrelere kendi içerisinde değer atanması gerekmektedir! Aksi taktirde derleyici hatası alınacaktır.
    b = 25;
    return 0; //Return ile geriye değer döndürebiliyoruz.
}
```

Kullanım 2 :

```csharp
int a = X(out int _b);
Console.WriteLine(_b);

int X(out int b)
{
    //Bir metot out parametre(ler) barındırıyorsa, o parametrelere kendi içerisinde değer atanması gerekmektedir! Aksi taktirde derleyici hatası alınacaktır.
    b = 25;
    return 0; //Return ile geriye değer döndürebiliyoruz.
}

```

TryParse :

```csharp
string a = "123";
if(int.TryParse(a, out int r))
{
    
}
else
{
    
}
```

------

> Prosedürel Kodlama notları sona ermiştir.

------

