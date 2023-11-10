# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Anonymous Type



### Anonymous Type Nedir?

Kodlama süreçlerinde bazen öyle nesnelere ihtiyacımız olur ki, o nesneyi, model olarak sade ve sadece o anın dışında başka bir yerde kullanma ihtiyacı hissetmeyiz.
Haliyle böyle durumlarda tek bir an için lazım olan bir nesnenin class modellemesini üretmek sizce ne kadar mantıklı olacaktır?
Düşünürsek eğer, her böyle ihtiyaç olduğunda bir class modellemesi yaparsak eğer, bir noktadan sonra projemizin içeriği tekil kullanımlık class'lardan oluşan çöpe dönmeyecek mi?

İşte böyle durumlar için C# programlama dilinde anonymous type adı verilen nesneler üretilmiştir. Bu nesneler, adı ve modellemesi tarafımızca yapılmaya gerek duyulmaksızın pratik bir şekilde o anda üretilebilen nesnelerdir!

```csharp
var anonymousInstance = new
{
    ExampleProperty1 = "....",
    ExampleProperty2 = 123,
    ExampleProperty3 = !false,
    ExampleProperty4 = 'o',
};
```

> Görüldüğü üzere anonymous type olan bir nesneyi bu şekilde oluşturabiliyor ve direkt içerisine opsiyonel bir şekilde property tanımlamasında bulunabiliyoruz.
>
> Burada tanımlanan propertyler read-only olarak oluşturulmakta ve verilen değerin türüne bürünmektedir!

* C#'ta her nesnenin bir türü vardır! Yani her nesnenin türü belirli bir sınıf modeline dayanır. Anonymous Type nesneler ise isimsiz olsalar dahi esasında türsüz nesneler değildir! Bu nesnelerin türleri bizler tarafından değil, compiler tarafından belirlenmektedir. Ama o anda rastgele belirlemektedir.
* Yani anlayacağınız anonymous nesneler türsüz nesneler değil, derleyici tarafından otomatik olarak belirlenen ve programcının doğrudan erişemeyeceği türden nesnelerdir!
* O yüzden anonymous nesneleri var keyword'ü ile refere etmek mecburiyetindeyiz. Çünkü bizler türünü bilememekte ve doğal olarak erişememekteyiz.

> Örnek :
> ```csharp
> var person = new
> {
>     Name = "Mustafa",
>     Surname = "Kurt"
> };
> 
> Console.WriteLine(person.GetType().FullName);
> ```



### Anonymous Type Neden Kullanılır?

Anonymous Type'lar, bildiğiniz <u>geçici veri yapılarını</u> tanımlamamızı sağlayan kullanışlı bir özelliktir. Özellikle LINQ sorguları gibi veri işleme işlemleri sürecinde sonuçları geçici olarak tutmak ve dönüştürmek için biçilmiş kaftandırlar.

Anonymous Type'lar, belirli bir sınıfa ihtiyaç olmadığı durumlarda veyahut birkaç özelliği geçici olarak taşımamız gerekiyorsa hızlı çözüm sunmaktadırlar.
Böylece <u>veri aktarım süreçlerini kolaylaştırıcı</u> etkisi vardır.

Anonymous Type'lar, bir kereye mahsus kullanılacak veya hızlıca bir veri dönüşü sağlanacak durumlarda <u>tek seferlik tür</u> niyetiyle kullanılabilir.

> Genellikle LINQ sorguları veya bazı veri geçişleri için tercih edilebilir.
>
> ```csharp
> await _context.Persons.Include(f => f.Orders)
>     				.ThenInclude(b => b.OrderDetails)
>     				.Where(b => b.Id == 3)
>     				.Select(p => new
>                       {
>                           p.Name,
>                           p.Orders
>                       })
>     				.ToListAsync();
> ```



### Anonymous Type Kullanırken Dikkat Edilmesi Gerekenler

Anonymous Type'ın kullanıldığı senaryolarda, compiler tarafından üretilen türe programcı tarafından doğrudan erişmek mümkün olmayacağından, uzun ömürlü ve daha geniş kullanımlı nesnelere ihtiyaç olduğu durumlarda normal(isimlendirilmiş) sınıfları kullanmanızı tavsiye ederiz.

Anonymous type'lar read-ony olduğundan dolayı property'lerin değerleri oluşturulduktan sonra değiştirilemezler! Bu yüzden kullanım durumlarına göre iyi değerlendirilip tercih edilmelidirler.



### Anonymous Type'da Read-Only Property'lerin Avantajları ve Dezavantajları Nelerdir?

<u>Avantajlar :</u>

* Anonymous type'ların property'lerinin read-only olması, değer oluşturulduktan sonra değiştirilemez oldukları anlamına gelmektedir. Bu da güvenirliliği sağlayacaktır.
* Read-only property'ler, kod sürecinde değişmemesi gereken değerlerin yanlışlıkla değiştirilmesinin önüne geçmekte ve böylece olası hatalara karşı sizle beraber programı korumaktadırlar.
* Anonymous typle'lardaki read-only property'ler, asenkron süreçlerde ek güvenlik sağlamakta ve birden fazla thread tarafından kullanıldıklarında kontrolsüz değer değişikliklerini mümkün kılmamaktadır.



<u>Dezavantajlar :</u>

* Property'lerin read-only olması durumunda, program akışı sürecinde gerektiği yerlerde değer değiştirebilme olanağından yoksun kalınmasına sebebiyet verecektir.
* Anonymous type'ların read-only olması bir yandan da ihtiyaç doğrultusunda yeni özellik eklemek ya da var olan özelliği kaldırmak gibi davranışları desteklememektedir. Böylece bu tür ihtiyaçları karşılama yetenekleri anonymous type'lar da kısıtlanmaktadır.
* Anonymous type'ların read-only olması, unit test süreçlerinde verilerin manipülasyonunu zorlaştırabilmektedir.



> Genel olarak, read-only property'ler anonymous type'ların daha güvenli ve değişmez ve hatalara karşı daha sağlam olmasını sağlamaktadır.
>
> Ancak bu özellik ihtiyaçlarınıza ve projenin gereksinimlerine bağlı olarak avantaj yahut dezavantaj sergileyebilir.
> Eğer daha sonra özellik değerlerini değiştirme ihtimali düşük ve güvenlik önemliyse, read-only property'ler kullanmanız elbet yararlı olacaktır.
> Ancak fazla esneklik ve değişkenlik gerektiren durumlarda normal sınıfların nesnelerini tercih etmeniz daha mantıklı olabilir.



### Anonymous Type Olan Nesnelerin Faaliyet Alanları

Anonymous Type'lar, sadece tanımlandıkları metotun kapsamında kullanılırlar. Haliyle anlayacağınız, tanımlandıkları metotun kapsamı dışına çıkamazlar!
Bu da ilgili nesnelerin diğer metotlara parametre vs. olarak taşınması mümkün değildir, anlamına gelir.

Anonymous type olarak tanımlanmış bir nesneyi, tanımlandığı scope'un dışında başka bir yere aktarmak istiyorsanız **dynamic** türünden aşağıdaki gibi istifade edebilirsiniz.

```csharp
var anonymousInstance = new
{
    ExampleProp1 = "....",
    ExampleProp2 = 123,
    ExampleProp3 = !false,
    ExampleProp4 = 'o',
};

Anonymous(anonymousInstance);

void Anonymous(dynamic instance)
{
    Console.WriteLine(instance.ExampleProp1);
    Console.WriteLine(instance.ExampleProp2);
    Console.WriteLine(instance.ExampleProp3);
    Console.WriteLine(instance.ExampleProp4);
}
```