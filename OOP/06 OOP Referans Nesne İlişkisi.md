# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Referans Nesne İlişkisi

[TOC]



### Referans Nedir?

Ram'in Stack bölgesinde tanımlanan ve Heap bölgesindeki nesneleri işaretleyen/referans eden değişkenlerdir/noktalardır.

<img src= https://i.imgur.com/oGAa5ew.png width=700 align=left>

Referanslar illa bir nesne referans etmek zorunda değildirler.

> Eğer ki referans herhangi bir nesne işaretlemiyorsa null değerini alır.



### Stack - Heap İlişkisi

<img src=https://i.imgur.com/nrJsDzC.png width=700 align=left>

```csharp
// MyClass m : MyClass türünde m isminde bir referans noktası oluşturur.
// '='operatörü : Assign operatörü olarak bildiğimiz bu operatör, referans türlü değişkenlerde referans/refere etme operatörü olarak işlev gösterir.
// new MyClass() : Heap üzerinde bir nesne oluşturur.
```

* Nesneler neden referansla işaretleniyor? Neden referans kullanıyoruz?

  * Bunun sebebi, nesnelerin referans türlü olmasıdır. Referans türlü değer/değişkenler Heap üzerinde oluşturulmakta olup, buna doğrudan erişim olmamasından dolayı referansla işaretleyip, dolaylı yoldan erişim sağlayabilmekteyiz.

* Referans üzerinden nesneye nasıl erişilir? Nesne üzerindeki elemanlara nasıl erişilir?

  * Öncelikle referans noktası oluşturulur ve referans etme operatörü '=' ile nesne çağırılır.

    ```csharp
    //Örnek
    MyClass m = new MyClass();
    ```

    Nesne oluşturulduktan sonra bu nesneye 'm' üzerinden erişim sağlayabilmekteyiz.

    ```csharp
    //Nesne üzerindeki elemanlara erişebilmek için '.' yani access member operatörünü kullanmaktayız.
    MyClass m = new MyClass();
    //Nesnemizin içerisinde public/erişilebilir Topla metodu olduğunu varsayarsak şu şekilde kullanım sağlayabilmekteyiz.
    m.Topla();
    ```

* Null olan (yani nesnesi olmayan) referanslar üzerinden herhangi bir member'i çağırıp işlemeye çalıştığımızda bu durumda NullReference hatası almaktayız.

  ```csharp
  //NullReference Hatası için örnek
  MyClass m2 = null;
  m2.Topla();
  ```



### Referanssız Nesneler

<img src=https://i.imgur.com/TJ3kbhF.png width=700, align=left>

Bir nesne oluşturulduğu an herhangi bir referansla işaretlenmezse eğer Heap'e yerleştirilir.

```csharp
//Referanssız nesne oluşturabilmekteyiz, lakin bu nesne sistemde/memory de lüzumsuz yer kaplayacağından dolayı belirsiz bir süre sonra Garbage Collecter dediğimiz çöp toplayıcısı tarafından temizlenecektir.

//GC; heap'de referanssız olan nesneleri imha etmekten/temizlemekten sorumlu bir yapılanmadır.
```

Lakin bu nesneye tarafımızca bir daha erişemeyiz. Haliyle ilgili nesneyle aramızdaki tek diyalog oluşturma anıdır.

```csharp
new MyClass().MyProperty = 10; // Sadece oluşturma anında erişebilmekteyiz.
```



### Referans Türüne Göre Nesne Elemanlarına Erişim

Her bir referans bir nesneyi temsil edebilecek yapıya sahiptir.

<img src=https://i.imgur.com/uPNFlr4.png width=700, align=left />

İleride Polimorfizm ve Abstraction konularında daha detaylı ele alacağız.



### Object Initializer İle Nesne Oluşturma Esnasında Propertylere İlk Değer Atama

Bir sınıftan nesne oluştururken ilgili sınıfın elemanlarına şu şekilde değer atayabilmekteyiz.

```csharp
MyClass m = new MyClass();
m.MyProperty = 10;
```

Birde **object initializer** ile şu şekilde değer atayabilmekteyiz.

```csharp
//Object Initializer Semantiği
MyClass m = new MyClass()
{
  MyProperty = 10,
  MyProperty2 = 30,
  MyProperty3 = 40 //Nesnenin default değeri olarak düşünebilirsiniz.
      
  //Metot işlevsel bir yapı olduğu için değer atama işlemi yapılmaz. Dolayısıyla Object Init ile sadece field ve propertylere erişim sağlayabilmekteyiz.
};
```



