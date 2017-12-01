---
title: Erstellen einer einfachen datengesteuerte CRUD-microservice
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Erstellen einer einfachen datengesteuerte CRUD-microservice"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b814d344f2c78e7cf57f9e2896cf1d6b52db38d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Erstellen einer einfachen datengesteuerte CRUD-microservice

Dieser Abschnitt beschreibt wie die Erstellung eine einfachen Microservice, der ausführt erstellen, lesen, Update- und Löschvorgänge (CRUD) für eine Datenquelle.

## <a name="designing-a-simple-crud-microservice"></a>Entwerfen eine einfache CRUD-microservice

Aus Sicht des ein Entwurf ist diese Art von Datenvolumes Microservice sehr einfach. Möglicherweise das Problem zu lösen einfach ist oder die Implementierung ist möglicherweise nur ein Proof of Concept.

![](./media/image4.png)

**Abbildung 8-4**. Interne Entwurf für einfache CRUD-microservices

Ein Beispiel für diese Art von einfachen Datenlaufwerk-Dienst ist der Katalog Microservice aus der eShopOnContainers-beispielanwendung. Dieser Typ des Diensts implementiert alle seine Funktionalität in einem einzelnen ASP.NET Core Web-API-Projekt, das Klassen für das zugeordnete Datenmodell, die Geschäftslogik und seine Datenzugriffscode enthält. Außerdem speichert ihre verknüpften Daten in einer Datenbank in SQL Server (als einen anderen Container für Dev/Testzwecke) ausgeführt, aber unter Umständen liegen auch alle regulären SQL Server-Host, wie in Abbildung 8 – 5 gezeigt.

![](./media/image5.png)

**Abbildung 8 – 5**. Einfache Data-driven/CRUD-Microservice Entwurf

