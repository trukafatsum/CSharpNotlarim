# C# Notları (Ekstra Bilgi)



## Döngülerde Boş Scope Kullanmak İstemedğimiz Durumlarda ;(Noktalı Virgül) Operatörü ile Temiz Kod Yazımı

> Sonsuz döngüye nasıl giriyorduk
>
> ```csharp
> while (true)
> {
>     
> }
> for (;;)
> {
>     
> }
> do
> {
>     
> }while(true);
> ```
>
> Eğer ki sonsuz döngüye ihtiyacımız var ve içinde işlem yapmayacaksak, bunu şu varyasyonlarla da yapabilmekteyiz;
>
> ```csharp
> //Bazen(ki ileride asenkron programlamada) içi boş sonsuz döngülere ihtiyacımız olabilir.
> //Bu durumlarda normal döngü gövdelerini kullanabileceğimiz gibi, scopesuz bu şekilde de kullanabilmekteyiz.
> while(true);
> 
> for(;;);
> 
> do;
> while(true);
> ```
>
> 



## if  Yapısında Boş Scope Kullanmak İstemediğimiz Durumlarda ;(Noktalı Virgül) Operatörü ile Temiz Kod Yazımı

> ```csharp
> if (true)
> {
>     
> }
> if (true);
> ```
>
> [Video desteği](https://youtu.be/D2HP2Ta51J0)
>
> 