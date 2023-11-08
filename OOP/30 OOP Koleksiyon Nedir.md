# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Koleksiyonlar





### Koleksiyon Nedir?

C#'ta koleksiyonlar, tıpkı diziler gibi birden fazla veriyi tek bir değişken içerisinde işlemek ve yönetmek için tutmamızı sağlayan veri yapılarıdır.

Diziler, temel programlama süreçlerinde ihtiyaç doğrultusunda oldukça kullanılan veri yapılarıdır. Ancak, yapıları itibariyle dizilerin getirdiği bir takım sınırlılıklar mevcuttur.

Kod süreçlerinde en çok şikayetçi olduğumuz sınırlılıklardan biri, dizilerin sabit boyutlu olmaları ve tanımlama süreçlerinde bu boyutların bildirilmesi zorunluluğudur. Dizilerin sabit boyutlu olması ve bu boyut yapısının tanımlandıktan sonra değiştirilememesi, ayrıca ihtiyaç doğrultusunda boyutunun arttırılmaması operasyonel süreçlerde sıkıntılara neden olabilmektedir.

Ayrıca, dizilerin boyutunun manuel belirlenmesi, bellek yönetiminin de manuel yapılması anlamına gelmektedir. Bu durum, gereksinimlerin esnek olmadığı durumlarda sorunlar yaratabilir.

Dizilere eleman eklerken veya var olan elemanları silerken index'lerle çalışma zorunluluğu, kodlama sürecini istemsiz bir şekilde karmaşıklaştırabilmektedir.

Koleksiyonlar, dizilerin bu dezavantajlarını gidermek ve daha esnek bir yönetim sağlamak amacıyla C# dilinde sunulan dinamik veri yapılarıdır.



### Koleksiyon Türleri

Koleksiyonlar; davranışları ve farklı senaryolara karşın kullanımlarından yola çıkarak **Generic**, **Non-Generic** ve **Specialized** olmak üzere üçe ayrılmaktadırlar.



#### Generic Koleksiyonlar

Farklı veri türlerini depolayabilen ve tür güvenliği sağlayan koleksiyonlardır. Yani bir generic koleksiyon oluşturulduğunda bu koleksiyonun içerisindeki öğelerin türü, koleksiyonu oluştururken belirtilen türle sınırlı olacaktır.

`System.Collections.Generic`

<img src=https://i.imgur.com/cfUuoB9.png width=45% align=left />

> Generic koleksiyonlar, tip güvenliği sayesinde kod hatası riskini oldukça azaltmakta ve performans açısından da diğer koleksiyonlara nazaran (tek türde çalıştıkları için) daha etkili davranmaktadırlar.



#### Non-Generic Koleksiyonlar

Generic koleksiyonların tip güvenliği olmayan versiyonlarıdır.

`System.Collections`

<img src=https://i.imgur.com/8JvDsi1.png width=45% align=left />

> Non-Generic koleksiyonlar genellikle object türle çalışırlar.



#### Specialized Koleksiyonlar

Özel amaçlı davranış sergileyen ve sadece belirli senaryolara uygun olarak geliştirilen koleksiyonlardır.

`System.Collections.Specialized`

<img src=https://i.imgur.com/2FVB7hK.png width=45% align=left />

> Specialized koleksiyonlar, genellikle özel amaçlarına uygun senaryolarda tercih edildikleri taktirde performanslı ve etkili bir çalışma sunacaktırlar.



### Birkaç Koleksiyonu İnceleyelim

#### List<.T>

C# dilinde en çok tercih edilen koleksiyon yapısıdır.

Generic T parametresi koleksiyonun türünü belirtilen tür olarak ifade edecektir.

Dizilerden farklı olarak boyutu otomatik olarak ayarlanabilmekte ve içerisine dinamik bir şekilde öğe ekleyip, çıkarılabilmektedir.

<img src=https://i.imgur.com/yYdHE7S.png align=left />



#### Dictionary<.Tkey,TValue>

