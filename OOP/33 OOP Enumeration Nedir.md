# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Nesne Dışı Yapılanmalar - Enumeration



### Enumeration Nedir, Neden Kullanılır?

> Enumeration, belirli sayısal değerleri sabitleştirilmiş metinsel karşılıklarıyla temsil etmek için kullanılan bir veri türüdür.
> Biliyorsunuz ki bizler, kodlama sürecinde belirli durumları sayısal olarak ifade ederiz.

> Misal olarak; cinsiyet bilgisi yahut evlilik durumu gibi ikili verileri genellikle 0 veya 1 olarak işleriz.
> Ya da bir siparişin durumunu ifade eden verileri de: 0(bekliyor), 1(işleniyor), 2(sipariş başarılı), 3(iptal edildi) şeklinde sayısal kabuller üzerinden yönetebiliriz.

* İşte bu yaklaşım neticesinde kod içerisinde iş mantıklarını sayısal veriler üzerinden yönetmek oldukça zor ve karmaşık olabilmektedir.

> Düşünsenize, sipariş durumunu kontrol eden kodda şöyle bir ifade geçmektedir;
>
> ```csharp
> //..
> if (order.Status ==4)
> {
>     
> }
> else if (order.Status == 2)
> {
>     
> }
> ```
>
> Şimdi siz bu kodu ilk gören biri olsanız bu 4'ün, 2'nin ne anlama geldiğini ilk bakışta anlar mısınız?

* İşte bizler böyle durumlara karşın sayısal değerleri kod sürecinde daha okunaklı ve anlaşılabilir kılan metinsel ifadelerle temsil edebiliyor ve kodu şu hale getirebiliyoruz.

  ```csharp
  //..
  if (order.Status == OrderStatus.Failed)
  {
      
  }
  else if (order.Status == OrderStatus.Completed)
  {
      
  }
  ```

> Böylece koda bakan bir geliştirici en azından siparişin hangi durumlarına göre aksiyonlar alındığını direkt koddan, kimseye sorma gereği duymaksızın anlayabilecektir.
>
> Anlayacağınız enumeration veri yapısı, kodun okunabilirliği ve anlaşılabilirliğini attırdığı gibi bir yandan da kodun bakımını daha da kolaylaştırmaktadır, diyebiliriz.



#### Enumeration'ların Ana Amaçları

* **Anlaşılabilirlik ve Okunabilirlik**

  Geliştiriciler için kodun içerisinde sabit sayısal değerler kullanmaktan ziyade bu değerlere karşılık anlamlı isimler kodun daha anlaşılır ve okunabilir olmasını sağlayacaktır. Misal olarak; Pazartesi için 1 değeri yerine **DayOfWeek.Monday** ifadesini kullanmak daha açıklayıcıdır.

* **Değerleri Gruplama**
  Enumeration'lar; cinsiyet gibi, sipariş durumları gibi, haftanın günleri ya da kullanıcı türü gibi değerleri mantıklı bir şekilde gruplamak için de kullanılmaktadırlar. Nihayetinde kodun içerisinde karışık sayısal değerlerden ziyade, anlamlı ve kodun mantığını yansıtan tanımlar üzerinden çalışma sağlar.

* **Hata Riski Azaltma**
  Enumeration'lar, değerlerin belirli bir kümeden seçildiğini garanti ederler. Bu yanlış değerlerin veya değerlerin dışında kalan durumların kullanımını önlemekte ve hata riskini azaltmaktadır.

* **Uygulama ve Bakım Kolaylığı**
  Enumeration'lar, kodunuzun daha düzenli olmasını ve bakımının daha kolay hale gelmesini sağlarlar. Değerlerin değiştirilmesi veya eklentiler yapılması gerektiğinde enumeration'ları güncellemek oldukça kolaydır.



### Enumeration'lar Nasıl Tanımlanır?

* Bir enumeration'ı tanımlamak oldukça basittir.

  ```csharp
  enum OrderStatus
  {
      Completed,
      Failed,
      Suspend
  }
  ```

* Burada, enumeration elemanlarının sırasıyla 0'dan başlayarak ardışık bir şekilde, otomatik olarak compiler tarafından numaralandığını bilmeniz şimdilik yeterlidir.

