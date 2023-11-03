# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Abstraction (Soyutlama)



### Abstraction Kavramı Nedir?

> Abstraction bir mantıktır! Bir davranıştır.

> Düşünsel süreç:
>
> * Kullanıcı işlemlerinden sorumlu olan bir sınıf düşünelim.
>
> ```csharp
> class UserService
> {
>     public void CreateUser(UserInfo userInfo)
>     {
>         //...
>     }
>     public void RemoveUser(int userId)
>     {
>         //...
>     }
>     public List<User> Users{get; set;}
>     public bool ValidateUser(UserInfo userInfo)
>     {
>         //...
>     }
> }
> ```
>
> * Bu sınıfı kullanarak bir kullanıcı doğrulaması gerçekleştirmek istediğimizi varsayalım.
> * Bu işlem için ilgili sınıftan üretilen instance'a ihtiyacımız olduğu aşikar.
> * Kullanıcı doğrulaması yapmak istiyoruz ama doğrulama işleminin dışında bu sınıftaki kullanıcı işlemlerine dair tüm member'lar karşımızda...
>
> <img src =https://i.imgur.com/4ZY25Ez.png width=30% align=left />
>
> * Sizce, kullanıcı doğrulaması yapmak istediğimiz bir anda doğrulama işleminin dışındaki member'ların gelmesi ne kadar sağlıklıdır?
> * Ne de olsa kullanıcı burada doğrulama işlemi yapacaksa, sadece doğrulamaya dair member'lara erişebilmesi en ideali olsa gerek...
>
> - Yani bu durumu şöyle de düşünebiliriz. Bir tesisatçının iş yaparken o anda ihtiyacı olan aletlerin dışındakileri gözünün önünden kaldırması işini kolaylaştıracaktır.
>
>   İngiliz anahtarı ve penseyle çalışacağı yerlerde, elinin altında türlü türlü aletlerin olması iş konsantrasyonunu negatif etkileyecektir.
>
> * Aynı mantık yazılımcılar için de söz konusudur. O anda ihtiyaç dışı member'ların arasından yapılacak işe odaklı member'ları ayırt etmek yazılımcılar açısından sıkıntılı bir durumdur.
>
>   Ki yazılımcı ister istemez yanlış metodu seçebilir yahut konuyla alakasız member'lar konsantrasyonunu bozabilir.
>
> İşte bu tarz durumlara karşın, kodun daha idealize olması için göstereceğimiz davranışa Abstraction denmektedir.



### Abstraction'ın Özeti Nedir?

> Gerekli olanları göster, gereksiz olanları gösterme!

Abstraction, bir sınıfın member'larından ihtiyaç doğrultusunda alakalı olanları gösterip, alakalı olmayanları göstermemek demek oluyor.



### Abstraction Nasıl Uygulanır?

> Abstraction'ın interface'ler yahut abstract class'larla doğrudan hiçbir ilgilisi alakası yoktur!

* Bir operasyon anında, kullanılacak sınıfın sadece o anki operasyona uygun member'larını getirebilmek için (yani abstraction'ı uygulayabilmek için) ilgili member'ları temsil edebilecek bir referansa ihtiyacımız olacaktır.
* Bunu normal sınıflarla öyle ya da böyle gerçekleştirebiliriz, lakin bu davranışı uygularken sadece interface'ler yahut abstract class'lar diğer yapılara göre daha elverişli olabilmektedirler.
* Hele hele sınıfların birden fazla interface ile implement edebilmeleri, ilgili sınıfın birden fazla referansla refere edilebilmesi anlamına geleceğinden dolayı, interface'lerin abstraction işlemi için oldukça yaygın olarak kullanılan yapılar olduğunu düşünebiliriz.

```csharp
interface IUserValidateService
{
    Bool ValidateUser(UserInfo userInfo);
}
interface IUserProcessService
{
    void CreateUser(UserInfo userInfo);
    void RemoveUser(int userId);
    List<User> Users{get; set;}
}
class UserService : IUserValidate,IUserProcessService
{
    public void CreateUser(UserInfo userInfo)
    {
        //..
    }
    public void RemoveUser(int userId)
    {
        //..
    }
    public List<User> Users {get; set;}
    public bool ValidateUser(UserInfo userInfo)
    {
        //..
    }
}
```

<img src=https://i.imgur.com/HA2e7hV.png width=65% align=left />

