# C# Notları (Koleksiyon Yapıları)

[TOC]



## Koleksiyonlar

### Koleksiyonlar Nelerdir? Diziler Varken Neden Koleksiyon Yapıları İnşa Edilmiştir?

> Dizilerdeki sınırlılıklar:
>
> * Dizilerde tanımlama yaparken eleman sayısının bildirilmesi zorunluluğu bir sınırlılıktır.
> * Diziler tanımlandığında kullansakta kullanmasakta bellekte belirtilen eleman sayısı kadar alan tahsisinde bulunurlar. Bu durum bellek boyutunda ekstradan maliyete sebep olacağı için bir sınırlılıktır.
> * Dizilerde eleman sayısının başta belirlenmesi durumunda, ihtiyaca binaen daha fazla değer atamak istediğimizde bu değerleri atayamayacağımız ve dizinin aralığını genişletemeyeceğimizden dolayı bu durum bir sınırlılık olarak karşımıza çıkmaktadır.
> * Tanımlanmış bir dizide elemanlara değer atarken [ ] indexer operatörüyle değer atanması bir sınırlılıktır.

Dizilerle koleksiyonların amacı aynı, birden fazla veriyi yönetmek. Dizilerde sınırlılıklarımız vardı, "bu sınırlılıkları ortadan kaldırmak için üretilmiştir" diyelim.



> Koleksiyonların dizilerden farklı bazı özellikleri ve avantajları şunlardır :
>
> 1. Boyut Esnekliği: Dizilerin boyutları oluşturulduktan sonra genellikle sabittir. Koleksiyonlar ise dinamik olarak boyutlandırılabilir, eleman eklendiğinde veya çıkarıldığında boyutları otomatik olarak ayarlanabilir.
> 2. Veri Ekleme ve Çıkarma Kolaylığı: Koleksiyonlar, veri eklemek, çıkarmak veya düzenlemek için çeşitli yöntemler ve işlevler sağlar. Bu, programcılara esneklik ve kolaylık sağlar.
> 3. Fonksiyonellik Farklılığı: Koleksiyonlar, özel gereksinimlere yönelik farklı fonksiyonelliklere sahip olabilir. Örneğin, List<T> dizilere benzeyebilirken, Stack<T>, Queue<T>, Dictionary<K, V> gibi farklı koleksiyon türleri farklı amaçlara hizmet edebilir.
> 4. Performans ve İşlem Farklılığı: Bazı durumlarda, koleksiyonlar belirli işlemlerde dizilere kıyasla daha etkin olabilir. Örneğin, bir List<T> kullanarak dinamik boyutlanabilir bir yapı oluşturmak, dizilerle karşılaştırıldığında daha fazla işlem kolaylığı sağlayabilir.



## ArrayList

### ArrayList Koleksiyonu Tanımlama

```csharp
//Diziler tanımlanırken kaç eleman tutacakları bildirilmek zorundadır.
int[] yaslar = new int[10]; //Dizi
ArrayList _yaslar = new ArrayList();//Koleksiyon
```



### ArrayList Koleksiyonu Değer Atama

```csharp
//Dizilerde indexer ile belirtilerek atama yapılırken, koleksiyonların genel çoğunluğunda Add() fonksiyonu üzerinden gerçekleştirilir.
yaslar[5] = 123;
_yaslar.Add(123);
```



### ArrayList Koleksiyonu Değer Okuma

```csharp
int[] yaslar = new int[17];
ArrayList _yaslar = new ArrayList();

for (int i = 0; i < 17; i++)
{
    yaslar[i] = i + 10;
    _yaslar.Add(i + 10);
}
//Diziler
Console.WriteLine(yaslar[5]);
//Koleksiyonlar
Console.WriteLine(_yaslar[5]);
```



### ArrayList Kullanılırken Boxing-Unboxing Durumları

> ArrayList, verilen datayı boxing işlemine tabii tutar.
> ArrayList içerisindeki herhangi bir veriyi talep ettiğimizde o veri object olarak gelecektir. Dolayısıyla kendi türünde işlem yapabilmek için unboxing işlemine tabii tutmamız gerekir.

```csharp
ArrayList _yaslar = new ArrayList();
//...
int toplam = 0;
for (int i = 0; i < _yaslar.Count; i++)
{
    toplam += (int)_yaslar[i]; //Unboxing
}
```



### ArrayList Collection Initializers(Koleyksiyon İlklendirici) İle Değer Ekleme

```csharp
ArrayList arrayList = new ArrayList(){
"Ahmet",
123,
true //Object türde tutulduğu için farklı türdeki değerleri de içerebilir.
};
```