* Tanımlanmış olan enumeration'ı kullanmak daha da basittir.

  ```csharp
  OrderStatus status = OrderStatus.Completed;
  ```

* Görüldüğü üzere enumration elemanlarına erişmek için enum adında nokta dedikten sonra elemanın adını yazmamız yeterlidir.
  Ayrıca bir enumeration'ın değerini metinsel elde etmek istiyorsanız aşağıdaki gibi ToString fonksiyonunu kullanabilirsiniz.

  ```csharp
  string status = OrderStatus.Completed.ToString();
  Console.WriteLine(status);
  ```

* Dersimizin devamında elimizdeki metinsel değerlere karşılık enumeration değerini de elde etmeyi inceleyeceğiz. Şimdilik devam edelim.



#### Enumeration Elemanlarına Sayısal Değer Atama

> Normalde enumeration'lar tanımları an varsayılan olarak ilk elemanda 0'dan başlayarak artan değerlere sahip olurlar.
>
> Ancak istendiği taktirde enumeration'lara özel sayısal değerler atanabilir.

<img src=https://i.imgur.com/IvvJIte.png align=left />



### Enumeration Elemanlarına Erişim Sağlama Yöntemleri

> Esasında enumeration elemanlarına erişim yöntemlerinden esas olanı biraz önce görmüştük.
>
> Yani doğrudan enumeration elemanlarına erişebilmeyi;
>
> ```csharp
> //OrderStatus status = OrderStatus.Completed;
> //-------------------------------------------
> string status = OrderStatus.Completed.ToString();
> Console.WriteLine(status);
> ```

> Bunun dışında, elimizde metinsel değerler üzerinden enumeration elemanına erişmek isteyebiliriz. Bunun için de 'Enum' abstract class'ından aşağıdaki gibi istifade etmemiz gerekmektedir.
>
> ```csharp
> string value = "Suspend";
> Order status = (OrderStatus)Enum.Parse(typeof(OrderStatus),value);
> ```

> Benzer mantıkta elimizdeki sayısal bir değere karşılık enumeration'daki elemana da erişmek isteyebiliriz. Bu durumda da aşağıdaki gibi Casting işlemini yapmamız yeterli olacaktır.
>
> ```csharp
> OrderStatus status0 = (OrderStatus)0;
> OrderStatus status2 = (OrderStatus)2;
> ```

> Ya da var olan bir enumeration içerisindeki tüm elemanlara bir dizi/koleksiyon mantığında ulaşıp, kümülatif işlemler de yapmak isteyebiliriz.
>
> ```csharp
> var items = Enum.GetValues(typeof(OrderStatus));
> foreach (var item in items)
>     Console.WriteLine(item);
> ```



### Enumeration Elemanlarına Metinsel Temsiller Ekleme

Enumeration elemanlarına metinsel temsiller eklemek, enum değerlerinin daha kullanışlı hale gelmesini sağlamaktadır.

Metinsel temsiller, enum değerlerini kullanıcı arayüzlerinde görüntüleme gibi durumlarda oldukça kullanışlıdır.

> Bir enumeration içerisindeki elemanlara metinsel temsil eklemek için aşağıdaki yöntem uygulanabilir.
>
> ```csharp
> using System.ComponenetModel;
> using System.Reflection;
> 
> OrderStatus status = OrderStatus.Completed;
> var description = satatus.GetType()
> 					   .GetField(status.ToString())
> 					   .GetCustomAttribute<DescriptionAttribute>()
> 					   ?.Description;
> Console.WriteLine(description);
> 
> enum OrderStatus
> {
>     [Description("Sipariş Başarılı")]
>     Completed,
>     [Description("Sipariş Başarısız")]
>     Failed,
>     [Description("Sipariş Askıda")]
>     Suspend
> }
> ```



### Enumeration Türünün Sayısal Türle Dönüşümleri

* C#'ta enumeration değerlerini, diğer veri türlerine dönüştürmek yaygın bir ihtiyaçtır.
  Zaten bu veri yapısının temeli sayısal türler olduğu için özellikle enumeration ile sayısal türler arasındaki dönüşüm oldukça önem arz etmektedir.

<img src=https://i.imgur.com/s1z673p.png align=left />



### Enumeration mı, Constant'lar mı?

Enumeration yahut constant string'ler arasında seçim yaparken dikkat edilmesi gereken bazı faktörler vardır.

