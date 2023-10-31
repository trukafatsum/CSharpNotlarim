# C# Notları (Hazır Sınıflar ve Fonksiyonlar)

[TOC]



## Math Sınıfı

### Abs Fonksiyonu

> Abs : Mutlak değer ve sonucu parametre içerisinde bildirilen türe pozitif döndürür.

```csharp
int i = Math.Abs(-5); // Çıktı : 5
```



### Ceiling Fonksiyonu

> Ceiling : Ondalıklı değeri yukarıya yuvarlar.

```csharp
int i = Math.Ceiling(3.14); // Çıktı : 4
```



### Floor Fonksiyonu

> Floor : Ondalıklı değeri aşağıya yuvarlar.

```csharp
int i = Math.Floor(3.14); // Çıktı : 3
```



### Round Fonksiyonu

> Round : Ondalıklı değeri en yakın olan tamsayıya yuvarlar.

```csharp
Console.WriteLine(Math.Round(3.4)); // 3
Console.WriteLine(Math.Round(3.5)); // 4 : Birşeyin yarısı tamamına genellenebilir.
Console.WriteLine(Math.Round(3.6)); // 4
```



### Pow Fonksiyonu

> Pow : Değerin üssünü almamızı sağlar.

```csharp
//Console.WriteLine(Math.Pow(x,y)); xᵞ
Console.WriteLine(Math.Pow(7,9));
```



### Sqrt Fonksiyonu

> Sqrt : Karekök fonksiyonu, elimizdeki değerin karekökünü almamızı sağlar.

```csharp
Console.WriteLine(Math.Sqrt(4));
Console.WriteLine(Math.Sqrt(25));
Console.WriteLine(Math.Sqrt(121));
Console.WriteLine(Math.Sqrt(55));
```



### Truncate Fonksiyonu

> Truncate : Elimizdeki değerin yuvarlama yapmadan tam sayı değerini elde etmemizi sağlar.

```csharp
Console.WriteLine(Math.Truncate(3.14));
```



## DateTime Struct'ı

### Now Özelliği

> Now : Çalıştığı işletim sisteminin tetiklendiği andaki tarih zaman dilimini döndüren property'dir.

```csharp
Console.WriteLine(DateTime.Now);
```



### Today Özelliği

> Today : Çalıştığı işletim sisteminin tetiklendiği andaki tarih bilgisini döndüren property'dir.

```csharp
Console.WriteLine(DateTime.Today);
```



### Compare Fonksiyonu

> Compare : İki tarihsel zaman arasında karşılaştırma yapmamızı sağlayan fonksiyondur.
>
> Geriye int türünde değer döndürür. -1 0 1

```csharp
DateTime tarih1 = new DateTime(2021, 01, 01);
DateTime tarih2 = new DateTime(2023, 10, 28);
int result = Datetime.Compare(tarih1,tarih2);
if (result < 0)
{
    Console.WriteLine($"{tarih1} küçüktür {tarih2}");
}
else if (result == 0)
{
    Console.WriteLine($"{tarih1} eşittir {tarih2}")
}
else
    Console.WriteLine($"{tarih1} büyüktür {tarih2}");
```



### Tarihsel Zamana Saat, Gün, Ay,Yıl Ekleyerek Sonucu Hesaplama

> AddDays, AddHours, AddMonths, AddMiliseconds vs..

```csharp
Console.WriteLine(DateTime.Now.AddSeconds(999));
Console.WriteLine(DateTime.Now.AddMonths(999));
Console.WriteLine(DateTime.Now.AddDays(999));
```



## TimeSpan Struct'ı

### TimeSpan Türü ile İki Tarih Farkının Karşılanması

```csharp
DateTime t1 = DateTime.Now;
DateTime t2 = new DateTime(2000, 1, 1);
TimeSpan span = t1 - t2;
Console.WriteLine(span.Days);
Console.WriteLine(span.Minutes);
```



## Random Sınıfı

> Rastgele sayısal değer oluşturmamızı sağlayan bir sınıftır.

### Next Fonksiyonu

```csharp
Console.WriteLine(random.Next()); //0 - ....
Console.WriteLine(random.Next(100)); //0 - 100
Console.WriteLine(random.Next(50,100)); //50 - 100
//Belirtilen maximum değer bu aralığa dahil değildir yani üretilecek olan değer 0 ile 99 arasında olacaktır.
//Negatif değer üretmeyecektir.
```



### NextDouble Fonksiyonu

> 0 ile 1 arasında rastgele değer üretir.

```csharp
Console.WriteLine(random.NextDouble());
```

