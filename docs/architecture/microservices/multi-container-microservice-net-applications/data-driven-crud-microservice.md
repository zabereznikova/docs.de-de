---
title: Erstellen eines einfachen datengesteuerten CRUD-Microservice
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Grundlagen der Erstellung eines einfachen CRUD-Microservice (datengesteuert) im Kontext einer Microserviceanwendung.
ms.date: 01/30/2020
ms.openlocfilehash: b72d7defed81e57e2971c5e2b53df2d86b2dc947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77502356"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Erstellen eines einfachen datengesteuerten CRUD-Microservice

Dieser Abschnitt beschreibt das Erstellen eines einfachen Microservice, der Erstell-, Lese-, Aktualisierungs- und Löschvorgänge (CRUD) für eine Datenquelle ausführt.

## <a name="designing-a-simple-crud-microservice"></a>Entwerfen eines einfachen CRUD-Microservice

Aus Entwurfssicht ist diese Art eines Container-Microservice sehr einfach konzipiert. Möglicherweise ist das zu lösende Problem einfach, oder bei der Implementierung handelt es sich nur um ein Proof of Concept.

![Diagramm, das das interne Entwurfsmuster eines einfachen CRUD-Microservice zeigt.](./media/data-driven-crud-microservice/internal-design-simple-crud-microservices.png)

**Abbildung 6-4**. Interner Entwurf für einfache CRUD-Microservices

Ein Beispiel für diese Art eines einfachen datengesteuerten Service ist der Microservice Katalog aus der Beispielanwendung „eShopOnContainers“. Dieser Servicetyp implementiert alle seine Funktionen in einem einzigen ASP.NET Core-Web-API-Projekt, das Klassen für sein Datenmodell, seine Geschäftslogik und seinen Datenzugriffscode enthält. Außerdem speichert er seine zugehörigen Daten in einer Datenbank unter SQL Server (als weiterem Container für Entwicklungs- und Testzwecke), es könnte sich aber wie in Abbildung 6-5 gezeigt auch um einen beliebigen regulären SQL Server-Host handeln.

![Diagramm, das einen datengesteuerten/CRUD-Microservice-Container zeigt.](./media/data-driven-crud-microservice/simple-data-driven-crud-microservice.png)

**Abbildung 6-5**. Einfacher datengesteuerter/CRUD-Microservice-Entwurf

