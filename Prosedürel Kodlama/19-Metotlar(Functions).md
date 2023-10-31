# C# Notları (Metotlar - Functions)

[TOC]



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
>     Console.WriteLine("Merhaba");
>     X();
>     Console.WriteLine("Dünya");
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
>     Console.WriteLine("Merhaba");
>     if(a > 1)
>         X(--a);
> }
> ```
>
> 

> İnceleme3 : Yukarıda tanımladığımız (İnceleme2'deki) metot üzerinde 7 kere Merhaba ve Dünya yazan bir uygulama geliştirelim.
>
> ```csharp
> void X(int a = 7)
> {
>     Console.WriteLine("Merhaba");
>     if (a > 1)
>         X(--a);
>     Console.WriteLine("Dünya");
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
>     a = 15;
>     return a;
> }
> int X(ref int a)
> {
>     a = 25;
>     return a;
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

