# C# Notları (Hata Kontrol Mekanizmaları)

[TOC]



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
> >     //Olası çalışma zamanı hatalarını verebilecek kodlarımızı buraya yazıyoruz.
> > }
> > catch
> > {
> >     //try içerisinde olası hata söz konusuysa, kodun akışı orada kesilecek ve akış catch bloğundan devam edecektir.
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
> >     //Olası çalışma zamanı hatalarını verebilecek kodlarımızı buraya yazıyoruz.
> >     Console.WriteLine("Lütfen birinci sayıyı giriniz : ");
> >     int sayi1 = int.Parse(Console.ReadLine());
> >     Console.WriteLine("Lütfen birinci sayıyı giriniz : ");
> >     int sayi2 = int.Parse(Console.ReadLine());
> > 
> >     Console.WriteLine("Toplam : " + (sayi1 + sayi2));
> > }
> > catch
> > {
> >     //try içerisinde bir hata söz konusu olduğunda catch bloğu tetiklenecektir.
> >     //hataya dair; long, kullanıcı bilgilendirme, kontrollü kapanış vs..
> >     Console.WriteLine("Lütfen doğru bir ifade giriniz.");
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
> >     sayi1 = int.Parse(Console.ReadLine());
> >     Console.WriteLine("Lütfen ikinci sayıyı giriniz.");//Normalde dışarıya yazmamız gerekir ancak akış gereği burada tutacağız.
> >     sayi2 = int Parse(Console.ReadLine());
> > }
> > catch
> > {
> >     Console.WriteLine("Lütfen doğru bir ifade giriniz.");
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
> >     int s1 = 0, s2 = 10;
> >     int sonuc = s2/s1;
> > }
> > catch (Exception ex)
> > {
> >     Console.WriteLine("Mesaj : " + ex.Message);
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
>>
>> <img src="https://www.tutorialsteacher.com/Content/images/csharp/exception-classes.png" align=left>
>>
>> * Exception : Tüm hata türlerinin atasıdır.
>>
>>   
>
>



#### try-catch : Exception Dışında Farklı Bir Tür ile Hata  Yakalama

>
>
>```csharp
>try
>{
>    int s1 = 0, s2 = 10;
>    int sonuc = s2/s1; //0'a bölme hatası
>}
>catch (DivideByZeroException ex) //(Exception ex) yerine yakalayacağımız hataya göre farklı bir tür verebiliriz.
>{
>    Console.WriteLine("Mesaj : " + ex.Message);
>}
>```
>
>* Yukarıdaki örnekte DivideByZeroException hatası almazsak ve başka bir hata alırsak, bu durumda catch bloğu bu hatayı yakalamayacaktır.
>
>  catch bloğu, bir parametre tanımlanmazsa eğer, tüm hataları karşılayabilen bir bloktur.
>
>  Ayrıca parametre tanımlanır ve bu parametrenin türü exception'sa yine tüm hataları karşılayabilmektedir.
>
>  *Eğer ki, parametre exception değil, özelleştirilmiş bir hataya indirgenmişse böyle bir durumda sadece ilgili türe ait hataları yakalayabilecek, karşılaştırabilecektir.*
>
>  
>
>  > Örnek
>  >
>  > ```csharp
>  > try
>  > {
>  >     int islem = int.Parse("metin");//format hatası
>  > }
>  > catch (DivideByZeroException ex) //0'a bölme hatası yakalama
>  > {
>  >     Console.WriteLine("Mesaj : " + ex.Message);
>  > }
>  > ```
>  >
>  > * Bu senaryoda try-catch bloğu kullanıldığı halde fiziksel olarak patlama meydana gelmiş ve uygulama sona ermiştir.
>  >
>  >   Çünkü, catch bloğu eğer ki bir türe özgü ise(genel olmayan) böyle bir durumda sadece o türden hataları yakalayabilen bir yapı haline gelmektedir.
>  >
>  >   Dolayısıyla try-catch bloğu hangi parametre tanımlandıysa o parametrenin yakalayabileceği türdeki hataları manipüle etmekte, eğer ki parametrenin dışında farklı bir türde hata fırlatılırsa try-catch bloğu ilgili hatayı manipüle etmeyecek ve fiziksel olarak uygulamayı patlatıp sonlandıracaktır.
>  >
>  > * Çözüm olarak bu durumda birden fazla catch bloğu ile diğer türdeki parametreleri kontrol etmek olacaktır. Bu da bir sonraki konumuzda yer alacaktır.
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
> >     int sonuc = s2 / s1; //DivideByZeroException
> >     int islem = int.Parse("metin");//Format exception
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
>     //hata verebilecek kodlar buraya
>     Console.WriteLine("try");
> }
> catch
> {
>     //hata aldıktan sonra yapılacak işlemler buraya
>     Console.WriteLine("catch");
> }
> finally
> {
>     //her iki durumda da çalışmasını istediğimiz kodlar
>     Console.WriteLine("finally");
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
> >     int s1 = 0, s2 = 10;
> >     int sonuc = s2 / s1;
> > }
> > catch (DivideByZeroException ex) when(x == "a") //şartlı kullanım 1
> > {
> >     Console.WriteLine("Mesaj : " + ex.Message);
> > }
> > catch (DivideByZeroException ex) when(x == "b") //şartlı kullanım 2
> > {
> >     Console.WriteLine("Mesaj : " + ex.Message);
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
>     Console.WriteLine("Hediye gönder...");
> }
> else
> {
>     Console.WriteLine("Hediye gönderme");
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
> 