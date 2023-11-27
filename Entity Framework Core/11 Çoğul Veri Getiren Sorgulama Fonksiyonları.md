# Entity Framewok Core

## Çoğul Veri Getiren Sorgulama Fonksiyonları



### ToListAsync

> ToListAsync: Üretilen sorguyu execute ettirmemizi sağlayan fonksiyondur.

#### Method Syntax

```csharp
var urunler = context.Urunler.ToListAsync();
```

#### Query Syntax

```csharp
var urunler = from urun in context.Urunler
			 select urun;
var datas = await urunler.ToListAsync();
```



###  Where

> Where : Oluşturulan sorguya where şartı eklememizi sağlayan bir fonksiyondur.

#### Method Syntax

```csharp
var urunler = await context.Urunler.Where(u => u.Id > 500).ToListAsync();
```

#### Query Syntax

```csharp
var urunler = from urun in context.Urunler
			 where urun.Id > 500 && urun.UrunAdi.EndsWith("7")
			 select urun;
var datas = await urunler.ToListAsync();
```



###  OrderBy

> OrderBy : Sorgu üzerinde sıralama yapmamızı sağlayan bir fonksiyondur. (Ascending)

#### Method Syntax

```csharp
var urunler = context.Urunler.Where(u => u.Id > 500 || u.UrunAdi.EndsWith("2")).OrderBy(u => u.UrunAdi).ToListAsync();
```

#### Query Syntax

```csharp
var urunler = from urun in context.Urunler
			 where urun.Id > 500 || urun.UrunAdi.StartsWith("2")
			 orderby urun.UrunAdi ascending//ascending default olarak kabul edilir.
			 select urun;
var datas = await urunler.ToListAsync();
```



### ThenBy

> ThenBy : OrderBy üzerinde yapılan sıralama işlemini farklı kolonlara da uygulamamızı sağlayan bir fonksiyondur. (Ascending)

```csharp
var urunler = context.Urunler.Where(u => u.Id > 500 || u.UrunAdi.EndsWith("2")).OrderBy(u => u.UrunAdi).ThenBy(u => u.Fiyat).ThenBy(u => u.Id);
```



### OrderByDescending

> OrderByDescending : Descending olarak sıralama yapmamızı sağlayan bir fonksiyondur.

#### Method Syntax

```csharp
var urunler = await context.Urunler.OrderByDescending(u => u.Fiyat).ToListAsync();
```

#### Query Syntax

```csharp
var urunler = await (from urun in context.Urunler
                     orderby urun.UrunAdi descending
                     select urun).ToListAsync();
```



### ThenByDescending

> ThenByDescending : OrderByDescending üzerinde yapılan sıralama işlemini farklı kolonlara da uygulamamızı sağlayan bir fonksiyondur. (Ascending)

```csharp
var urunler = await context.Urunler.OrderByDescending(u => u.Id).ThenByDescending(u => u.Fiyat).ThenBy(u => u.UrunAdi).ToListAsync();
```