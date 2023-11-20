# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Nesne Dışı Yapılanmalar - Struct



### Struct Nedir?

> C#'ta struct, değer türünde bir veri tipi oluşturmak için kullanılan bir veri yapısıdır.

Yani anlayacağınız, class'lar ile referans, struct'lar ile de değer türlü veriler oluşturulabilmetedir.

Struct'lar genellikle, class'lara nazaran küçük boyutlu ve hafif veriler oluşturmak için tercih edilseler de, kodlama sürecinde performans ve maliyet optimizasyonu açısından da tercih edilebilmektedirler.



**<u>Performans</u>**

Değer türlü veriler, nesnelere nazaran bellekte daha az yer kapladıkları gibi daha hızlı erişilebilir yapılardır. Bu da performans optimizasyonu açısından fark yaratacaktır.

**<u>Maliyet</u>**

Nesnelerin oluşturulması ve kullanıldıktan sonra imha edilmeleri ekstra iş yükü getirebilmektedir. Struct'lar da ise bu iş yükü ciddi manada törpülenmiştir diyebiliriz. Bu durumda maliyet optimizasyonu açısından fark yaratmaktadır.



### Struct Ne Amaca Hizmet Eder?

> Struct'lar temelde, yazılım sürecinde int gibi, char gibi, bool gibi kendimize ait değer türlü değişkenler oluşturmak için kullandığımız veri türleridir.

Özellikle bellek performansının kritik arz ettiği uygulamalarda, uygun noktalarda class'lar yerine struct'ları tercih edebilirsiniz.

Misal olarak; matematiksel veriler gibi basit değerleri temsil etmek için class'lar yerine struct'ları tercih etmeniz daha doğru olacaktır.

Ya da koordinat sistemindeki noktaları veya key/value çiftleri tarzında kimi değerleri struct olarak tanımlamak performans açısından daha elverişli olacaktır.

Kıssadan hisse yapmamız gerekirse eğer; kodlama sürecindeki birden fazla değerlerin/verilerin atomik bir temsili için struct'ları kullanırız!



### Struct Veri Türü Bellekte Nerede Saklanır?

> Struct'lar, value type yani değer türlü veri yapıları olduğu için belleğin Stack kısmında tutulurlar.

<img src=https://i.imgur.com/5IU49iH.png align=left />



### Struct ile Class Arasındaki Farklar Nelerdir?

#### Değer Türü vs Referans Türü

* Struct, value type bir veri türüdür. Bu yüzden bellekte Stack alanında saklanır.
* Class ise referance type bir veri türüdür. Haliyle, referansı belleğin Stack kısmında tutuluyor olsa da instance'ı Heap kısmında tutulmaktadır.



#### Kalıtım (Inheritance)

* Struct'lar kalıtımı desteklemez, farklı bir class'tan yahut struct'tan türemez veya miras alamazlar. Sadece interface'leri implement edebilirler.
* Class'ların ise kalıtımsal davranışı doğasında vardır.



#### Null Değer

* Struct'lar nullable türleri destekler, ancak varsayılan olarak nullable değillerdir.

* Class'lar ise nullable türlerdir ve varsayılan olarak da null olabilirler.

  ```csharp
  //MyStruct myStruct = null; //Hata verecektir.
  MyStruct? myStruct = null;
  ```



#### Hafıza ve Performans

* Struct'lar genellikle daha hafif ve performans odaklıdır. Değer türlü oldukları için bellekte daha az yer kaplarlar ve hızlı erişim sağlanabilirler. Ancak, büyük struct veriler performans sorunlarına yol açabilir.
* Class'lar ise daha fazla bellek kullanabilir ve daha yavaş olabilirler. Çünkü referanslar oluşturulması ve bellekte yer tahsisi yapılması gerekmektedir.



#### Eşitlik Karşılaştırması

* İki struct değerini aşağıdaki gibi Equals fonksiyonuyla karşılaştırırsak burada değer bazlı bir karşılaştırma yapılacaktır ve sonuç olarak 'Eşit' yazısını ekrana yazdıracaktır.
  ```csharp
  MyStruct myStruct1 = new()
  {
      MyProperty = 1
  };
  MyStruct myStruct2 = new()
  {
      MyProperty = 1
  };
  if (myStruct1.Equals(myStruct2))
  {
      Console.WriteLine("Eşit");
  }
  ```

* Aynı mantıkla class'ları değerlendirirsek eğer referans karşılaştırması gerçekleştirirler. Tabi burada istendiği ya da gerektiği taktirde Equals metodu override edilerek özel bir karşılaştırma tutumu sergilenebilir.



#### Performans ve Kopyalama Davranışı

