# Entity Framewok Core

## Veri Sorgulama - Temel Düzeyde Sorgulama Yapılanmaları



```csharp
using Microsoft.EntityFrameworkCore;

public class ETicaretContext : DbContext
{
    public DbSet<Urun> Urunler{get;set;}
    public DbSet<Parca> Parcalar{get; set;}
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
    
    public ICollection<Parca> Parcalar {get; set;}
}
public class Parca
{
    public int ID {get; set;}
    public string ParcaAdi {get; set;}
}
ETicaretContext context = new();
```



### En Temel Basit Bir Sorgulama Nasıl Yapılır?

#### Method Syntax

> Sorgulama sürecinde metotlarla mantığı kuruyorsanız, bu method syntax olarak adlandırılmaktadır.

```csharp
var urunler = await context.Urunler.ToListAsync();

```



#### Query Syntax

```csharp
var urunler2 = await (from urun in context.Urunler
    		  select urun).ToListAsync();
```



### Sorguyu Execute Etmek İçin Ne Yapmamız Gerekmektedir?

#### ToListAsync

> Sorguyu execute etmek için kullandığımız bir fonksiyondur.

##### Method Syntax

##### QuerySyntax



#### Foreach

##### Deffered Execution(Ertelenmiş Çalışma)

> IQueryable çalışmalarında ilgili kod yazıldığı noktada tetiklenmez, çalıştırılmaz yani ilgili kod yazıldığı noktada sorguyu generate etmez!
> Çalıştırıldığı/execute edildiği noktada tetiklenir! İşte bu duruma da ertelenmiş çalışma denir!

```csharp
int urunId = 5;
var urunler = from urun in context.Urunler
			 where urun.ID > urunId
			 select urun;
urunId = 200; //IQueryable oluşturulduğu için değişmeyeceğini düşünebiliriz, lakin sorguya dahil edilecektir.
foreach (Urun urun in urunler)
{
    Console.WriteLine(urun.UrunAdi);
}
```



### IQueryable ve IEnumerable Nedir? Basit Olarak!

```csharp
var urunler = from urun in context.Urunler
			 select urun; //IQueryable, sorguya karşılık gelen kısım
```



#### IQueryable

> EF Core üzerinden yapılmış olan sorgunun execute edilmemiş halini ifade eder.

#### IEnumerable

> Sorgunun çalıştırılıp/execute edilip verilerin in memorye yüklenmiş halini ifade eder.