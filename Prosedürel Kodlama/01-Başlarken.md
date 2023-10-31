# C# Notları (Başlarken)

[TOC]



## C# Nedir?

* Microsoft tarafından .Net çatısı altında geliştirilen ve gelişen modern programlama dilidir.
  
* Açık kaynak ve ücretsizdir.
  
* C benzeri bir dildir.
  
* OOP'yi ve OOP'nin gelişimini destekler.

    > OOP: Object Orianted Programing (Nesne Tabanlı Programlama)
    
* Orta seviyeli bir dildir.

*	Programlama Dillerinin Sınıflandırılması

    * Çok yüksek seviyeli diller (visual basic, vb.net, Foxpro, access..)
    * Yüksek seviyeli diller (pascal, basic, fotran..)
    * Orta seviyeli diller (c,c++,c# , Java, Ada..)
    * Düşük seviyeli diller (assembly..)
    * Makine dilleri (1 ve 0'lardan oluşur)
            
	> Burada kalite mi söz konusu? Hayır bir dil yüksek seviyeli ise beşeri dile daha yakındır, baktığınız zaman makale gibi okursunuz.
    Bir dil okunabilirliği düşüyorsa sembollerle ifade ediliyorsa ve bir matematiğe mantığa göre yorumlanabiliyorsa o dil düşük seviyelidir.

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

>	Dolayısıyla toplulukların sadece Windows işletim sistemlerini kullanmaması ve farklı işletim sistemlerinde de yazılım ve programlama yapılabilmesine imkan kılan Core gelmiştir.

<img src="https://i.stack.imgur.com/kAGE2.png" alt="" width=auto height=auto>

Bu çatı altında;
*    Asp.Net 5
*    Universal Windows Apps
*    Core CLR
*    .Net Native yazılımları geliştirilir.

*	Cross Platform'dur. Çeşitli işletim sistemlerinde uygulamaları destekler.
*	Modüler'dir.
*	Framework'ü de kapsar.

---

## Compiler Nedir?

Bir programlama dili __derlenen__ bir dilse, bu programlama dilinin __önce derlenmesi sonra çalıştırılıp sonuç alınması gerekir.__

__Peki derlemek ne demek?__
>		Yazdığımız kodları makinenin anlayabileceği koda çevrilmesi gerekmektedir, bu çevrilme işlemi derlemedir.
>
>	>	Yani kullanıcının çalıştırabileceği yazılım uzantısı .exe'yi derleme ile elde ederiz.


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
>> Bir başka örnek vermek gerekirse; bir banka uygulaması yaptığımızı varsayarsak, tek bir solution altında bu banka ile ilgili bankamatik, ödeme gibi alt projeleri olabilir.

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
>> dotnet new [project type] --name [project name] + --force --> Proje oluştururken dizinde aynı isimde proje varsa ve bunun üzerine yazmasını istiyorsan ekliyoruz
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
>>Derlemeden önce projeyi restore eder.
				\bin\Debug\net5.0\ dizinine çıktı verir
---
```			  
> dotnet publish
```
> Projeyi derleyerek, yayınlanabilir dosyaları çıktı olarak verir.
>>Çıktı olarak;
>>*	.dll,
>>*	.deps.json (projenin tüm bağımlılıklarını içerir)
>>*	.runtimeconfig.json (runtime konfigürasyonları)
>>*	Uygulama bağımlılıklarının dll'leri
>
>> \bin\Debug\net5.0\publish dizinine çıktı verir
---
```				
> dotnet run
```
> Uygulamayı derler, ayağa kaldırır. Çalıştırır.
>> run --no-build (derlemeden ayağa kaldırır)
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
>>örn. dotnet add package Serilog.Sinks.Seq --version 4.0.0
---
```	
> dotnet add reference
```
> Uygulamaya fiziksel bir dll dosyasını referans etmemizi sağlar
>> dotnet add [source project].csproj reference [target project].csproj
---
```
> dotnet remove package 
```
> Uygulamaya yüklenmiş olan paketlerin/kütüphanelerin silinmesini sağlar
>> dotnet remove package [package name]
```
> dotnet remove reference
```
> Uygulamaya referans edilmiş .dll'leri kaldırır
>> dotnet remove reference [reference name]
---
```						
> dotnet list reference
```
> Uygulamada referans edilen tüm paketleri listeler
>> dotnet list reference
---

## Programlamaya Başlarken Temel İlkeler

###    Don't repeat yourself (DRY)
>Kodsal olarak sürekli kendini tekrar etmemen gerekir.
>> Hem kod açısından hem ezber açısından yaşadıklarımızı tekrar etmiyoruz.

###    Anlamlı isimlendirme

>örneğin mevsimleri isimlendirirken;
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
>>Kod yeniden yapılandırmanın başarılı olabilmesi için eşli programlama gereklidir.

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
Bir Sprintin en başında yapılan etkinliktir. Planlamada tüm Scrum Ekibi mevcut Sprint içinde yapılacak işi planlar.

Planlama toplantısının süresi Sprintin uzunluğu ile orantılıdır. Bir aylık Sprint için planlama toplantısı en fazla 8 saat, iki haftalık bir Sprint için ise 4 saat olabilir.

Sprint Planlama toplantısında temel olarak, içinde bulunulan Sprint süresince kullanılabilir ürün parçası olarak neler yapılacağı ve bu ürün parçalarını oluşturmak için yapılacak işlerin nasıl gerçekleştirileceği sorularına cevap aranır.

Ürün İş Listesinde bulunan işler üzerinde tahminleme yapmak için Planlama Kart Oyunu en çok kullanılan yöntemlerden biridir.

Geliştirme Ekibinin ne kadar iş alacağını kendisi seçmesi, kendi kendine organize olabilen ekip olma yolunda önemli bir yöntemdir.

#### Günlük SCRUM (Daily SCRUM)

>Geliştirme Ekibinin son bir gün içinde yaptığı faaliyetler ve planladığı faaliyetler hakkında bilgi alışverişini yaptığı toplantıdır.
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
