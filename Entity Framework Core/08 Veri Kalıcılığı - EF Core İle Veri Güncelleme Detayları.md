# Entity Framework Core

## Veri Kalıcılığı | EF Core ile Veri Güncelleme Detayları



### Veri Nasıl Güncellenir?

```csharp
using Microsoft.EntityFrameworkCore;

ETicaretContext context = new();
Urun urun = await context.Urunler.FirstOrDefaultAsync(u => u.ID == 3);
urun.UrunAdi = "H Ürünü";
urun.Fiyat = 999;

await context.SaveChangesAsync();


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



### ChangeTracker Nedir? Kısaca!

> ChangeTracker : context üzerinden gelen verilerin takibinden sorumlu bir mekanizmadır.
> Bu takip mekanizması sayesinde context üzerinden gelen verilerle ilgili işlemler neticesinde update yahut delete sorgularının oluşturulacağı anlaşılır.



### Takip Edilmeyen Nesneler Nasıl Güncellenir?

```csharp
ETicaretContext context = new();
Urun urun = new()
{
    ID = 3,
    UrunAdi = "Yeni Ürün",
    Fiyat = 123
};
//Update fonksiyonu, ChangeTracker mekanizması tarafından takip edilmeyen nesnelerin güncellenebilmesi için kullanılır.
//Update fonksiyonunu kullanabilmek için kesinlikle ilgili nesnede ID değeri verilmelidir!
context.Urunler.Update(urun);
await context.SaveChangesAsync();
```



### EntityState Nedir?

> Bir entity instance'ının durumunu ifade eden bir referanstır.

```csharp
ETicaretContext context = new();
Urun u = new();
Console.WriteLine(context.Entry(u).State);
```



### EF Core Açısından Bir Verinin Güncellenmesi Gerektiği Nasıl Anlaşılıyor?

```csharp
ETicaretContext context = new();
Urun urun = await.context.Urunler.FirstOrDefault(u => u.ID == 3);
Console.WriteLine(context.Entry(urun).State); //Unchanged : veritabanından geldi herhangi bir değişiklik yok

urun.UrunAdi = "Hilmi";
Console.WriteLine(context.Entry(urun).State); //Modified : güncellemeye hazırlandı

await context.SaveChangesAsync();
Console.WriteLine(context.Entry(urun).State); //Unchanged

urun.Fiyat = 999;
Console.WriteLine(context.Entry(urun).State); //Modified
```



### Birden Fazla Veri Güncellenirken Nelere Dikkat Edilmelidir?

```csharp
ETicaretContext context = new();
var urunler = await context.Urunler.ToListAsync();
foreach (var urun in urunler)
{
    urun.UrunAdi += "*";
    //await context.SaveChangesAsync(); //Her ürün için transaction oluşturulması maliyetlidir.
}
await context.SaveChangesAsync(); //Bu şekilde tek bir transaction altında tüm değişiklikleri işlemek daha verimlidir.
```