Wenn Sie diese Art von Dienst entwickeln, müssen Sie nur [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) und wie eine Datenzugriffs-API oder ORM- [Entity Framework Core](https://docs.microsoft.com/ef/core/index). Sie können auch generieren [Swagger](http://swagger.io/) Metadaten automatisch über [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) zu beschreiben, was Ihren Dienst anbietet, wie im nächsten Abschnitt erläutert.

Beachten Sie, dass ausführen, einen Datenbankserver, z. B. SQL Server in einem Docker-Container für entwicklungsumgebungen, schwerwiegend sind, da Sie alle Ihre Abhängigkeiten, einrichten aufweisen darf und ohne eine Datenbank in der Cloud oder lokal bereitgestellt werden soll. Dies ist sehr praktisch, wenn Integration ausgeführt testet. Allerdings ist für produktionsumgebungen, die eine Datenbank in einem Container ausführen nicht empfohlen, da Sie hohen Verfügbarkeit mit diesen Ansatz in der Regel nicht erhalten. Für eine produktionsumgebung in Azure empfiehlt es sich die Verwendung von Azure SQL-Datenbank oder eine andere datenbanktechnologie, die hohe Verfügbarkeit und hoher Skalierbarkeit bereitstellen kann. Beispielsweise können Sie für einen NoSQL-Ansatz DocumentDB auswählen.

Schließlich können Sie durch Bearbeiten der dockerfile-Datei und Docker-compose.yml-Metadatendateien, erstellen das Image dieses Containers konfigurieren – welche Basisimage es verwenden, sowie Einstellungen wie z. B. interne und externe Namen und TCP-Ports zu entwerfen. 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Implementieren eine einfache CRUD-Microservice mit ASP.NET Core

Um eine einfache CRUD-Microservice mit .NET Core und Visual Studio zu implementieren, zunächst erstellen Sie ein einfaches ASP.NET Core Web-API-Projekt (ausgeführt .NET Core, damit es auf einem Linux-Docker-Host ausgeführt werden kann), als Abbildung 8 – 6.

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  ![](./media/image6.png)   ![](./media/image7.png)
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

**Abbildung 8 – 6**. Erstellen ein ASP.NET Core Web-API-Projekt in Visual Studio

Nach dem Erstellen des Projekts, können Sie die MVC-Controller implementieren, wie in jedem anderen Web-API-Projekt mit dem Entity Framework-API oder anderen-API. EShopOnContainers.Catalog.API im Projekt können Sie sehen, die wichtigsten Abhängigkeiten für diese Microservice nur ASP.NET Core selbst, Entity Framework und Swashbuckle, wie in Abbildung 8 – 7 dargestellt.

![](./media/image8.PNG)

**Abbildung 8 – 7**. Abhängigkeiten in eine einfache CRUD-Web-API-microservice

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Implementieren von CRUD-Web-API-Diensten mit Entity Framework Core

Entity Framework (EF) Core ist eine einfache, die erweiterbar sind, und plattformübergreifende-Version des beliebten Entity Framework-Daten zugreifen, Technologie. EF Core handelt es sich um eine objektrelationale Mapper (ORM), die .NET Entwicklern mit einer Datenbank mithilfe von .NET Objekten arbeiten.

Der Katalog Microservice verwendet EF und SQL Server-Anbieter, weil die Datenbank in einem Container mit dem SQL Server für Linux-Docker-Image ausgeführt wird. Allerdings kann die Datenbank in SQL Server, z. B. Windows on-Premises oder Azure SQL-Datenbank bereitgestellt werden. Das einzige gewünschten ändern, ist die Verbindungszeichenfolge in der ASP.NET Web API Microservice.

#### <a name="add-entity-framework-core-to-your-dependencies"></a>Fügen Sie Entity Framework Core hinzu, um Ihre Abhängigkeiten

Sie können das NuGet-Paket für den Datenbankanbieter installieren, in diesem Fall SQL Server, von innerhalb der Visual Studio-IDE oder mit der NuGet-Konsole verwenden möchten. Verwenden Sie den folgenden Befehl:

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a>Das Datenmodell

Datenzugriff erfolgt mit EF-Kern mithilfe eines Modells. Ein Modell besteht aus der Entitätsklasse und an einem abgeleiteten Kontext, der eine Sitzung mit der Datenbank, sodass Sie Abfragen und Speichern von Daten darstellt. Sie können Generieren eines Modells aus einer vorhandenen Datenbank, manuell ein Modell, um Ihre Datenbank zu entsprechen, code und EF-Migrationen verwenden, um eine Datenbank aus dem Modell erstellen (und entwickeln sie, während das Modell im Zeitverlauf ändert). Für den Katalog Microservice verwenden wir den letzten Ansatz. Sehen Sie ein Beispiel für die Entitätsklasse CatalogItem im folgenden Codebeispiel wird eine einfache Plain Old-CLR-Objekt ist ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) Entitätsklasse.

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public CatalogItem() { }
}
```

Darüber hinaus benötigen Sie ein ' DbContext ', die eine Sitzung mit der Datenbank darstellt. Für den Katalog Microservice wird die CatalogContext-Klasse von der Basisklasse von ' DbContext ' abgeleitet, wie im folgenden Beispiel gezeigt:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }

    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

Die Implementierung von ' DbContext ' kann kein zusätzlichen Code enthalten. Beispielsweise haben in der beispielanwendung wir eine OnModelCreating-Methode in der CatalogContext-Klasse, die automatisch die Beispieldaten beim ersten versucht wird auffüllen, auf die Datenbank zugreifen. Diese Methode ist nützlich für Demodaten. Sie können auch die OnModelCreating-Methode verwenden, zum Anpassen der Objekt-Datenbank Entität Zuordnungen mit vielen anderen [EF Erweiterungspunkte](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

Sie können weitere Details zu OnModelCreating in der [Implementieren der Infrastruktur Persistenzebene mit Entity Framework Core](#implementing_infrastructure_persistence) Abschnitt weiter unten in diesem Buch.

##### <a name="querying-data-from-web-api-controllers"></a>Abfragen von Daten aus der Web-API-Controller

Instanzen von die Entitätsklassen werden in der Regel mit Language Integrated Query (LINQ), aus der Datenbank abgerufen, wie im folgenden Beispiel gezeigt:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ??
           throw new ArgumentNullException(nameof(catalogIntegrationEventService));
        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
    [FromQuery]int pageIndex = 0)
    {
        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();
        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();
        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);
        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);
        return Ok(model);
    } 

    //...
}
```

##### <a name="saving-data"></a>Speichern von Daten

