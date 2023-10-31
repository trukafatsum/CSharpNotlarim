# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## Positional Record

[TOC]



### Positional Record Nedir?

* Norminal Record'lar Object Initializer'lar ile ilk değerleri verilerek üretilebilen readonly datalardı.
* Positional Record'lar ise esasında Record'lar içerisinde tanımlama yapabildiğimiz constructor ve deconstructor kullanımlarını daha da özelleştirerek kullanılmasını sağlamaktadırlar.

```csharp
class Program
{
    static void Main(string[]args)
    {
        MyRecord m = new MyRecord("asfasfasf","oıwoqjwrıqw");
        var (n,s) = m;
    }
}
record MyRecord(string name, string surname)// Positional Record : Hem constructor hem deconstruct'a karşılık gelmektedir.
{
    
}
```

> Bu özellik record'a has bir özelliktir. Record yerine Class kullanmaya çalışırsak compiler hata verecektir.
>
> ```csharp
> class Program
> {
>     static void Main(string[]args)
>     {
>         MyRecord m = new MyRecord("asasfasf","qwerqwrqwr");
>         var (n,s) = m;
>     }
> }
> class MyRecord(string name, string surname)
> {
>     
> }
> ```

#### Prototip

```csharp
// record name(...,...) : Bu semantik C# 9.0 ile positional record'a gelmiştir.
```

* Bir record üzerinde constructor ve desconstruct yapılanmasını hızlı bir şekilde oluşturmamızı sağlayan bir semantik sağlamaktadır.
* Positional Record kullanılırken parametrelerin karşılıkları olan propertyleri manuel oluşturmak zorunda değiliz.
* Bu parametrelerin karşılığı olarak compiler seviyesinde propertyler otomatik oluşturulacaktır.
* Bu propertyler oluşturulurken **init** olacak şekilde oluşturulur.



### Positional Record Kullanırken Kendimiz Constructor Tanımlayabilir Miyiz?

* Positional Record tanımlanmışsa eğer nesne üretiminde tetiklenmesi / kullanılması zorunludur!!

```csharp
class Program
{
    static void Main(string[]args)
    {
        MyRecord m = new MyRecord();
        var (n,s) = m;
    }
}
record MyRecord(string name, string surname)
{
    public MyRecord() : this("asdf","qwerty") // Yeni bir constructor tanımlayabilmek için this ile positional record'un constructor'ına değer göndermek zorundayız.
    {
        
    }
}
```



### Positional Record Kullanırken Property Oluşturma

```csharp
record MyRecord(string name, string surname)
{
    public string Name => name;
    public string Surname => surname;
}
```

