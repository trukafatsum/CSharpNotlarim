# Object  Oriented Programming (Nesne Tabanlı/Yönetimli Programlama)

## sealed Keyword

<img src = https://github.com/trukafatsum/CSharpNotlarim/blob/main/OOP/%C4%B0lgili%20Ders%20QR/23-QR.png width=10% alt="İlgili Video İçeriği QR" />

### sealed Keyword'ü Nedir?

* Bir sınıfın miras vermesini yahut bir başka deyişle başka bir sınıf tarafından miras alınmasını engelleyen bir keyword'dür.
* Sadece sınıflarda ve sadece 'override' edilmiş metotlarda kullanılabilir.



### Class Üzerinde sealed Keyword'ünün İşlevi Nedir?

```csharp
sealed class A
{
}
class B : A //A sınıfı sealed olduğu için miras alınamaz derleyici hatası verir.
{
}
sealed record C
{
}
record D : C //Record'larda sınıf fıtratında oldukları için, aynı durum burası içinde geçerlidir.
{   
}
```



### Metot Üzerinde sealed Keyword'ünün İşlevi

* Kalıtımsal durumlarda, atalardan gelen ve birinci dereceden alt sınıf tarafından 'override' edilmiş olan 'virtual' member'ların hiyerarşideki sonraki sınıflar tarafından 'override' edilmesini ilgili member'ı sealed ile işaretleyerek engelleyebiliriz.

  ```csharp
  class A
  {
      public virtual void X()//A sınıfında virtual method tanımlandı
      {
          Console.WriteLine("Merhaba A");
      }
  }
  class B : A
  {
      sealed public override void X() // A sınıfından kalıtım alan B sınıfı içerisinde ilgili method override edildi
      {
          Console.WriteLine("Merhaba B");
      }
  }
  class C : B
  {
      public override void X() // B sınıfında sealed ile işaretlendiği için tekrar override edilemez. B sınıfındaki override haliyle devam eder.
      {
          Console.WriteLine("Merhaba C");//B'de sealed ile işaretlenmemiş olsaydı override edilebilirdi.
      }
  }
  ```

* Pratikte bu yöntem sayesinde üst sınıfın davranışını güvenli bir şekilde korumuş ve ilgili metodun değiştirilmesini önlemiş oluyoruz.



### sealed Keyword'ü Hangi Durumlarda Kullanılmalıdır?

* <u>Sınıfların Davranışlarını Korumak İstediğimizde</u>
  Kalıtımsal Hiyerarşide üst sınıfların özel metotları/davranışları varsa ve bu metotlardaki davranışların alt sınıflar tarafıdan değiştirilebilir olmasını istemediğimiz durumlarda, o metodu sealed olarak işaretleyebiliriz.
* <u>Performans İyileştirmesi İstendiğinde</u>
  Mikro seviyede yapılan bir optimizasyon neticesinde C#'ta bir sınıf sealed ile işaretlendiğinde sealed olmayan bir sınıfa göre ufak çapta bir performans artışı gösterdiği anlaşılmıştır. Bunun nedeni, derleyicinin sealed ile işaretlenmiş sınıfın miras alınamayacağını bilerek daha hızlı derleme yapmasıdır.
* <u>Singleton Design Pattern</u>
  Signleton Design Pattern'da bir sınıfın uygulama çapında tekil bir instance'ının olması amaçlanmaktadır. Haliyle ilgili sınıf sealed ile işaretlenerek, bu sınıftan herhangi bir kalıtımsal ilişkinin yaratılmasını engelleyebilir ve tek instance üretimini daha da garanti hale getirmiş oluruz.

> Ekstra bilgi : Java'da final keyword'ü C#'taki sealed keyword'ünün muadilidir.

