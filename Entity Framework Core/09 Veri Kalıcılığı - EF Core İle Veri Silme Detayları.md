# Entity Framework Core

## Veri Kalıcılığı | EF Core ile Veri Silme Detayları



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



### Veri Nasıl Silinir?

```csharp
ETicaretContext context = new();
Urun urun = await context.Urunler.FirstOrDefaultAsync(u => u.ID == 5);
context.Urunler.Remove(urun);
await context.SaveChangesAsync();
```



### Silme İşleminde ChangeTracker'ın Rolü

> ChangeTracker, context üzerinden gelen verilerin takibinden sorumlu bir mekanizmadır. Bu takip mekanizması sayesinde context üzerinden gelen verilerle ilgili işlemler neticesinde update yahut delete sorgularının oluşturulacağı anlaşılır!



### Takip Edilmeyen Nesneler Nasıl Silinir?

```csharp
ETicaretContext context = new();
Urun u = new()
{
    ID = 2
};
context.Urunler.Remove(u);
await context.SaveChangesAsync();
```



### EntityState İle Silme İşlemi

```csharp
Urun u = new() { ID = 1};
context.Entry(u).State = EntityState.Deleted;
await context.SaveChangesAsync();
```



### Birden fazla Veri Silinirken Nelere Dikkat Edilmelidir?

#### SaveChanges'ı Verimli Kullanalım

> SaveChanges fonksiyonu her tetiklendiğinde bir transaction oluşturacağından dolayı EF Core ile yapılan her bir işleme özel kullanmaktan kaçınmalıyız!
> Çünkü her işleme özel transaction veritabanı açısından ekstradan maliyet demektir.

#### RemoveRange

```csharp
ETicaretContext context = new();
List<Urun> urunler = await context.Urunler.Where(u => u.ID >= 7 && u.ID <= 9).ToListAsync();
context.Urunler.RemoveRange(urunler);
await context.SaveChangesAsync();
```

