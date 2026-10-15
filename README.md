# EstateProjectBackend

🌍 **Dil / Language:** [Türkçe](#-proje-amacı) | [English](#-project-purpose)

---

## 🎯 Proje Amacı
EstateProjectBackend, emlak ve gayrimenkul yönetim platformları için geliştirilmiş, yüksek performanslı ve ölçeklenebilir bir ASP.NET Core Web API arka uç sistemidir. Emlak ilanlarının oluşturulması, güncellenmesi, filtrelenmesi, danışman/kullanıcı yönetimi ve ilgili operasyonel süreçlerin merkezi ve güvenli bir yapı üzerinden yürütülmesini sağlar.

Proje, kurumsal yazılım standartlarına uygun olarak **Clean Architecture (Soğan Mimarisi)** prensipleri doğrultusunda yapılandırılmıştır. Bu sayede iş mantığı (Domain/Application), veri erişim katmanı (Persistence), dış servis entegrasyonları (Infrastructure) ve sunum katmanı (API) birbirinden net sınırlarla ayrılarak yüksek sürdürülebilirlik ve test edilebilirlik sağlanmıştır.

## 🛠️ Kullanılan Teknolojiler
- **C# / .NET:** Modern, tip güvenli ve performanslı uygulama geliştirme platformu
- **ASP.NET Core Web API:** RESTful servis mimarisi ve HTTP uç noktalarının yönetimi
- **Clean Architecture (Onion Architecture):** Sorumlulukların ayrıştırıldığı katmanlı mimari yapı
- **Entity Framework Core:** Veri tabanı erişimi ve nesne-ilişkisel eşleme (ORM)
- **Repository & Unit of Work Tasarım Desenleri:** Soyutlanmış veri erişim operasyonları
- **Swagger / OpenAPI:** API uç noktalarını belgeleme ve test etme aracı

## 🚀 Kurulum ve Çalıştırma

Projeyi yerel geliştirme ortamınızda çalıştırmak için aşağıdaki adımları takip edebilirsiniz:

### Gereksinimler
- [.NET SDK 8.0+](https://dotnet.microsoft.com/download)
- [Visual Studio 2022](https://visualstudio.microsoft.com/) veya [VS Code](https://code.visualstudio.com/)
- SQL Server veya desteklenen ilişkisel bir veritabanı sunucusu

### Adım Adım Kurulum

1. **Depoyu Klonlayın:**
```bash
git clone https://github.com/Merenylmz/EstateProjectBackend.git
cd EstateProjectBackend
```

2. **Bağımlılıkları Yükleyin:**
```bash
dotnet restore
```

3. **Veritabanı Yapılandırması:**
`EmlakSiteAPI/appsettings.json` dosyasında bulunan veritabanı bağlantı dizesini (`ConnectionStrings`) kendi yerel veritabanı bilgilerinize göre güncelleyin:
```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=EstateProjectDb;Trusted_Connection=True;TrustServerCertificate=True;"
}
```

4. **Veritabanı Migration İşlemini Uygulayın:**
```bash
dotnet ef database update --project EmlakSiteAPI.Persistance --startup-project EmlakSiteAPI
```

5. **Uygulamayı Başlatın:**
```bash
dotnet run --project EmlakSiteAPI
```

API başarıyla ayağa kalktığında tarayıcınızdan `https://localhost:<port>/swagger` adresine giderek Swagger arayüzünü görüntüleyebilirsiniz.

## 📌 Ek Bilgiler ve Özellikler
- **Modüler Katman Yapısı:**
  - `EmlakSiteAPI.Domain`: Temel varlıklar (Entities), değer nesneleri ve iş kurallarının çekirdeği.
  - `EmlakSiteAPI.Application`: DTO'lar, arayüzler (interfaces), servisler ve iş akışları.
  - `EmlakSiteAPI.Infrastucture`: E-posta gönderimi, dosya yükleme ve harici API entegrasyonları.
  - `EmlakSiteAPI.Persistance`: DbContext, konfigürasyonlar, migration'lar ve repository uygulamaları.
  - `EmlakSiteAPI`: Controller'lar, middleware'ler ve DI (Dependency Injection) yapılandırması.
- **SOLID Prensipleri:** Kod tabanı genişletilebilir, bakımı kolay ve loosely coupled (gevşek bağlı) şekilde kurgulanmıştır.

---

# EstateProjectBackend (English)

## 🎯 Project Purpose
EstateProjectBackend is a scalable, enterprise-grade ASP.NET Core Web API backend designed for real estate and property management systems. It provides robust endpoints to manage property listings, categories, agents, clients, and transactional real estate operations securely and efficiently.

The project is built around **Clean Architecture (Onion Architecture)** principles. By decoupling the core business logic (Domain/Application), data access layer (Persistence), external services (Infrastructure), and presentation layer (Web API), the system achieves superior maintainability, readability, and testability.

## 🛠️ Technologies Used
- **C# / .NET:** High-performance, modern backend runtime and language
- **ASP.NET Core Web API:** RESTful service design and HTTP endpoint handling
- **Clean Architecture (Onion Architecture):** Separation of concerns across independent layers
- **Entity Framework Core:** Object-Relational Mapping (ORM) and database management
- **Repository & Unit of Work Patterns:** Abstracted and testable data access operations
- **Swagger / OpenAPI:** Interactive API documentation and testing interface

## 🚀 Installation and Usage

Follow the steps below to set up and run the project locally:

### Prerequisites
- [.NET SDK 8.0+](https://dotnet.microsoft.com/download)
- [Visual Studio 2022](https://visualstudio.microsoft.com/) or [VS Code](https://code.visualstudio.com/)
- SQL Server or an equivalent supported relational database

### Step-by-Step Guide

1. **Clone the Repository:**
```bash
git clone https://github.com/Merenylmz/EstateProjectBackend.git
cd EstateProjectBackend
```

2. **Restore Dependencies:**
```bash
dotnet restore
```

3. **Configure the Database:**
Update the connection string in `EmlakSiteAPI/appsettings.json` according to your local database environment:
```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=EstateProjectDb;Trusted_Connection=True;TrustServerCertificate=True;"
}
```

4. **Apply Database Migrations:**
```bash
dotnet ef database update --project EmlakSiteAPI.Persistance --startup-project EmlakSiteAPI
```

5. **Run the Project:**
```bash
dotnet run --project EmlakSiteAPI
```

Once the application starts, navigate to `https://localhost:<port>/swagger` in your browser to inspect and test the API via Swagger UI.

## 📌 Additional Information & Features
- **Architectural Breakdown:**
  - `EmlakSiteAPI.Domain`: Core entities, enums, and domain-specific rules.
  - `EmlakSiteAPI.Application`: Business interfaces, DTOs, validations, and service logic.
  - `EmlakSiteAPI.Infrastucture`: File storage, notification/email providers, and external integrations.
  - `EmlakSiteAPI.Persistance`: EF Core DbContext, entity configurations, repositories, and migrations.
  - `EmlakSiteAPI`: API controllers, middleware pipeline, and dependency injection setup.
- **SOLID & Best Practices:** Ensures loosely coupled components with high cohesion, ready for microservices or containerized deployment.