Daten werden erstellt, gelöscht und mit Instanzen von Klassen für die Entitäten in der Datenbank geändert. Sie können Code wie im folgenden hartcodierte Beispiel (in diesem Fall simulierten Daten) auf Ihre Web-API-Controller hinzufügen.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Abhängigkeitsinjektion in ASP.NET Core und Web-API-Controller

Verwenden Sie in ASP.NET Core (Dependency Injection, DI) ausgegeben. Sie müssen nicht Einrichten einer Drittanbieter-Inversion of Control (IoC) Container, obwohl Sie Ihre bevorzugten IoC-Container in ASP.NET Core-Infrastruktur eingebunden werden können, wenn Sie möchten. In diesem Fall bedeutet dies, dass Sie die erforderlichen EF DBContext oder zusätzliche Repositorys über die Controller-Konstruktor direkt einfügen können. Im obigen Beispiel der CatalogController-Klasse werden wir ein Objekt des Typs CatalogContext sowie andere Objekte über den Konstruktor CatalogController injiziert.

Eine wichtige Konfiguration in der Web-API-Projekt eingerichtet ist, die Registrierung des DbContext-Klasse in den Dienst IoC-Container. Sie dazu in der Regel die Startklasse. durch Aufrufen von Diensten. AddDbContext Methode innerhalb der ConfigureServices-Methode, wie im folgenden Beispiel gezeigt:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
               typeof(Startup).
               GetTypeInfo().
               Assembly.
               GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...

}
```

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Abfragen von Daten**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

-   **Speichern von Daten**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Die von Docker-Containern verwendet DB-Verbindungs-Zeichenfolge und Umgebung Variablen

Sie können ASP.NET Core Einstellungen verwendet und eine ConnectionString-Eigenschaft der settings.json-Datei wie im folgenden Beispiel gezeigt hinzufügen:

```csharp
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

Die Datei settings.json kann Standardwerte für die ConnectionString-Eigenschaft oder eine andere Eigenschaft haben. Diese Eigenschaften werden jedoch mithilfe der Werte der Umgebungsvariablen überschrieben werden, die Sie in der Docker-compose.override.yml-Datei angeben.

Aus Docker compose.yml oder Docker compose.override.yml Dateien können Sie diese Umgebungsvariablen zu initialisieren, damit diese Docker sie als OS-Umgebungsvariablen für Sie eingerichtet wird wie gezeigt in der folgenden Docker-compose.override.yml-Datei (die Verbindung Zeichenfolge und andere Zeilen in diesem Beispiel zu umschließen, aber es würde nicht in eine eigene Datei umschließen).

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    - ExternalCatalogBaseUrl=http://10.0.75.1:5101
    #- ExternalCatalogBaseUrl=http://dockerhoststaging.westus.cloudapp.azure.com:5101
  
  ports:
    - "5101:5101"