* Struct'lar, değişkenler birbirlerine atandıkları taktirde deep copy gerçekleştirecek ve atanan veri çoğaltılacaktır. Böylece her iki struct arasında bir bağımsızlık durumu söz konusu olacaktır.

  ```csharp
  MyStruct myStruct1 = new()
  {
      X =123,
      Y = 321
  };
  MyStruct myStruct2 = myStruct1;
  ```

  <img src=https://i.imgur.com/9eg7hm0.png align=left />

* Class'lar da ise sadece referans kopyalanacak ve shallow copy davranışı söz konusu olacaktır. Böylece bir nesne birden fazla referans tarafından işaretlenerek, manipüle edilebilir olacaktır.

  ```csharp
  MyClass myClass1 = new()
  {
      MyProperty = 1
  };
  MyClass myClass2 = myClass1;
  ```

  <img src=https://i.imgur.com/WEyIDno.png align=left />

> <u>Maliyet</u> : Class **>** Record **>** Struct
> <u>Performans</u> : Struct **>** Record **>** Class



### Struct Nasıl Tanımlanır ve Kullanılır?

```csharp
struct MyStruct
{
    private int X;
    public int X
    {
        get => x;
        set => x = value;
    }
    public int MyProperty {get; set;}
    public void MyMethod()
    {
        //..
    }
}
```

Görüldüğü üzere bir struct; class gibi oldukça kolay bir şekilde tanımlanabilmektedir.
Dikkat ederseniz eğer struct'ın içerisinde field, property ve method tanımlayabiliyoruz.

> Struct'ların tanımlanması bu kadar basit. Kullanımına gelirsek eğer burada **new ile kullanmak, new'siz kullanmak** gibi iki farklı durum söz konusu olacaktır.



#### Struct'ı new Operatörüyle Örneklendirirsek Ne Olur?

* Bildiğiniz gibi new operatörü class'larda kullanıldığı zaman ilgili class'tan bir nesne talep edilmekte ve üretilen bu nesne belleğin Heap kısmında muhafaza edilmektedir.
* Struct yapısında ise new operatörü kullanırsak eğer, evet ilgili yapıdan bir nesne benzeri değer üretilecektir ama struct'ın bir değer tipli veri olmasından dolayı o değer belleğin Stack kısmında muhafaza edilecektir.
* Ayrıca new operatörü sayesinde struct içerisindeki field'lara default değerleri atanmış olacaktır ve varsa property ile metotlar kullanılabilir hale gelecektir.

> Uzun lafın kısası bir struct'ı new ile kullanmanın esas farkı o struct içerisindeki property ve metotların işlevselliğini kazandırabilmektedir.



#### Struct'ı new Operatörü Olmaksızın Kullanırsak Ne Olur?

* Struct'lar da class'lardaki gibi nesne mecburiyeti olmadığı için illa new operatörüyle kullanmak zorunda değiliz!
* Yani new operatörü ile struct yapıdan bir nesne üretmeden de o struct'ı kullanabilmekteyiz.
* Tabi sadece o struct'taki field'ları kullanabilmekteyiz. Property ve metotları kullanabilmek için struct'ı new'lememiz gerekmektedir.

> Haliyle new operatörü olmaksızın kullanılan struct üzerinden bir field'ı kullanacaksanız, önce o field'ın ilk değerinin verilmesine özen göstermelisiniz, aksi taktirde derleyici hatasıyla karşılaşırsınız.



### Struct'lar da Kalıtımsal Durumlar

Struct veri türleri sadece interface'leri implement edebilirler. Bunun dışında ne farklı bir struct'dan ne de class'dan kalıtım alıp, verebilir!



### Struct'ların davranışı sealed class'lara benziyor mu?

Struct veri yapısı, fıtratı gereği kendiliğinden sealed class'lar gibi davranış sergilemekte ve farklı bir struct ile kalıtımsal ilişkiye girmemektedir.



### Struct'ın this Keyword'ü ile Kendini Değiştirebilmesi

Struct veri türü, kendilerini this keywordü ile aşağıdaki gibi değiştirebilen yapılardır.

```csharp
struct MyStruct
{
    public int X{get; set;}
    public int Y{get; set;}
    public void NewStruct()
    {
        this = new MyStruct();
    }
}
```

> Esasında bu tarz bir işlem class yapısı için mümkün olmayacağından dolayı ilginç bir özelliktir.
>
> Class'ların this keywordü read-only iken, struct'ların ise değildir! Haliyle bu şekilde kendi içlerinde kendilerini değiştirebilmektedirler.



### Son Kırıntılar

* Struct'lar içlerinde static memblerlar barındırabilir.
* Bir sınıfın tüm member'ları value type ise bir struct, yok eğer değilse bir class tasarlayın.
* Struct'lar özünde hafif (lightweight) bir class yapısıdır diyebiliriz.
* Belirli senaryolarda, performans açısından struct'lar class'lara alternatif olarak değerlendirilebilir.
* Garbage Collection'ın performansını artırabilmek için struct tercih edilebilir.
* Struct'larda Static Constructor tanımlanabilir.
