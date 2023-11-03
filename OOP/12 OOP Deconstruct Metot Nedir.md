# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Deconstruct Metodu

[TOC]

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/12-QR.png width=10% alt="İlgili Video İçeriği QR" />

### Deconstruct Metodu Nedir?

* Bir sınıf içerisinde "Deconstruct" ismiyle tanımlanan metot, compiler tarafından özel olarak algılanmakta ve sınıfın nesnesi üzerinden geriye hızlıca Tuple bir değer döndürmemizi sağlamaktadır.

  > Tüm özel sınıfların isimleri sınıf ismiyle aynı olmak zorundaydı. Bunların arasında bir istisna var o da 'deconstruct'.
  > Deconstruct bir fonksiyondur. Sınıf ismiyle aynı ismi barındırmaz. İsmi Deconstruct olmalıdır!

### Prototip

```csharp
class MyClass
{
    public string x {get; set;}
    public string y { get; set;}
    public void Deconstruct(out string a, out string b)
    {
        a = x;
        b = y;
    }
}
```

> 1. Deconstruct fonksiyon tanımlamak için öncelikle public olması gerekmektedir.
>
> 2. Geriye değer döndürmemelidir.
> 3. Bu özel bir metottur ve özel olduğunu tanımlamak için 'Deconstruct' ismiyle tanımlanması gerekmektedir.
> 4. İmzasındaki değişkenler out olarak tanımlanması gerekmektedir.
>
> out olarak aldığı bu parametreleri Tuple olarak döndürecektir.
>
> Compiler bu metodun özel bir yapılanma olduğunu isminden algılayacaktır.



### Pratikte İnceleyelim

Person isminde bir sınıf oluşturalım ve Name (isim) ve Age (yaş) tutacak 2 property oluşturalım.

```csharp
class Program
{
    static void Main(string[]args)
    {
        Person person = new Person
        {
            Name = "Mustafa",
            Age = 25
        };
        var (x,y) = person; // Burada bizlere x ve y olarak Name ve Age değerlerini alır.
    }
}
class Person
{
    public string Name {get; set;}
    public int Age {get; set;}
    
    public void Deconstruct(out string name, out int age) // Deconstruct
    {
        name = Name;
        age = Age;
    }
}
```