* Görüldüğü üzere 'UserService' sınıfı içerisindeki member'lar ihtiyaca binaen interface referansları aracılığıyla ayrıştırılabilmekte ve abstraction davranışı böylece gerçekleştirilebilmektedir.
* İşte bu mantıkta olayı değerlendirdiğimizde abstraction davranışı için interface'leri veya abstract class'ları kullanıyoruz. Aksi taktirde bu davranış akla direkt interface ve abstract class getirmektedir ki, yanlıştır!
* *Bir de dikkat ederseniz eğer abstraction davranışı; member'ları ayıkladığı/gizlediği için 'encapsulation', kalıtımsal işlem gerektirdiği için 'inheritance' ve farklı referanslar kullandırdığı için 'polimorfizm' kavramlarıyla doğrudan bağlantılı bir davranıştır.*



### Abstraction'ın Etkisi Nedir?

> Nasıl yaptı bilmiyorum, sadece yapabildiğini biliyorum...

* Abstraction davranışının uygulandığı noktalarda, ilgili nesnenin işlevi nasıl yaptığından öte, ne yaptığıyla ilgilendiğimizi ifade etmiş oluyoruz.
* Bunu da genellikle interface'ler kullanılarak bu davranışı gerçekleştirdiğimizden dolayı söyleyebiliriz.
* İlgili interface, bizlere refere ettiği instance'daki o niteliği imza olarak söylemekte ama nasıl bir işlevsellik gösterdiğine dair bilgi vermemektedir.
* Dolayısıyla abstraction, nesnenin işleri nasıl yaptığını değil, hangi görevleri yapabileceğini söylememizi sağlamaktadır.

> Yani; X, Y ve Z davranışlarına sahip olan bir sınıfın, abstraction ile sadece Y member'ı erişilebilir hale getiriliyorsa, bu durumda kesinlikle bu sınıfta Y davranışının olduğu garanti ediliyor anlamına gelmektedir.



### Abstraction'ın Ana Hedefi Nedir?

> Bir nesnenin yalnızca o anki duruma göre ilgili davranışları gösterilmekte, gereksiz ayrıntıları gizlenmektedir.
>
> Abstraction'ın amacı, geliştiriciden bir sınıfa karşın olabilecek gereksiz ayrıntıları gizleyerek karmaşıklığın üstesinden gelmektir.
>
> O sınıftan üretilmiş bir instance'ı kullanırken o instance'ın sadece ne yapabileceğini göstermek lakin nasıl yapabileceği hakkında bilgi vermemektedir.
>
> Ayrıca yerine göre uygulama ayrıntılarını gizleyerek sadece ilgili davranışların erişilebilir olmasını sağlamakta abstraction'ın bir hedefidir diyebiliriz.



### Abstraction'a Örnek Senaryolar Verelim

> Abstraction, hayatın içinden bir davranıştır.

* Amazon hesabına giriş sürecinde kullanılacak bir nesneyi düşünürsek, eğer bu nesnenin o anda bizlerden sadece username ve password'ü alacak metoduna erişebilmemiz ve diğer konudan alakasız metotlarına erişmememiz bir abstraction davranışı neticesidir.
* Bir araba esasında birçok parçanın bir araya gelerek bütünsel olarak işlemesi neticesinde işlevsellik göstermektedir. Lakin şoför için araba sadece bir arabadır, yani şoför açısından arabanın motorunda dönen tüm fiziksel kurallar soyutlanmıştır. Şoför arabanın nasıl çalıştığını bilemeyebilir lakin çalıştığını bilir. İşte bu abstraction'dır.
* Evlerimizdeki prizler ve o prizlere takılan fişler arasında bir abstraction durumu söz konusudur. Bir prizi görevi kendisine takılan fiş üzerinden ilgili cihazlara elektrik göndermektir. Tabi bir prize birden çok fiş takılabilir, lakin priz hangi cihaza bağlı olduğunu asla bilmez. Burada priz açısından elektrik göndereceği cihazın detayları fiş sayesinde soyutlanmıştır. Priz sadece kendisine takılacak fişi bilir. Belki bu akla dependency inversion prensibini de getirebilir :)
  Doğrudur, bir yandan da bir abstraction örneğidir...
* Sabahları uyandığımızda ayılmak için genellikle kahve içeriz. Mutfağa gidip kahve makinesinin düğmesine basarız ve kahveyi yaparız. Bunu yapaabilmek için kahve makinesinin nasıl kullanılacağını bilmenin dışında su ve kahve çeğirdeği koymamız yeterli olacaktır. Bunların dışında; suyun ideal sıcaklığı, öğütülmüş kahve miktarı, makineyi çalıştırması için gerekli elektrik voltajı vs. gibi ekstradan bilgilere ihtiyacımız muhtemelen olmayacaktır.
  Bir kişi, kahve yapabilmek için gerekli olan tüm bu kaygıları ortadan kaldırabilmek için kahve makinesini yapmıştır. Böylece sizlerin kahve yapma sürecinde uygulayabileceğiniz davranışlar gereksiz detaylardan soyutlanmıştır.



