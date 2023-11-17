# Entity Framework Core

## Veri Kalıcılığı | EF Core ile Veri Ekleme Detayları

```csharp
using Microsoft.EntityFrameworkCore;

public class ETicaretContext : DbContext
{
    public DbSet<Urun> Urunler{get;set;}
    protected override void OnConfiguring(DbContextOptionsBuilder optionBuilder)
    {
        optionBuilder.UseSqlServer("Server=.\SQLEXPRESS; Database=ETicaretDB; User ID:sa;Password:1234");
    }
}
public class Urun
{
    public int ID {get; set;}
    public string UrunAdi {get; set;}
    public float Fiyat {get; set;}
}
```



### Veri Nasıl Eklenir?

Eklenecek olan ürünün instance'ını oluşturuyoruz.

```csharp
ETicaretContext context = new();
Urun urun = new()
{
    UrunAdi = "A Ürünü",
    Fiyat = 1000
};
```



#### context.AddAsync Fonksiyonu

```csharp
await context.AddAsync(urun); //object olarak, tip güvensiz veri eklememizi sağlar
```



#### context.DbSet.AddAsync Fonksiyonu

```csharp
await context.Urunler.AddAsync(urun); //Tip güvenli veri eklememizi sağlar
```



### SaveChanges Nedir?

> SaveChanges : insert, update ve delete sorgularını oluşturup bir transaction eşliğinde veritabanına gönderip execute eden fonksiyondur.
>
> Eğer ki oluşturulan sorgulardan herhangi biri başarısız olursa tüm işlemleri geri alır. (rollback)

```csharp
await context.SaveChangesAsync();
```



### EF Core Açısından Bir Verinin Eklenmesi Gerektiği Nasıl Anlaşılıyor?

```csharp
ETicaretContext context = new();
Urun urun = new()
{
    UrunAdi = "B Ürünü",
    Fiyat = 2000
};
Console.WriteLine(context.Entry(urun).State); //Detached
await context.AddAsync(urun);
Console.WriteLine(context.Entry(urun).State); //Added
await context.SaveChangesAsync();
Console.WriteLine(context.Entry(urun).State); //Unchanged
```



### Birden Fazla Veri Eklerken Nelere Dikkat Edilmelidir?

```csharp
ETicaretContext context = new();
Urun urun1 = new()
{
    UrunAdi = "C ürünü",
    Fiyat = 2000
};
Urun urun2 = new()
{
    UrunAdi = "D ürünü",
    Fiyat = 2000
};
Urun urun3 = new()
{
    UrunAdi = "E ürünü",
    Fiyat = 2000
};

await context.AddAsync(urun1);
await context.SaveChangesAsync();
await context.AddAsync(urun2);
await context.SaveChangesAsync();
await context.AddAsync(urun3);
await context.SaveChangesAsync();
```

> Bu şekilde yaptığımız işlemde 3 farklı transaction çalışacaktır, haliyle bu şekilde kullanım verimsizdir.



### SaveChanges'ı Verimli Kullanalım!

> SaveChanges fonksiyonu her tetiklendiğinde bir transaction oluşturacağından dolayı EF Core ile yapılan her bir işleme özel kullanmaktan kaçınmalıyız!
> Çünkü her işleme özel transaction veritabanı açısından ekstradan maliyet demektir. O yüzden mümkün mertebe tüm işlemlerimizi tek bir transaction eşliğinde veritabanına gönderebilmek için savechanges'ı aşağıdaki gibi tek seferde kullanmak hem maliyet hem de yönetilebilirlik açısından katkıda bulunmuş olur.

```csharp
ETicaretContext context = new();
Urun urun1 = new()
{
    UrunAdi = "C ürünü",
    Fiyat = 2000
};
Urun urun2 = new()
{
    UrunAdi = "D ürünü",
    Fiyat = 2000
};
Urun urun3 = new()
{
    UrunAdi = "E ürünü",
    Fiyat = 2000
};

await context.AddAsync(urun1);
await context.AddAsync(urun2);
await context.AddAsync(urun3);
await context.SaveChangesAsync();
```



### AddRange

```csharp
ETicaretContext context = new();
Urun urun1 = new()
{
    UrunAdi = "C ürünü",
    Fiyat = 2000
};
Urun urun2 = new()
{
    UrunAdi = "D ürünü",
    Fiyat = 2000
};
Urun urun3 = new()
{
    UrunAdi = "E ürünü",
    Fiyat = 2000
};
await context.Urunler.AddRangeAsync(urun1,urun2,urun3);
await context.SaveChangesAsync();
```



### Eklenen Verinin Generate Edilen Id'sini Elde Etme

```csharp
ETicaretContext context = new();
Urun urun = new()
{
    UrunAdi = "O ürünü",
    Fiyat = 2000
};
await context.AddAsync(urun);
await context.SaveChangesAsync();
Console.WriteLine(urun.ID);
```