# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Sınıf Modeline Özel Keyword'ler : this | base | readonly

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/22-QR.png width=10% alt="İlgili Video İçeriği QR" />

> Hatırlatma: 
> this kewrod'ü:
>
> 1. Bir sınıfın, uygulamanın herhangi bir noktasında üretilmiş olan instance'larını/object'lerini/nesnelerini sınıf içerisinde temsil etmemizi sağlayan bir keyword'dür.
>
> 2. Bir sınıf içerisinde bulunan birden fazla constructor overload'ı arasında zıplamamızı / atlamamızı sağlayan bir keyword'dür.

> Hatırlatma:
>
> base keyword'ü:
>
> 1. Bir instance'ın base class'ını sınıf modeli içerisinde temsil eden bir keyword'dür.
>
> 2. Base class'daki constructor'lardan seçim yapmamızı sağlar.

### readonly Keyword'ü

Bir class içerisinde tanımlanmış olan değişkenin yahut referansın sadece okunabilir olmasını sağlayan bir keyword'dür.

readonly keyword'ü ile işaretlenmiş olan referansların değerleri ya tanımlama noktasında ya da constructor'da verilebilir.

> const yapılanmalar, readyonly ile karıştırılabilir. Aralarındaki fark şöyledir:
> const tanımlandığı yerde değeri verilmelidir. Ve constructor içerisinde bile değer ataması gerçekleştirilemez!
>
> Lakin readyonly'de ister tanımlarken, isterseniz de constructor içerisinde değer ataması gerçekleştirilebilir.

