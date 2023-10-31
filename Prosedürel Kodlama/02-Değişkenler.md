

# C# Notları (Değişkenler)

[TOC]



## Giriş


**En temelden ele almamız gerekirse,**
>Bir yazılım çalıştırıldığında, içerisindeki verileri RAM'de tutar. Yazılım veri tutmaz. RAM'den alır ve RAM'e yerleştirir.
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
<br>Tür elimizdeki veriye göre bildirilmelidir.

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
>>Hatırlatma : Belleğin STACK kısmında değer türlü değişkenler, değerleri ve tür bilgileri tutulur.

<img src="https://imgur.com/tE3viXo.png" align=left>

> Eğer ki tanımlama esnasında bu değişkene değer atamak istersek;
>> Konsepti kapatmadan önce '=' assign(atama) operatörünü kullanarak ilgili değişkenin türüne uygun bir değer (9) göndereceğiz.

```csharp
int x = 9 ;
```

> Burada sol tarafta bir değişkenimiz var,
>> Arada '=' assign(atama) operatörümüz var
>>> sağ tarafta ise atanacak değer yer alıyor.

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
>> Daha sonra değer atamaya örnek vererek devam edelim,

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

1.	Metinsel Değerler
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
	
2.	Karaktersel Değerler
	* char : Karaktersel ifadeler tek tırnak içerisine yazılmalıdır. '.'
	
	  ```csharp
	  char karakterA = 'A';
	  string metinA = "A";
	  /* 'A',"A" -> Dikkat : Tek tırnak içerisine yazılan ifade karakterdir, çift tırnak içerisindeki string dir. Tek bir karakterlik değer tutulması gereken yerde string kullanılırsa (bellek optimizasyonu açısından) boş yere alan tahsisinde bulunulmuş olur.
	  */
	  /*Gerçek hayattan örnek vermek gerekirse; 1 tane çiçek için saksı (char) yeterli olacak iken 1 dönüm tarla(string) kiralanmış olarak düşünebilirsiniz.*/
	  
	  char karakter = 'AB'; // Hatalı : Tek bir karakter atanabilir. Compiler hata verecektir.
	  
	  
	  ```
	
3.	Mantıksal Değerler
	* bool : Mantıksal ifadeler direkt olarak true ya da false ile belirtilir.
	
	  ```csharp
	  bool medeniHal = true; yada = false; // true : 1 // false : 0
	  ```
	
4.	Sayısal Değerler
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
>> Null : değersiz, değeri yok anlamına gelir. Boş demek değildir.
>>>Boşluk space dediğimiz boştur ama yine bir karakterdir.

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
>Metodu faaliyet alanlarına böle biliyoruz.

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