```

Die Docker-compose.yml-Dateien auf Projektmappenebene können nicht nur flexibler als Konfigurationsdateien auf das Projekt oder Microservice allerdings auch mehr Sicherheit. Beachten Sie, dass die Docker-Images, die Sie pro Microservice build enthalten nicht die Docker-compose.yml Dateien, nur die Binärdateien und Konfigurationsdateien für jede Microservice, einschließlich der dockerfile-Datei. Aber die Docker-compose.yml-Datei wird nicht zusammen mit der Anwendung bereitgestellt. Es wird nur zum Zeitpunkt der Bereitstellung verwendet. Daher ist die platzieren Umgebungswerte für Variablen in die Docker-compose.yml-Dateien (auch ohne das Verschlüsseln der Werte) eine höhere Sicherheit als überführen diese Werte in den normalen NET-Konfigurationsdateien, die mit Ihrem Code bereitgestellt werden.

Sie können schließlich den Wert aus dem Code abrufen, mithilfe der Konfiguration\["ConnectionString"\], wie in der ConfigureServices-Methode in einer früheren Codebeispiel gezeigt.

Allerdings kann für produktionsumgebungen zu Explorer zusätzliche Methoden zum Speichern von geheimen Schlüsseln wie die Verbindungszeichenfolgen sinnvoll. In der Regel, die verwaltet werden durch die ausgewählte Orchestrator, wie Sie tun können [Docker Containerhostclustern geheime Schlüssel Management](https://docs.docker.com/engine/swarm/secrets/).

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Implementieren von versionsverwaltung in ASP.NET Web-APIs

Wie die geschäftsanforderungen ändern, neue Sammlungen von Ressourcen hinzugefügt werden, ändert sich möglicherweise die Beziehungen zwischen Ressourcen und die Struktur der Daten in Ressourcen möglicherweise geändert werden. Aktualisieren einer Web-API, um neue Anforderungen zu verarbeiten ist ein relativ einfacher Vorgang jedoch berücksichtigen Sie die Auswirkungen, die solche Änderungen auf Clientanwendungen, die Nutzung der Web-API haben. Obwohl der Entwickler entwerfen und implementieren eine Web-API die vollständige Kontrolle über diese API hat, hat der Entwickler nicht das gleiche Maß an Kontrolle über Clientanwendungen, die vom Drittanbieter Organisationen Remote erstellt werden kann.

Versionsverwaltung ermöglicht eine Web-API, um anzugeben, die Funktionen und Ressourcen, die sie verfügbar macht. Eine Clientanwendung kann Anforderungen an eine bestimmte Version einer Funktion oder die Ressource dann senden. Es gibt verschiedene Methoden zum Implementieren einer versionsverwaltung:

-   URI-versionsverwaltung

-   Abfrage Zeichenfolge versionsverwaltung

-   Header-versionsverwaltung

Abfragezeichenfolge und URI Versioning sind die am einfachsten zu implementieren. Header-versionsverwaltung ist ein guter Ansatz. Allerdings Header versionsverwaltung nicht als explizite und einfach wie das URI-versionsverwaltung. Da URL versionsverwaltung die einfachste und explizitesten ist, verwendet die beispielanwendung eShopOnContainers URI Versioning.

Mit URI-versionsverwaltung verwendet werden, wie in der beispielanwendung eShopOnContainers bei jedem Ändern der Web-API oder das Schema von Ressourcen ändern, fügen Sie eine Versionsnummer an den URI für jede Ressource hinzu. Vorhandene URIs sollte weiterhin funktionieren wie zuvor, Zurückgeben von Ressourcen, die entsprechen dem Schema die angeforderte Version entspricht.

Wie im folgenden Codebeispiel wird gezeigt, kann die Version mit der Route-Attribut in der Web-API, wodurch die Version in den URI explizit festgelegt werden (in diesem Fall v1).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Dieser Mechanismus für die Versionskontrolle ist einfach und richtet sich nach dem Server die Anforderung an den entsprechenden Endpunkt weiterleiten. Allerdings für eine komplexere versionsverwaltung und die beste Methode, wenn Sie REST verwenden, verwenden Sie Hypermedia und implementieren [HATEOAS (Hypertext als Modul Anwendungsstatus)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Scott Hanselman. ASP.NET Core RESTful-Web-API-versionsverwaltung lassen sich einfach**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

-   **Eine RESTful-Web-API-versionsverwaltung**

    [*https://docs.Microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Versionsverwaltung, Hypermedia und REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Generieren von Swagger-Metadaten mit Beschreibung von Ihrer Web-API von ASP.NET Core 

[Swagger](http://swagger.io/) ist eine häufig verwendete open Source-Framework durch eine große Ökosystem von Tools, mit dem Sie gesichert, Entwurf, Build, Dokument und Ihre Rest-APIs nutzen. Der Standard für die APIs Beschreibung Metadaten-Domäne wird zunehmend. Sie sollten Beschreibung Swagger-Metadaten mit einem beliebigen Microservice, datengesteuerte Microservices oder erweiterte Domain driven Microservices (wie im folgenden Abschnitt erläutert) einschließen.

Das Herzstück des Swagger ist der Swagger-Spezifikation, die API-Beschreibungsmetadaten in JSON oder YAML-Datei ist. Die Spezifikation erstellt die RESTful-Vertrag für Ihre API, über alle Ressourcen und Vorgänge sowohl einem von Menschen und machine readable Format für einfache Entwicklungs-, Discovery und Integration.

Die Spezifikation bildet die Grundlage für die OpenAPI Spezifikation (bei-Zugriff) und entwickelt wird, in eine offene, transparent und gemeinschaftliche Community zu standardisieren, die RESTful-Schnittstellen definiert sind.

Die Spezifikation definiert die Struktur für die wie ein Dienst ermittelt werden kann und wie seine Funktionen verstanden. Weitere Informationen einschließlich einer Web-Editor und Beispiele der Swagger-Spezifikationen von Unternehmen wie sich von Spotify, Uber, Flaute und Microsoft, finden Sie unter der Swagger-Website (<http://swagger.io>).

### <a name="why-use-swagger"></a>Gründe für die Verwendung von Swagger

Gründe zum Generieren von Swagger-Metadaten für Ihre-APIs sind die folgenden.

**Möglichkeit für andere Produkte zu konsumieren und zu integrieren Sie Ihre APIs**. Dutzende von Produkten und [professionellen Tools](http://swagger.io/commercial-tools/) und viele [Bibliotheken und Frameworks](http://swagger.io/open-source-integrations/) Swagger zu unterstützen. Microsoft hat auf hoher Ebene Produkte und Tools, die automatisch Swagger-basierten APIs, wie z. B. die folgenden nutzen können:

-   [AutoRest](https://github.com/Azure/AutoRest). Sie können .NET-Clientklassen für den Aufruf von Swagger automatisch generieren. Dies

-   Tool kann von der CLI verwendet werden, und es Visual Studio auch für die einfache Verwendung über die GUI integriert.

-   [Microsoft Flow](https://flow.microsoft.com/en-us/). Sie können automatisch [verwenden und integrieren Sie Ihre API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) in einen allgemeinen Microsoft Flow-Workflow, ohne Programmierkenntnisse erforderlich.

-   [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/). Können Sie automatisch Ihre API aus nutzen [PowerApps mobilapps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) mit erstellten [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), mit ohne Programmierkenntnisse erforderlich.

-   [Azure App Service-Logik-Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). Sie können automatisch [verwenden und Ihre API in eine Azure App Service-Logik-App integrieren](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), mit ohne Programmierkenntnisse erforderlich.

**Möglichkeit zum automatischen Generieren von API-Dokumentation**. Bei der Erstellung von umfangreichen RESTful-APIs, z. B. komplexe Microservice basierende Anwendungen, müssen Sie viele Endpunkte mit anderen Datenmodellen verwendet werden, in der Anforderung und Antwort-Nutzlasten zu verarbeiten. Müssen die richtige Dokumentation und müssen einen Volltonfarbe API-Explorer aus, wie Sie mit Swagger, erhalten ist der Schlüssel für den Erfolg Ihrer API und die Annahme von Entwicklern.

Die Swagger-Metadaten ist, was Microsoft Flow-, PowerApps und Azure-Logik-Apps verwenden, um zu verstehen, wie Sie APIs verwenden und eine Verbindung mit ihnen herstellen.

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Gewusst wie: Automatisieren der Metadatengenerierung Swagger-API, mit dem Swashbuckle NuGet-Paket

Generieren von Swagger-Metadaten manuell (in JSON oder YAML-Datei) kann aufwändig sein. Allerdings können Sie API-Ermittlung von ASP.NET Web API-Dienste automatisieren, indem Sie mit der [Swashbuckle NuGet-Paket](http://aka.ms/swashbuckledotnetcore) Swagger-API-Metadaten dynamisch zu generieren.

Swashbuckle generiert automatisch Swagger-Metadaten für ASP.NET Web API-Projekte. ASP.NET Core Web-API-Projekte und der herkömmlichen ASP.NET Web-API und weitere Flavor, z. B. Azure-API-App, Azure-Mobile-App, Azure Service Fabric-Microservices basierend auf ASP.NET unterstützt. Sie unterstützt auch einfache Web-API für Container, wie in der Referenz-Anwendung bereitgestellt.

Swashbuckle kombiniert API Explorer und Swagger oder [Swagger-Ui](https://github.com/swagger-api/swagger-ui) bereitstellen, eine umfassende Ermittlung und die Dokumentation für Ihre API-Consumern auftreten. Zusätzlich zu seiner generatormodul der Swagger-Metadaten enthält Swashbuckle auch eine eingebettete Version von Swagger-Ui, das sie automatisch dient Sie nach der Installation von Swashbuckle.

Dies bedeutet, dass Sie Ihre API mit einer nice Ermittlung UI können Entwickler Ihre API verwenden ergänzen können. Da es sich automatisch generiert werden, können Sie den Schwerpunkt auf Ihre API erstellen, muss eine sehr kleine Menge an Code und Wartung. Das Ergebnis für den API Explorer sieht aus wie in Abbildung 8 – 8.

![](./media/image9.png)

**Abbildung 8 – 8**. Swashbuckle-API-Explorer auf der Grundlage von Swagger-Metadaten – eShopOnContainers Katalog Microservice

Die API-Explorer ist nicht der wichtigste hier. Nachdem Sie eine Web-API, die sich in der Swagger-Metadaten beschreiben können haben, kann Ihre API nahtlos aus Swagger-basierte Tools, einschließlich Client-Proxyklasse Code-Generatoren, die auf einer Vielzahl von Plattformen abzielen, können verwendet werden. Wie erwähnt, z. B. [AutoRest](https://github.com/Azure/AutoRest) .NET-Clientklassen automatisch generiert. Jedoch zusätzliche Tools wie [Swagger-Codegen](https://github.com/swagger-api/swagger-codegen) stehen auch zur Verfügung, die Generierung von Client-API-Bibliotheken, Server-Stubs und Dokumentation automatisch zu ermöglichen.

Derzeit Swashbuckle besteht aus zwei NuGet-Pakete: Swashbuckle.SwaggerGen und Swashbuckle.SwaggerUi. Die erste stellt Funktionen bereit, generieren eine oder mehrere Swagger-Dokumente direkt von der API-Implementierung, und richten sie als JSON-Endpunkte. Letzteres stellt eine eingebettete Version von der Swagger-Ui-Tool, das von Ihrer Anwendung bedient werden kann und die von den generierten Swagger-Dokumenten zur Beschreibung Ihrer API ausgeschaltet werden kann. Die neuesten Versionen der Swashbuckle werden jedoch diese durch die Swashbuckle.AspNetCore Metapackage umbrochen.

Beachten Sie, dass Sie .NET Core-Web-API-Projekte verwenden müssen [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) Version 1.0.0 oder höher.

Nachdem Sie diese NuGet-Pakete im Projekt-Web-API installiert haben, müssen Sie Swagger in der Start-Klasse, wie im folgenden Code zu konfigurieren:

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...
        services.AddSwaggerGen();
        services.ConfigureSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SingleApiVersion(new Swashbuckle.Swagger.Model.Info()
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API",
                TermsOfService = "eShopOnContainers terms of service"
            });
        });
        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUi();
    }
}
```