Das vorherige Diagramm zeigt den logischen Katalogmicroservice, der seine Katalogdatenbank enthält, die sich im selben Docker-Host befinden kann. Es kann sich für die Entwicklung, aber nicht für die Produktion eignen, wenn sich die Datenbank im selben Docker-Host befindet. Wenn Sie diese Art von Service entwickeln, benötigen Sie nur [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) und eine Datenzugriffs-API oder eine ORM wie [Entity Framework Core](https://docs.microsoft.com/ef/core/index). Sie könnten ferner, wie im nächsten Abschnitt erläutert, automatisch [Swagger](https://swagger.io/)-Metadaten über [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) generieren, um eine Beschreibung dessen bereitzustellen, was Ihr Service umfasst.

Beachten Sie, dass sich die Ausführung eines Datenbankservers wie SQL Server in einem Docker-Container gut für Entwicklungsumgebungen eignet, da alle Ihre Abhängigkeiten eingerichtet werden können, ohne dass Sie eine Datenbank in der Cloud oder lokal bereitstellen müssen. Dies ist sehr praktisch bei der Durchführung von Integrationstests. Allerdings wird dies für Produktionsumgebungen, die einen Datenbankserver in einem Container ausführen, nicht empfohlen, da Sie mit diesem Ansatz in der Regel keine Hochverfügbarkeit erzielen. Für eine Produktionsumgebung in Azure empfiehlt es sich, Azure SQL DB oder eine andere Datenbanktechnologie zu verwenden, die eine Hochverfügbarkeit und Skalierbarkeit bereitstellen kann. Für einen NoSQL-Ansatz können Sie beispielsweise CosmosDB auswählen.

Und schließlich können Sie durch Bearbeiten der Dockerfile-Datei und der docker-compose.yml-Metadatendateien konfigurieren, wie das Image dieses Containers erstellt wird, d.h. welches Basisimage es verwendet und welche Entwurfseinstellungen wie interne und externe Namen sowie TCP-Ports verwendet werden sollen.

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Implementieren eines einfachen CRUD-Microservice mit ASP.NET Core

Erstellen Sie zum Implementieren eines einfachen CRUD-Microservice mit .NET Core und Visual Studio zunächst wie in Abbildung 6-6 gezeigt ein einfaches ASP.NET Core-Web-API-Projekt (unter .NET Core, sodass es auf einem Linux-Docker-Host ausgeführt werden kann).

![Screenshot von Visual Studio mit der Einrichtung des Projekts.](./media/data-driven-crud-microservice/create-asp-net-core-web-api-project.png)

**Abbildung 6-6**. Erstellen eines ASP.NET Core-Web-API-Projekts in Visual Studio 2019

Wählen Sie zuerst eine ASP.NET Core-Webanwendung und dann den API-Typ aus, um ein ASP.NET Core-Web-API-Projekt zu erstellen. Nach dem Erstellen des Projekts können Sie Ihre MVC-Controller wie in jedem anderen Web-API-Projekt mit der Entity Framework-API oder einer anderen API implementieren. In einem neuen Web-API-Projekt können Sie sehen, dass die einzige Abhängigkeit im betreffenden Microservice ASP.NET Core selbst betrifft. Intern (innerhalb der Abhängigkeit *Microsoft.AspNetCore.All*) verweist diese wie in Abbildung 6-7 gezeigt auf Entity Framework und viele andere .NET Core NuGet-Pakete.

![Screenshot von VS mit den NuGet-Abhängigkeiten von Catalog.API.](./media/data-driven-crud-microservice/simple-crud-web-api-microservice-dependencies.png)

**Abbildung 6-7**. Abhängigkeiten in einem einfachen CRUD-Web-API-Microservice

Das API-Projekt enthält Verweise auf das NuGet-Paket „Microsoft.AspNetCore.App“, das wiederum Verweise auf alle erforderliche Pakete enthält. Einige weitere Pakete können ebenfalls enthalten sein.

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Implementieren von CRUD-Web-API-Services mit Entity Framework Core

Entity Framework Core (EF Core) ist eine einfache, erweiterbare und plattformübergreifende Version der beliebten Entity Framework-Datenzugriffstechnologie. EF Core ist eine objektrelationale Zuordnung (ORM, Object-Relational Mapper), die .NET-Entwicklern mithilfe von .NET-Objekten das Arbeiten mit einer Datenbank ermöglicht.

Der Microservice Katalog verwendet EF und den SQL Server-Anbieter, da seine Datenbank in einem Container mit dem Image SQL Server for Linux Docker ausgeführt wird. Allerdings könnte die Datenbank in einem beliebigen SQL Server wie Windows lokal oder Azure SQL DB bereitgestellt werden. Sie müssten lediglich die Verbindungszeichenfolge im ASP.NET Web API-Microservice ändern.

#### <a name="the-data-model"></a>Das Datenmodell

Bei EF Core erfolgt der Datenzugriff über ein Modell. Ein Modell setzt sich aus Entitätsklassen (Domänenmodell) und einem abgeleiteten Kontext (DbContext) zusammen, der eine Sitzung bei der Datenbank darstellt und Ihnen das Abfragen und Speichern von Daten ermöglicht. Mithilfe des Code-First-Ansatzes können Sie ein Modell aus einer vorhandenen Datenbank generieren, ein Modell manuell anhand Ihrer Datenbank schreiben oder mithilfe von EF-Migrationen eine Datenbank aus Ihrem Modell erstellen (hiermit wird die Entwicklung der Datenbank vereinfacht, während Ihr Modell sich im Laufe der Zeit weiterentwickelt). Für den Microservice Katalog verwenden wir den letztgenannten Ansatz. Das folgende Codebeispiel zeigt die Entitätsklasse CatalogItem. Hierbei handelt es sich um eine einfache POCO-Entitätsklasse ([Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)).

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureFileName { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public int AvailableStock { get; set; }
    public int RestockThreshold { get; set; }
    public int MaxStockThreshold { get; set; }

    public bool OnReorder { get; set; }
    public CatalogItem() { }

    // Additional code ...
}
```

Darüber hinaus benötigen Sie einen DbContext, der eine Sitzung mit der Datenbank darstellt. Für den Microservice Katalog wird die CatalogContext-Klasse von der DbContext-Basisklasse abgeleitet, wie das folgende Beispiel zeigt:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    { }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...
}
```

Zusätzliche `DbContext`-Implementierungen sind möglich. Im als Beispiel dienenden Catalog.API-Microservice gibt es einen zweiten `DbContext` namens `CatalogContextSeed`. Hier werden automatisch die Beispieldaten beim ersten Zugriffsversuch auf die Datenbank aufgefüllt. Diese Methode ist auch für Demodaten und automatische Testszenarios nützlich.

Innerhalb von `DbContext` verwenden Sie die `OnModelCreating`-Methode, um Objekt-/Datenbankentitätszuordnungen und andere [EF-Erweiterungspunkte](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/) anzupassen.

##### <a name="querying-data-from-web-api-controllers"></a>Abfragen von Daten aus Web-API-Controllern

Instanzen Ihrer Entitätsklassen werden üblicherweise – wie im nachstehenden Beispiel gezeigt – mit LINQ (Language Integrated Query) aus der Datenbank abgerufen:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(
        CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService
            ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        context.ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("items")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType(typeof(IEnumerable<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType((int)HttpStatusCode.BadRequest)]
    public async Task<IActionResult> ItemsAsync(
        [FromQuery]int pageSize = 10,
        [FromQuery]int pageIndex = 0,
        string ids = null)
    {
        if (!string.IsNullOrEmpty(ids))
        {
            var items = await GetItemsByIdsAsync(ids);

            if (!items.Any())
            {
                return BadRequest("ids value invalid. Must be comma-separated list of numbers");
            }

            return Ok(items);
        }

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

Daten werden in der Datenbank mithilfe von Instanzen Ihrer Entitätsklassen erstellt, gelöscht und geändert. Sie können Code wie im folgenden hartcodierten Beispiel (in diesem Fall Simulationsdaten) zu Ihren Web-API-Controllern hinzufügen.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Abhängigkeitseinfügung in ASP.NET Core- und Web-API-Controllern

In ASP.NET Core können Sie die vorkonfigurierte Abhängigkeitseinfügung (DI, Dependency Injection) verwenden. Sie müssen keinen IoC-Container (Inversion of Control) eines Drittanbieters einrichten, können aber Ihren bevorzugten IoC-Container in die ASP.NET Core-Infrastruktur einbinden, wenn Sie möchten. In diesem Fall können Sie den erforderlichen EF-DBContext oder zusätzliche Repositorys direkt über den Controller-Konstruktor einfügen.

Im obigen Beispiel für die `CatalogController`-Klasse fügen wir ein Objekt des `CatalogContext`-Typs und andere Objekte über den `CatalogController()`-Konstruktor ein.

Ein wichtiger Konfigurationsschritt bei der Einrichtung des Web-API-Projekts ist die Registrierung der DbContext-Klasse im IoC-Container des Diensts. Hierzu rufen Sie in der Regel in der `Startup`-Klasse die `services.AddDbContext<DbContext>()`-Methode innerhalb der `ConfigureServices()`-Methode auf, wie im folgenden **vereinfachten** Beispiel gezeigt:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.MigrationsAssembly(
                typeof(Startup).GetTypeInfo().Assembly.GetName().Name);

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

- **Abfrage von Daten** \
  [https://docs.microsoft.com/ef/core/querying/index](/ef/core/querying/index)

- **Speichern von Daten** \
  [https://docs.microsoft.com/ef/core/saving/index](/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Die von Docker-Containern verwendete DB-Verbindungszeichenfolge und die Umgebungsvariablen

Wie im folgenden Beispiel gezeigt wird, können Sie die ASP.NET Core-Einstellungen verwenden und eine ConnectionString-Eigenschaft zu Ihrer Datei settings.json hinzufügen:

```json
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

Die Datei settings.json kann Standardwerte für die ConnectionString-Eigenschaft oder für eine andere Eigenschaft enthalten. Diese Eigenschaften werden jedoch durch die Werte der Umgebungsvariablen überschrieben, die Sie in der Datei docker-compose.override.yml angeben, wenn Sie Docker verwenden.

Aus Ihren Dateien „docker-compose.yml“ oder „docker-compose.override.yml“ können Sie diese Umgebungsvariablen initialisieren, damit Docker sie wie in der folgenden Datei „docker-compose.override.yml“ gezeigt als Umgebungsvariablen für das Betriebssystem für Sie einrichtet. (Die Verbindungszeichenfolge und andere Zeilen in diesem Beispiel weisen einen Zeilenumbruch auf, was in Ihrer Datei jedoch nicht der Fall wäre.)

```yml
# docker-compose.override.yml

#
catalog-api:
  environment:
    - ConnectionString=Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

Die docker-compose.yml-Dateien auf der Lösungsebene sind nicht nur flexibler als Konfigurationsdateien auf der Projekt- oder Microservice-Ebene, sondern auch sicherer, wenn Sie die in den docker-compose-Dateien deklarierten Umgebungsvariablen mit Werten überschreiben, die von Ihren Bereitstellungstools (z.B. Azure DevOps Services-Docker-Bereitstellungsaufgaben) festgelegt wurden.

Abschließend können Sie diesen Wert aus Ihrem Code abrufen, indem Sie Configuration\["ConnectionString"\] verwenden, wie es in der ConfigureServices-Methode in einem Codebeispiel weiter oben gezeigt wurde.

Allerdings kann es für Produktionsumgebungen sinnvoll sein, zusätzliche Methoden zu untersuchen, mit denen sich Geheimnisse wie die Verbindungszeichenfolgen speichern lassen. [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) ist eine hervorragende Möglichkeit zum Verwalten von Anwendungsgeheimnissen.

Azure Key Vault dient zum Speichern und Schützen kryptografischer und geheimer Schlüssel, die von Cloudanwendungen und -diensten verwendet werden. Ein Geheimnis ist etwas, das Sie streng überwachen sollten. Es handelt sich dabei z.B. um API-Schlüssel, Verbindungszeichenfolgen, Kennwörter usw. Zu dieser strengen Überwachung gehören *u.a.* die Nutzungsprotokollierung, das Festlegen der Ablaufzeit und das Verwalten des Zugriffs.

Azure Key Vault ermöglicht detaillierte Kontrolle über die Nutzung von Anwendungsgeheimnissen, ohne dass sie jemand kennen muss. Die Geheimnisse können sogar ausgetauscht werden, um die Sicherheit zu erhöhen, ohne Unterbrechung der Entwicklung oder des Betriebs.

Anwendungen müssen in der Active Directory-Instanz Ihres Unternehmens registriert sein, damit sie den Schlüsseltresor verwenden können.

Weitere Informationen finden Sie in der *Dokumentation zu Azure Key Vault*.

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Implementieren einer Versionsverwaltung in ASP.NET Web-APIs

Wenn sich die Geschäftsanforderungen ändern, werden möglicherweise neue Sammlungen von Ressourcen hinzugefügt, die Beziehungen zwischen Ressourcen können sich ändern, und die Struktur der Daten in Ressourcen wird möglicherweise modifiziert. Es ist relativ einfach, eine Web-API zu aktualisieren, damit sie neue Anforderungen verarbeiten kann. Sie müssen jedoch die Auswirkungen berücksichtigen, die derartige Änderungen auf Clientanwendungen haben, die die Web-API nutzen. Zwar hat der Entwickler, der eine Web-API entwirft und implementiert, die vollständige Kontrolle über diese API, er hat allerdings nicht das gleiche Maß an Kontrolle über Clientanwendungen, die möglicherweise von Drittanbietern erstellt werden.

Mit der Versionsverwaltung kann eine Web-API angeben, welche Features und Ressourcen sie bereitstellt. Eine Clientanwendung kann dann Anforderungen an eine bestimmte Version eines Features oder einer Ressource senden. Es gibt verschiedene Methoden für das Implementieren einer Versionsverwaltung:

- URI-Versionsverwaltung

- Abfragezeichenfolgen-Versionsverwaltung

- Header-Versionsverwaltung

Abfragezeichenfolgen- und URI-Versionsverwaltungen lassen sich am einfachsten implementieren. Die Header-Versionsverwaltung ist ein guter Ansatz. Allerdings ist die Header-Versionsverwaltung nicht so explizit und einfach wie die URI-Versionsverwaltung. Da die URI-Versionsverwaltung die einfachste und expliziteste Methode ist, wird sie auch in der Beispielanwendung eShopOnContainers verwendet.

Mit der URI-Versionsverwaltung, die auch in der Beispielanwendung eShopOnContainers verwendet wird, wird bei jeder Änderung der Web-API oder des Ressourcenschemas für jede Ressource eine Versionsnummer zum URI hinzugefügt. Vorhandene URI sollten weiterhin funktionieren wie zuvor und Ressourcen zurückgeben, die dem Schema entsprechen, das mit der angeforderten Version übereinstimmt.

Die Version kann wie im folgenden Codebeispiel mithilfe des Route-Attributs im Web-API-Controller festgelegt werden, wodurch die Version im URI explizit wird (in diesem Fall v1).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Dieser Mechanismus für die Versionsverwaltung ist einfach und richtet sich nach dem Server, der die Anforderung an den entsprechenden Endpunkt weiterleitet. Für eine komplexere Versionsverwaltung und die beste Methode bei der Verwendung von REST sollten Sie jedoch Hypermedia verwenden und [HATEOAS (Hypertext as the Engine Of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources) implementieren.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy (Versionsverwaltung von RESTful-Web-APIs in ASP.NET Core leicht gemacht)**  \
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- **Versionsverwaltung einer RESTful-Web-API** \
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- **Roy Fielding. Versioning, Hypermedia, and REST (Versionsverwaltung, Hypermedia und REST)**  \
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Generieren von Swagger-Beschreibungsmetadaten aus Ihrer ASP.NET Core-Web-API

[Swagger](https://swagger.io/) ist ein häufig verwendetes Open-Source-Framework, hinter dem ein großes Ökosystem von Tools steht, die Sie beim Entwerfen, Erstellen, Dokumentieren und Nutzen Ihrer RESTful-APIs unterstützen. Swagger wird immer mehr zum Standard für die Beschreibungsmetadaten-Domäne von APIs. Wie im folgenden Abschnitt erläutert wird, sollten Sie Swagger-Beschreibungsmetadaten in sämtliche Arten von Microservices integrieren, d.h. sowohl in datengesteuerte Microservices als auch in komplexere domänengesteuerte Microservices.

Das Herzstück von Swagger ist die Swagger-Spezifikation, bei der es sich um API-Beschreibungsmetadaten in einer JSON- oder YAML-Datei handelt. Die Spezifikation erstellt den RESTful-Vertrag für Ihre API und legt die Details zu allen ihren Ressourcen und Vorgängen in einem visuell lesbaren und einem maschinenlesbaren Format für einfache Entwicklungs-, Ermittlungs- und Integrationsvorgänge fest.

Die Spezifikation bildet die Grundlage für die OpenAPI Specification (OAS) und wird in einer offenen, transparenten und vernetzten Community entwickelt, um das Definieren von RESTful-Schnittstellen zu standardisieren.

Die Spezifikation definiert die Struktur, wie ein Service ermittelt werden kann und wie seine Funktionen interpretiert werden. Weitere Informationen, einschließlich eines Web-Editors und Beispielen für Swagger-Spezifikationen von Firmen wie Spotify, Uber, Slack und Microsoft finden Sie auf der Webseite von Swagger (<https://swagger.io>).

### <a name="why-use-swagger"></a>Gründe für die Verwendung von Swagger

Im Folgenden werden die wichtigsten Gründe für das Generieren von Swagger-Metadaten für Ihre-APIs genannt.

**Möglichkeit für andere Produkte, Ihre APIs automatisch zu nutzen und zu integrieren**. Dutzende von Produkten und [kommerziellen Tools](https://swagger.io/commercial-tools/) sowie viele [Bibliotheken und Frameworks](https://swagger.io/open-source-integrations/) unterstützen Swagger. Microsoft verfügt beispielsweise über die folgenden allgemeinen Produkte und Tools, die automatisch Swagger-basierte APIs nutzen können:

- [AutoRest](https://github.com/Azure/AutoRest). Sie können automatisch .NET-Clientklassen für den Aufruf von Swagger generieren. Dieses Tool kann von der CLI verwendet werden und integriert auch Visual Studio für eine benutzerfreundliche Verwendung über die GUI.

- [Microsoft Flow](https://flow.microsoft.com/). Ermöglicht die automatische [Verwendung und Integration Ihrer API](https://flow.microsoft.com/blog/integrating-custom-api/) in einen allgemeinen Workflow von Microsoft Flow, ohne dass hierzu Programmierkenntnisse erforderlich sind.

- [Microsoft PowerApps](https://powerapps.microsoft.com/). Sie können automatisch Ihre API aus [mobilen PowerApps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) nutzen, die mit [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/) erstellt wurden, ohne dass hierzu Programmierkenntnisse erforderlich sind.

- [Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). Sie können automatisch [Ihre API verwenden und in eine Azure App Service Logic App integrieren](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), ohne dass hierzu Programmierkenntnisse erforderlich sind.

**Möglichkeit zum automatischen Generieren einer API-Dokumentation**. Bei der Erstellung umfangreicher RESTful-APIs wie komplexen auf Microservices basierenden Anwendungen müssen Sie zahlreiche Endpunkte mit unterschiedlichen Datenmodellen berücksichtigen, die in den Anforderungs- und Antwortnutzlasten verwendet werden. Über die richtige Dokumentation und einen gut funktionierenden API-Explorer zu verfügen (wie es mit Swagger der Fall ist), ist der Schlüssel für den Erfolg Ihrer API und deren Annahme durch die Entwickler.

Microsoft Flow, PowerApps und Azure Logic Apps verwenden die Metadaten von Swagger, um zu verstehen, wie APIs verwendet werden und die Verbindung zu ihnen hergestellt wird.

Es gibt mehrere Optionen zum Automatisieren der Swagger-Metadatengenerierung für ASP.NET Core-REST-API-Anwendungen in Form von auf *swagger-ui* basierenden funktionalen API-Hilfeseiten.

Die wohl bekannteste Option ist [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), was derzeit in [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) verwendet wird und in diesem Leitfaden genauer erläutert wird. Es steht aber auch [NSwag](https://github.com/RSuter/NSwag) zur Verfügung, womit Typescript- und C\#-API-Clients sowie C\#-Controller aus einer Swagger- oder OpenAPI-Spezifikation und auch durch Scannen der DLL-Datei mit [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio), die die Controller enthält, generiert werden können.

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Automatisieren der API-Swagger-Metadatengenerierung mit dem Swashbuckle-NuGet-Paket

Das manuelle Generieren von Swagger-Metadaten (in einer JSON- oder YAML-Datei) kann aufwendig sein. Sie können jedoch die API-Ermittlung von ASP.NET Web-API-Diensten automatisieren, indem Sie das [Swashbuckle-NuGet-Paket](https://aka.ms/swashbuckledotnetcore) verwenden, um Swagger-API-Metadaten dynamisch zu generieren.

Swashbuckle generiert automatisch Swagger-Metadaten für Ihre ASP.NET Web-API-Projekte. Es unterstützt neben ASP.NET Core-Web-API-Projekten und der traditionellen ASP.NET-Web-API auch Azure API App-, Azure Mobile App- und Azure Service Fabric-Microservices auf Basis von ASP.NET. Es unterstützt ferner eine einfache Web-API für Container, wie sie in der Beispielanwendung bereitgestellt wird.

Swashbuckle kombiniert API Explorer und Swagger oder [swagger-ui](https://github.com/swagger-api/swagger-ui), um Ihren API-Nutzern eine umfassende Ermittlungs- und Dokumentationserfahrung zu bieten. Zusätzlich zu seiner Engine für die Swagger-Metadatengenerierung umfasst Swashbuckle auch eine eingebettete Version von swagger-ui, die nach der Installation von Swashbuckle automatisch bereitsteht.

Dies bedeutet, dass Sie Ihre API um eine benutzerfreundliche Ermittlungs-UI ergänzen können, die es Entwicklern leichter macht, Ihre API zu verwenden. Da aufgrund der automatischen Generierung nur sehr wenig Code benötigt wird und der Wartungsaufwand gering ist, können Sie sich auf die Erstellung Ihrer API konzentrieren. Abbildung 6-8 zeigt das Ergebnis für den API Explorer.

![Screenshot des Swagger-API-Explorers mit der eShopOContainers-API.](./media/data-driven-crud-microservice/swagger-metadata-eshoponcontainers-catalog-microservice.png)

**Abbildung 6-8**. Swashbuckle API Explorer auf Basis von Swagger-Metadaten – Microservice Katalog von eShopOnContainers

Die von Swashbuckle generierte Dokumentation der Swagger-Benutzeroberflächen-API enthält alle veröffentlichten Aktionen Der API Explorer hat hierbei nicht den höchsten Stellenwert. Sobald Sie über eine Web-API verfügen, die sich selbst in Swagger-Metadaten beschreiben kann, kann Ihre API nahtlos von Swagger-basierten Tools verwendet werden, einschließlich Client-Proxy-Klassencodegeneratoren, die für eine Vielzahl von Plattformen geeignet sind. Wie bereits erwähnt wurde, generiert beispielsweise [AutoRest](https://github.com/Azure/AutoRest) automatisch .NET-Clientklassen. Es stehen jedoch zusätzliche Tools wie [swagger-codegen](https://github.com/swagger-api/swagger-codegen) zur Verfügung, die eine automatische Codegenerierung von API-Client-Bibliotheken, Server-Stubs und Dokumentation ermöglichen.

Derzeit besteht Swashbuckle aus fünf NuGet-Paketen im allgemeinen Metapaket [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) für ASP.NET Core-Anwendungen.

Nachdem Sie diese NuGet-Pakete in Ihrem Web-API-Projekt installiert haben, müssen Sie Swagger wie im folgenden **vereinfachten** Code gezeigt in der Startup-Klasse konfigurieren:

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...

        // Add framework services.
        services.AddSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SwaggerDoc("v1", new OpenApiInfo
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample"
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
            .UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
            });
    }
}
```

Anschließend können Sie Ihre Anwendung starten und die folgenden JSON- und UI-Endpunkte von Swagger mit URLs wie den folgenden durchsuchen:

```console
  http://<your-root-url>/swagger/v1/swagger.json

  http://<your-root-url>/swagger/
```

Die von Swashbuckle generierte UI für eine URL wie `http://<your-root-url>/swagger` wurde bereits oben gezeigt. In Abbildung 6-9 sehen Sie nun auch, wie Sie eine beliebige API-Methode testen können.

![Screenshot der Swagger-Benutzeroberfläche mit verfügbaren Testtools.](./media/data-driven-crud-microservice/swashbuckle-ui-testing.png)

**Abbildung 6-9**. Testen einer Swashbuckle-UI mit der API-Methode Katalog/Elemente

Die Detailansicht der Swagger-Benutzeroberflächen-API zeigt ein Beispiel der Antwort an und kann zum Ausführen der tatsächlichen API verwendet werden, was hilfreich für den Entwickler ist. Abbildung 6-10 zeigt die JSON-Metadaten von Swagger, die vom Microservice eShopOnContainers generiert werden (den die Tools im Hintergrund verwenden), wenn Sie `http://<your-root-url>/swagger/v1/swagger.json` mit [Postman](https://www.getpostman.com/) anfordern.

![Screenshot einer Postman-Beispielbenutzeroberfläche mit JSON-Metadaten von Swagger.](./media/data-driven-crud-microservice/swagger-json-metadata.png)

**Abbildung 6-10**. JSON-Metadaten von Swagger

Es ist wirklich so einfach. Und da die Generierung automatisch erfolgt, wachsen Ihre Swagger-Metadaten mit, wenn Sie weitere Funktionen zu Ihrer API hinzufügen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **ASP.NET-Web-API-Hilfeseiten mit Swagger** \
  [https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger](/aspnet/core/tutorials/web-api-help-pages-using-swagger)

- **Erste Schritte mit Swashbuckle und ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle](/aspnet/core/tutorials/getting-started-with-swashbuckle)

- **Erste Schritte mit NSwag und ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag](/aspnet/core/tutorials/getting-started-with-nswag)

> [!div class="step-by-step"]
> [Zurück](microservice-application-design.md)
> [Weiter](multi-container-applications-docker-compose.md)