Dictionary koleksiyonu key-value formatında kümülatif veri saklayan bir koleksiyondur.

Key(anahtar) değerleri benzersizdir.

<img src=https://i.imgur.com/vut4dHJ.png align=left>



#### Queue <.T>

C# dilinde, ilk giren ilk çıkar(FIFO-First In First Out) mantığında çalışan koleksiyondur.

Bu koleksiyon, elemanların eklenme sırasına göre işlenmesini sağlamaktadır.
Queue, mantıken bir kuyruk davranışı sergiler.

<img src=https://i.imgur.com/nXNzGQn.png align=left>

> Queue koleksiyonu, genellikle iş parçacığı kuyruklarında, işlemlerin sırasına göre işlenmesi gereken senaryolarda ve verilerin sırasıyla işlendiği diğer durumlarda oldukça kullanışlıdır.
>
> İlk giren ilk çıkar mantığına dayalı olarak çalıştığı için, bu tür senaryolarda verilerin doğru sıra ile işlenmesini sağlar.



#### Stack<.T>

C# dilinde, son giren ilk çıkar(LIFO - Last In First Out) mantığında çalışan koleksiyondur.

Bu koleksiyon da tıpkı Queue koleksiyonunda olduğu gibi, elemanların ekleme sırasına göre işlenmesini sağlamaktadır.
Stack, mantıken bir yığın davranışı sergilemektedir.

<img src=https://i.imgur.com/hssOeLz.png align=left />



#### LinkedList<.T>

LinkedList, verileri birbirlerine bağlı düğümler(node) şeklinde saklamaya olanak tanıyan bir koleksiyondur.

Her düğüm(node), içereceği veriyi ve bir sonraki düğümün referansını içermektedir.

<img src=https://i.imgur.com/6cq0c8n.png align=left />



#### SortedList<.TKey,TValue>

SortedList<.T> koleksiyonu da key-value tarzında veri tutan bir koleksiyondur. Key'ler sıralı bir şekilde tutulmakta ve bu sayede key'lere göre hızlı erişim durumu söz konusu olmaktadır.

SortedList koleksiyonunda key'ler tekildir.

Ayrıca SortedList koleksiyonunda önemli bir nokta da key'leri sıralamak için bir karşılaştırma işlemine ihtiyaç duyulmasıdır.
Eğer koleksiyona eklenen key'lerin sıralanmasını istiyorsanız, bu key'lerin türüne uygun bir karşılaştırıcı belirlemelisiniz.

<img src=https://i.imgur.com/JnP9r4C.png align=left />

Ya da key'e verilen türün default olarak IComparable<.T> interface'ini uygulaması da beklenebilir.

<img src=https://i.imgur.com/D0OS7Jb.png align=left />



#### SortedDictionary<.TKey, TValue>

SortedList<.T> koleksiyonunda olduğu gibi key-value tarzında veri tutan bir koleksiyondur.

SortedList'ten en önemli farkı key'leri sıralamak için bir karşılaştırma işlemine ihtiyaç duymamasıdır.
Bu nedenle key'ler herhangi bir türe uygun olarak eklenip direkt sıralanabilir.

<img src=https://i.imgur.com/qYJGSSx.png align=left />

> SortedDictionary koleksiyon, key'lerin sıralı bir şekilde tutulması istendiği ve özel bir key sıralaması gerekmediği durumlarda kullanılabilir.



#### ObservableCollection<.T>

ObersavleCollection, verilerin eklendiği, çıkarıldığı veya değiştirildiği durumlarda otomatik olarak izleme yapan bir koleksiyondur.

Bu koleksiyon ile verilerde yapılan değişiklikleri 'Event Notifications' denen olay bildirimleriyle takip edebilirsiniz.
Bu notifikasyonlar neticesinde, CollectionChanged event'i tetiklenir.

Bu event sayesinde koleksiyona bağlı olan bileşenlerin otomatik olarak güncellenmesi sağlanabilir.

<img src=https://i.imgur.com/qtFEFH7.png align=left />



#### ArrayList