Şimdi gelin bu faktörleri aşağıdaki bir tablo üzerinden karşılaştıralım.

<img src=https://i.imgur.com/87Sp1Vb.png align=left />



### Enumeration'ların Karmaşık Uygulamalardaki Avantaj ve Dezavantajları

#### Rol ve Avantajları

* **Anlaşılabilirlik ve Bakım Kolaylığı**

  Enumeration'lar, kodun daha anlaşılır ve düzenli olmasını sağlarlar. Değerleri semantik anlamlara sahip olduğu için, kodun okunabilirliğini artırır ve bakım işlemlerini daha kolay hale getirir.

* **Kod Kusurlarını Azaltma**

  Enumeration'lar, geçerli değerler kümesini belirlemek için kullanıldığından, kodun hatalı veya geçersiz değerlerle çalışmasını engeller.

* **Değer Değişiklikleri Yönetimi**

  Eğer değerlerde değişiklik yapmanız gerekirse, enumeration'ları güncellemek oldukça kolaydır. Bu değerlerin birden çok yerde düzeltilmesi ihtiyacını azaltır.

* **Daha İyi Dökümantasyon**

  Enumeration kullanılan kodun dökümante edilmesi, karmaşık değerlerin kullanıldığı kodlara nazaran daha kolay ve izah edilebilirdir.



#### Sınırlamalar ve Dikkat Edilmesi Gerekenler

* **Geniş Enumeration'lar**
  Büyük enumeration değerleri bellek kullanımını artıracağından ve işlevleri yavaşlatacağından performans sorunlarına yol açabilir. O yüzden enumeration'lar sınırlı bir veri kümesini temsil etmek için kullanılmalı, haddinden fazla büyük verilerde tercih edilmemelidir.
* **Arayüz ve Soyut Sınıflarla Entegre Olamama**
  Enumeration'lar, arayüzleri veya abstract class'ları implemente edemezler. Bu durum, bazı tasarım desenlerini veya uygulama yapılarını kullanırken kısıtlamalara yol açabilir.
* **Sabit Değer Kümesi**
  Enumeration'lar, tanımlandıktan sonra dinamik olarak değerlerinin değiştirilmesine izin vermezler. Bu tarz dinamik değişikliklerin olacağı senaryolarda enumeration'lardan ziyade veritabanı yapılarından istifade etmeniz daha elverişli olabilir.



### Flags Attribute'u Nedir? Nasıl Kullanılır?

Bazen bir özelliği tanımlarken, bu tanımlamayı bir enumeration içerisindeki birden fazla elemanla gerçekleştirmemiz iş icabı gerekebilmektedir.

> Misal olarak, aşağıdaki gibi yetkileri ifade eden enumeration'dan değer verirken birden fazla değer verme durumu söz konusu olabilir.
> ```csharp
> enum Permissions
> {
>     Add,
>     Remove,
>     Update,
>     List
> }
> Console.WriteLine(Permission.Update | Permission.Remove);
> ```
>
> Burada görüldüğü üzere enumeration eleman çağırımları arasında '|' operatörü ile bit düzeyinde bir birleştirme yapılmaktadır.
>
> Bu birleştirme neticesinde sağlıklı netice elde edebilmek için enumeration'ın elemanlarına toplamları farklı olabilecek değerler vermemiz gerekecektir. Bunun için 2 üzerin n formülasyonu gayet yeterlidir.

> ```csharp
> Console.WriteLine(Permission.Add | Permission.List);
> 
> [Flags]
> enum Permissions
> {
>     Add = 1,
>     Remove = 2,
>     Update = 4,
>     List = 8
> }
> ```
>
> Dikkat ederseniz, bu şekilde 2 üzeri n formülasyonu ile her hangi bir elemanla diğerinin toplamının sonucu başka bir elemanın değerine karşılık gelmemektedir. Ve ayrıca enumeration'ın Flags attribute'u ile işaretlendiğine dikkatinizi çekerim. Bu attribute ile işaretlendiği ve bu şekilde değer verildiği taktirde bu enumeration'ı aşağıdaki gibi kullanabiliriz.
>
> ```csharp
> Console.WriteLine(Permissions.Update | Permissions.Remove);
> Console.WriteLine(Permissions.Update | Permissions.List);
> ```