# C# Notları (Foreach Iterasyonu)

[TOC]



## Iterasyon Nedir?

> İtere etmek, fiilinden gelmektedir.

* Mantıksal açıdan her tahminin altında bir iterasyon mantığı yatar.

  1,3,5... dedikten sonra 7'nin aklınıza gelmesi itere etmektir.

  f(5) = 10

  f(10) = 20

  f(15) = 30

  f(100) = ? dediğimizde bunun cevabını(200) verebilmeniz iterasyondur.

  Bir kelime eğer ki içerisinde tekrar eden bir hece barındırıyorsa bu iterasyonel bir kelime olarak geçer:

  örn. Mermer, baba, berber...

* Bu iterasyon mantığı bilgisayar bilimlerinde de kullanılmaktadır.

  Elimizdeki verileri(dizi,koleksiyon) tek tek elde ederek işlem yapmamızı sağlayan mantıktır.



## Iterasyon ile Döngü Arasındaki Fark Nedir?

```csharp
//Foreach(iterasyon) bir döngü değildir!
int[] sayilar = { 3, 213, 423, 42, 34, 234, 234, 234 };
//Tüm değerleri elde edelim.

for (int i = 0; i < sayilar.Length; i++) //Döngülerde bir sonraki işlem önemli değildir, kombinasyon önemlidir. Sonsuza kadar çalışabilir.
{
    
}

//Veri kaynağı olmadığı sürece foreach ile işlem yapılamaz!
foreach (int sayi in sayilar) //Iterasyon elindeki veri kümesi kadar işlem yapar.
{
    
}
```

> Döngülerde herhangi bir bağımlılık yoktur, foreach ise veri kümesine bağımlıdır.
> Veri kümesi değiştiği taktirde foreach patlar.



## Foreach Iterasyonu Nasıl Kullanılır?

```csharp
//Prototip : foreach ( degisken..in..collection.. ){..işlem..}
ArrayList sayilar = new ArrayList { 123, 123, 325, 2, 534, 5, 345, 345 }; //Veri kümesi olması gerekir (Dizi veya Koleksiyon)
foreach (object item in sayilar) //Sayilar koleksiyonu içerisinde gelecek olan değerler object olduğu için değişken object olarak belirtilir.
{
    Console.WriteLine(item);
}
```

```csharp
ArrayList sayilar = new ArrayList { 123, 123, 325, 2, 534, 5, 345, 345 };
foreach (object item in sayilar)
{
    sayilar.Add(123123); // Kaynak değişecekse veri kümesinde değişiklik olacaksa iterasyon patlar. Bu tür durumlarda döngülerde çalışılmalıdır.
    Console.WriteLine(item);
}
```