C#'ın dizilerden koleksiyonlara evrilmenin ilk ara geçiş türüdür.

İçerisinde farklı türlerden değerleri object olarak tutmaktadır. Haliyle verilere boxing işlemini uygulamaktadır.

Boxing'e tabi tutulmuş verileri kendi türlerinde kullanabilmek için unboxing yapılması gerekeceğinden dolayı pek önereceğimiz bir koleksiyon değildir.

<img src=https://i.imgur.com/6odbw6R.png align=left />



#### BitArray

BitArray, 0 ve 1 bitlerini saklayan ve bu bitler üzerinde işlemler yapmamıza imkan tanıyan bir koleksiyondur.

Bu koleksiyon, boolean değerlerin yerine geçen ve bellek kullanımında avantaj sağlayan bir veri yapısıdır.

<img src=https://i.imgur.com/aVKxlUj.png align=left />

<img src=https://i.imgur.com/KwC5Cp8.png align=left />



#### NameValueCollection

NameValueCollection, key-value formatında veri saklayan ve key'leri index'leyen bir koleksiyondur.
Bu koleksiyonda key ve value değerleri direkt string olarak tutulmaktadır.

Genellikle web.config, appsettings.json vs. gibi konfigürasyonel dosyalarda tutulan yapılandırma verilerini kod kısmında karşılamak ya da tutmak için kullanılır.
Bundan dolayı bu koleksiyon içerisinde aynı key'e sahip olan birden çok değer tutulabilir.

<img src=https://i.imgur.com/SL0l3aS.png align=left />



#### StringCollection

StringCollection, string değerleri saklamak ve bu değerler üzerinde kolayca işlem yapmak için kullanılan bir koleksiyondur.

Bu koleksiyon ile key-value formatına gerek kalmaksızın sade ve sadece string değerleri saklayabilirsiniz.
Yani bir nevi string diziler yerine ( string[ ] ) tercih edilen koleksiyondur diyebiliriz.

<img src=https://i.imgur.com/yZjde3R.png align=left />



#### StringDictionary

StringDictionary, sadece string türünden değerleri key-value formatında tutan bir koleksiyondur.
Hashtable koleksiyonunun string'e özel bir türevidir diyebiliriz.

Key değerleri tekil olmalıdır.

Ayrıca Dictionary<.TKey,TValue> koleksiyonu varken bu koleksiyon pek önerilmemektedir!

<img src=https://i.imgur.com/COaT6nL.png align=left />



#### HybridDictionary *

HybridDictionary, birçok key-value formatında değer tutan koleksiyondan biridir. Amma velakin bu diğerlerine nazaran hafızayı daha da iyi bir şekilde yönetmek için optimize edilmiştir.

HybridDictionary, arkaplanda belirli bir eşiğe kadar basit bir dizi kullanmaktadır. O eşik aşıldığı zaman ListDictionary veya Hashtable gibi daha verimli koleksiyonları kullanmaya başlamaktadır.

Böylece, küçük boyutlu koleksiyonlarda düşük bellek tüketimi ve performans avantajı sağlamakta ve büyük boyutlu koleksiyonlarda ise verimliliği korumaktadır.
Ve özellikle orta büyüklükteki koleksiyonlar için ise iyi bir denge sağlamaktadır.

<img src=https://i.imgur.com/uUhlvlm.png align=left />



#### ListDictionary

ListDictionary, düşük miktarda veri için optimize edilmiş olan bir koleksiyondur.

Küçük koleksiyonlar için etkili bir şekilde çalışan davranışa sahiptir. Diğer dictionary türlerindeki hızlı erişim ve arama yeteneklerine nazaran düşük bellek tüketimi ön plandadır.

Ve özellikle düşük veri setleri için optimize edilmiş hafıza kullanımı sunmaktadır.

<img src=https://i.imgur.com/fa6MN2a.png align=left />



#### Indexed Element Initialization

İstenilen index'e değer atanabiliyor.

<img src=https://i.imgur.com/HVPjmbY.png align=left />
