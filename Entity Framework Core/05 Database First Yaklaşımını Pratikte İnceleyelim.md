# Entity Framework Core



## Database First Yaklaşımı



### Tersine Mühendislik(Reverse Engineering)

* Tersine mühendislik, bir sunucudaki veritabanının iskelesini kod kısmına oluşturma sürecidir.
* Bu süreci Package Manager Console(PMC) ya da .Net CLI aracılığıyla iki farklı şekilde yürütebiliriz.



### PMC ile Tersine Mühendislik

`Scaffold - DbContext 'Connection String' Microsoft.EntityFrameworkCore.[Provider]`

* PMC ile veritabanını modelleyebilmek için aşağıdaki kütüphanelerin projeye yüklenmesi gerekmektedir:
  * Microsoft.EntityFrameworkCore.Tools
  * Database Provider (Örn; Microsoft.EntityFrameworkCore.SqlServer)

<img src=https://i.imgur.com/CZLOLJu.png align=left width=75% />

<img src=https://i.imgur.com/YiHfMCu.png align=left width=75% />



### .Net CLI ile Tersine Mühendislik

`dotnet ef dbcontext scaffold 'Connection String' Microsoft.EntityFrameworkCore.[Provider]`

* .Net CLI ile veritabanını modelleyebilmek için aşağıdaki kütüphanelerin projeye yüklenmesi gerekmektedir:
  * Microsoft.EntityFrameworkCore.Design
  * Database Provider (Örn; Microsoft.EntityFrameworkCore.SqlServer)

<img src=https://i.imgur.com/Dt8ezdU.png align=left width=75% />


### Tabloları Belirtme

Varsayılan olarak veritabanındaki tüm tablolar modellenir. Sadece istenilen tabloların modellenebilmesi için aşağıdaki gibi talimatların verilmesi yeterlidir.

​	`Scaffold-DbContext 'Connection String' Microsoft.EntityFrameworkCore.[Provider] -Tables Table1, Table2...`
​	`dotnet ef dbcontext scaffold 'Connection String' Microsoft.EntityFrameworkCore.[Provider] --table Table1 --table Table2 ...`



### DbContext Adını Belirtme

Scaffold ile modellenen veritabanı için oluşturulacak context nesnesi adını veritabanından alacaktır. Eğer ki context nesnesinin adını değiştirmek istiyorsanız aşağıdaki gibi çalışabilirsiniz.

​	`Scaffold-DbContext 'Connection String' Microsoft.EntityFrameworkCore.[Provider] -Context ContextName`
​	`dotnet ef dbcontext scaffold 'Connection String' Microsoft.EntityFrameworkCore.[Provider] --context ContextName`



### Path ve Namespace Belirtme

Entity'ler ve DbContext sınıfı, default olarak direkt projenin kök dizinine modellenir ve projenin varsayılan namespace'ini kullanırlar. Eğer ki bunlara müdahale etmek istiyorsanız aşağıdaki gibi talimat verebilirsiniz.

Path:
`Scaffold-DbContext 'Connection String' Microsoft.EntityFrameworkCore.[Provider] -ContextDir Data -OutputDir Models`
`dotnet ef dbcontext scaffold 'Connection String' Microsoft.EntityFrameworkCore.[Provider] --context-dir Data --output-dir Models`

Namespace:
`Scaffold-DbContext 'Connection String' Microsoft.EntityFrameworkCore.[Provider]  -Namespace YourNamespace -ContextNamespace YourContextNamespace`

`dotnet ef dbcontext scaffold 'Connection String' Microsoft.EntityFrameworkCore.[Provider] --namespace YourNamespace --context-namespace YourContextNamespace`



### Model Güncelleme

Veritabanında olan değişiklikleri kod kısmına yansıtabilmek için Scaffold talimatını tekrar vermeniz gerekmektedir lakin verilen talimat neticesinde ilgili sınıfların zaten var olduğuna dair hata mesajı sizleri yüksek ihtimalle karşılayacaktır.


Böyle bir durumda veritabanı modeline değişiklikleri manuel olarak yansıtabileceğimiz gibi (ki tavsiye edilmez!), dosyalar var olsa dahi zorla yeniden en güncel haliyle modellenmesini sağlayabiliriz. Bunun için aşağıdaki gibi Force talimatının verilmesi yeterli olacaktır.

<img src=https://i.imgur.com/BpvOMph.png align=left />
`Scaffold-DbContext 'Connection String' Microsoft.EntityFrameworkCore.[Provider] -Force`

<img src=https://i.imgur.com/JqQd8zY.png align=left />
`dotnet ef dbcontext scaffold 'Connection String' Microsoft.EntityFrameworkCore.[Provider] --force`



### Modellerin Özelleştirilmesi

* Database First yaklaşımında veritabanı nesneleri otomatik olarak modellenmekte ve generate edilmektedir. Bazen bu otomatize olan süreçte manuelde olsa entity'ler de yahut context nesnesinde özelleştirme yapmak isteyebiliriz.
* Ama biliyorsunuz ki, veritabanında yapılan değişiklikler neticesinde Force komutu eşliğinde tüm değişiklikler kod kısmına sıfırdan yansıtılabilir ve bu da yapılan değişikliklerin ezilme reskinin söz konusu olduğu anlamına gelir.
* Bu tarz özelleştirme durumlarında bizzat model sınıflarını kullanmaktansa bunların partial class'ları üzerinde çalışmak en doğrusudur!
