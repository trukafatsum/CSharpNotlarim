# Object Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Record Struct



### Record Struct Nedir?

Record Struct'ı anlayabilmek için öncelikle Record yapısını hatırlamakta fayda var.

* Record'lar, verisel olarak taşıdıkları değerleri ön planda tutan, değeri değiştirilemeyen ve compile neticesinde IEquatable<.T> implemente ederek özünde bir sınıfa dönüşen referans türlü veri yapılarıdır.
* Record Struct'lar ise Record'ın birçok avantajını sağlayan lakin değer türlü olması gibi radikal farkları olan veri yapılarıdır.
* Bir record struct'ı oluşturmak oldukça basittir. `recod struct MyRecordStruct {}`
  * Nasıl ki bir record özünde tüm sınıf özelliklerine sahip olan bir yapıysa, benzer mantıkta bir record struct da yine özünde bir struct olan ve struct'ın tüm özelliklerine sahip olan bir yapılanmadır.

Record ile record struct arasında mantıken benzerlikler olduğu gibi bazı noktalarda davranışsal farklar söz konusudur. 

#### <u>Immutability</u>

Record'lar da Positional Records özelliğini hatırlayalım..

```csharp
record MyRecord (string x, int y)
{
    
}
```

Bu positional record'ların en önemli özelliği değiştirilemez olmalarıdır. Çünkü burada tanımlanan değişkenler özünde init property olarak üretilmektedirler.

Amma velakin positional records özelliği record struct'ta kullanılıyorsa eğer, değiştirilemez değildirler!

```csharp
record struct MyRecordStruct(string x, int y)
{
    
}
```

Yani yukarıdaki tanımlara nazaran aşağıdaki durumlar söz konusu olacaktır.

```csharp
MyRecord myRecord = new("asd",123);
myRecord.x = "dsa";
myRecord.y = 321;
//Compiler record üzerinde sonradan değer atama işlemlerinde hata verecektir.
MyRecordStruct myRecordStruct = new("asd",123);
myRecordStruct.x = "dsa";
myRecordStruct.y = 321;
//Record Struct'ta ise compiler herhangi bir hata vermeyecektir ve değer atamaları gerçekleşebilir.
```

Ha yine de record struct'ta positional record'ı değiştirilemez olarak kullanmak istiyorsanız readonly keywordü ile işaretleme yapmanız gerekmektedir.

```csharp
readonly record struct MyRecordStruct(string x, int y)
{
    
}
```



#### <u>with Expressions</u>

with expressions, immutable tür olan record nesneleri üzerinde verisel değişiklik yapamadığımız için ilgili nesneyi klonlayarak (deep copy) istediğimiz yeni değerlerde yeniden oluşturmamızı sağlayan bir özelliktir. Haliyle record class'lar da olduğu gibi record struct'larda da with expression niteliği kullanılabilmektedir.

```csharp
MyRecordStruct myRecordStruct = new("asd",123);
var newMyRecordStruct = myRecordStruct with { x= "dsa" };
```



#### <u>Equality Comparison (Eşitlik Karşılaştırması)</u>

Normal şartlarda struct veri türlerinin üzerinde aşağıdaki gibi eşitlik (==) ve eşit değillik (!=) operatörleri desteklenmemektedir!

```csharp
MyStruct m1 = new() {MyProperty = 5};
MyStruct m2 = new() {MyProperty = 15};

if (m1 == m2)
{
    
}
```

Lakin record struct'lar da bu operatörler desteklenmektedir! Bu da radikal yeniliklerden birisidir!

```csharp
MyRecordStruct m1 = new("abc",123);
MyRecordStruct m2 = new("abc", 123);
if (m1 == m2)
{
    
}
```

Tabi burada verisel değerler ön planda tutulduğu için aynı değerlere sahip iki farklı record nesnesinin bu şekilde karşılaştırılması true değerini döndürecektir.



#### <u>Printing Members</u>

Record struct'ların getirdiği son yenilik ise elemanlarını direkt olarak string'e ToString fonksiyonuyla çevirdiğimizde bizlere verinin metinsel halini sunmasıdır.

```csharp
MyRecordStruct m1 = new("abc",123);
MyRecordStruct m2 = new("def",456);
MyRecordStruct m3 = new("ghı",456);

Console.WriteLine(m1.ToString());
Console.WriteLine(m2.ToString());
Console.WriteLine(m3.ToString());
```

Esasında bu özelliğin record class'larda da olduğunu bilmenizde fayda vardır!



### Primary Constructor

Record struct'larda positional records kullanılıyorsa eğer constructor tanımlanmasına izin verilmemektedir.

```csharp
record struct MyRecordStruct
{
    public MyRecordStruct(string x, int y)
    {
        
    }
}
//Yukarıdaki şekilde tanımlanabilir.
```

```csharp
record struct MyRecordStruct()
{
    public MyRecordStruct(string x, int y)
    {
        
    }
}
record struct MyRecordStruct(string x)
{
    public MyRecordStruct(int y)
    {
        
    }
}
record struct MyRecordStruct(string x, int y)
{
    public MyRecordStruct()
    {
        
    }
}
//Yukarıdaki şekilde tanımlanamazlar!
```

> Mikro seviyede yapılan bir optimizasyon neticesinde record struct'ların, normal struct'lara oranla '20' kat daha fazla performanslı olduğu gözlemlenmiştir!



### Performans Cetveli

Record Structs > Struct > Record Class > Class