Sobald dies geschehen ist, können Sie die Anwendung starten und Durchsuchen die folgenden Swagger JSON und UI-Endpunkte, mit URLs wie diesen:

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

Sie zuvor gesehen haben, die generierte Benutzeroberfläche von Swashbuckle für eine URL wie http:// erstellt&lt;die Stamm-Url &gt; /Swagger/Benutzeroberfläche. In Abbildung 8 – 9 können Sie auch sehen wie Sie alle API-Methode testen können.

![](./media/image10.png)

**Abbildung 8 – 9**. Swashbuckle UI testen die Katalogelemente/API-Methode

Abbildung 8 bis 10 zeigt die JSON Swagger-Metadaten aus den eShopOnContainers Microservice generiert (Dies ist, was die Tools verwenden, darunter) Wenn Sie anfordern &lt;die Stamm-Url&gt;/swagger/v1/swagger.json mit [Postman](https://www.getpostman.com/).

![](./media/image11.png)

**Abbildung 8 bis 10**. Swagger-JSON-Metadaten

Es ist einfach. Und da er automatisch generiert werden, wächst die Swagger-Metadaten wenn Sie Ihre API weitere Funktionen hinzugefügt.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **API-Hilfe ASP.NET-Webseiten mit Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)


>[!div class="step-by-step"]
[Vorherigen] (Microservice-Anwendung-design.md) [weiter] (multi-container-Anwendungen-Docker-compose.md)
