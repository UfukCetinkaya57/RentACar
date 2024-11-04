# RentACar API

RentACar API, temel düzeyde endpointleri bulunan, asıl amacı yüksek işleyişte modülerliğin, temiz mimarinin nasıl işlendiğini gösteren basit işlevli bir ASP.NET Core API projesidir. Proje, SOLID prensipleri, CQRS ve bağımlılık enjeksiyonu gibi en iyi desenleri kullanarak temiz bir mimariyle tasarlanmıştır.

### Mimariler
Proje, SOLID ve CQRS prensiplerine uygun olarak **Clean Architecture** ve katmanlı bir yapı ile tasarlanmıştır:
- **Application Katmanı**: İş mantıkları ve doğrulama işlemleri burada bulunur.
- **Persistence Katmanı**: Veritabanı işlemlerini yönetir.
- **Domain Katmanı**: Temel entity ve nesneler buradadır.
- **Web API Katmanı**: API uç noktalarını barındırır.

## Kullanılan Teknolojiler
- **EF Core**: Veritabanı yönetimi için Entity Framework.
- **MediatR**: CQRS modelini uygulamak için.
- **AutoMapper**: Nesne haritalama işlemleri için.
- **FluentValidation**: Girdi doğrulama işlemleri için.
- **Serilog**: Dosya ve SQL Server’a loglama.

### Serilog
- **Dosya Loglama**: Log dosyaları `appsettings.json` içerisindeki `FolderPath` alanında belirtilen klasöre kaydedilir.
- **SQL Server Loglama**: Hatalar ve olaylar SQL Server üzerindeki `Logs` tablosuna kaydedilir.
- **Yapılandırma**: Loglama ayarları `appsettings.json` dosyasındaki `SeriLogConfigurations` bölümünden yapılandırılabilir.

## Kurulum

### Gereksinimler
- [SQL Server](https://www.microsoft.com/sql-server/sql-server-downloads)
- Docker (isteğe bağlı, SQL Server ve PostgreSQL ile çalışmak için)

### Adımlar
1. Projeyi klonlayın:
```git clone <repository-url>```

2. Veritabanı bağlantılarını yapılandırın:
- `appsettings.json` dosyasında `ConnectionStrings` kısmındaki RentACar veritabanı bağlantısını ayarlayın.

3. Migration’ları uygulayın ve veritabanını güncelleyin:
```dotnet ef database update```

4. Uygulamayı başlatın:
``` dotnet run ```
