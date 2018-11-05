---
title: Arbeiten mit Daten in ASP.NET Core-Apps
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Arbeiten mit Daten in ASP.NET Core-Apps
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: 069bfacd1ae08b5c84d6e304b2f12f18e1eecb22
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49122850"
---
# <a name="working-with-data-in-aspnet-core-apps"></a>Arbeiten mit Daten in ASP.NET Core-Apps

> „Daten sind ein wertvolles Gut und werden länger erhalten bleiben als die Systeme.“
>
> Tim Berners-Lee

Der Datenzugriff stellt in beinahe allen Softwareanwendungen einen wichtigen Bestandteil dar. ASP.NET Core unterstützt verschiedene Datenzugriffsoptionen, einschließlich Entity Framework Core und Entity Framework 6, sowie alle .NET-Frameworks für den Datenzugriff. Welches Framework für den Datenzugriff verwendet werden soll, hängt von den Anforderungen der jeweiligen App ab. Wenn Sie die Auswahlmöglichkeiten aus ApplicationCore und Benutzeroberflächenprojekten zusammenfassen und Informationen zur Implementierung in der Infrastruktur kapseln, können sie loser gekoppelte, testbare Software erstellen.

## <a name="entity-framework-core-for-relational-databases"></a>Entity Framework Core (für relationale Datenbanken)

Wenn Sie eine neue ASP.NET Core-Anwendung programmieren, die mit relationalen Datenbanken zusammenarbeiten muss, wird die Verwendung von Entity Framework Core (EF Core) empfohlen, damit die Anwendung auf ihre Daten zugreifen kann. EF Core ist eine objektrelationale Zuordnung (Object-Relational Mapper, O/RM), die es .NET-Entwicklern ermöglicht, Objekte aus Datenquellen zu entnehmen oder diesen hinzuzufügen. In EF Core ist der Großteil des Datenzugriffscodes, den Entwickler in der Regel schreiben müssen, nicht mehr erforderlich. Ähnlich wie ASP.NET Core wurde auch EF Core von Grund auf neu erstellt, um modulare plattformübergreifende Anwendungen zu unterstützen. Sie fügen den Dienst als NuGet-Paket zu Ihrer Anwendung hinzu, konfigurieren dieses beim Start und fordern es wenn nötig über Dependency Injection an.

Wenn Sie EF Core mit einer SQL Server-Datenbank verwenden möchten, führen Sie den folgenden Dotnet-CLI-Befehl aus:

dotnet add package Microsoft.EntityFrameworkCore.SqlServer

Führen Sie den folgenden Befehl zum Testen aus, wenn Sie Unterstützung für eine InMemory-Datenquelle hinzufügen möchten:

dotnet add package Microsoft.EntityFrameworkCore.InMemory

### <a name="the-dbcontext"></a>DbContext

Sie benötigen zum Arbeiten mit EF Core eine Unterklasse von <xref:Microsoft.EntityFrameworkCore.DbContext>. Diese Klasse enthält Eigenschaften, die Auflistungen der Entitäten darstellt, mit denen Ihre Anwendung arbeiten soll. Das eShopOnWeb-Beispiel umfasst CatalogContext mit Auflistungen für Elemente, Marken und Typen:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

DbContext muss über einen Konstruktor verfügen, der DbContextOptions akzeptiert und dieses Argument an den Basiskonstruktor „DbContext“ übergibt. Beachten Sie, dass Sie nur eine DbContextOptions-Instanz übergeben können, wenn Sie nur über ein DbContext-Element in Ihrer Anwendung verfügen. Wenn es allerdings mehrere Elemente sind, müssen Sie den generischen DbContextOptions<T>-Typ verwenden, der Ihren DbContext-Typ als generischen Parameter übergibt.

### <a name="configuring-ef-core"></a>Konfigurieren von EF Core

In Ihrer ASP.NET Core-Anwendung konfigurieren Sie in der Regel EF Core in Ihrer ConfigureServices-Methode. EF Core verwendet ein DbContextOptionsBuilder-Element, das mehrere nützliche Erweiterungsmethoden unterstützt, um seine Konfiguration zu optimieren. Zum Konfigurieren von CatalogContext zur Verwendung einer SQL Server-Datenbank mit einer in der Konfiguration definierten Verbindungszeichenfolge sollten Sie den folgenden ConfigureServices-Code verwenden:

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

Zur Verwendung in der In-Memory-Datenbank:

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

Nachdem Sie EF Core installiert, einen untergeordneten DbContext-Typ erstellt und diesen in ConfigureServices konfiguriert haben, können Sie EF Core verwenden. Sie können in jedem Dienst, der eine Instanz Ihres DbContext-Typs benötigt, diese anfordern und damit beginnen, mit Ihren gespeicherten Entitäten unter Verwendung von LINQ so zu arbeiten, als würden diese sich nur in einer Auflistung befinden. EF Core übersetzt Ihre LINQ-Ausdrücke dann in SQL-Abfragen, um Ihre Daten zu speichern und abzurufen.

Sie können wie in Abbildung 8–1 dargestellt die Abfragen abrufen, die EF Core ausführt, indem Sie eine Protokollierung konfigurieren und sicherstellen, dass diese mindestens auf „Information“ festgelegt ist.

![](./media/image8-1.png)

Abbildung 8–1: Protokollieren von EF Core-Abfragen an die Konsole

### <a name="fetching-and-storing-data"></a>Abrufen und Speichern von Daten

Greifen Sie zum Abrufen von Daten aus EF Core auf eine passende Eigenschaft zu, und verwenden Sie LINQ, um das Ergebnis zu filtern. Außerdem können Sie LINQ verwenden, um eine Projektion durchzuführen, indem Sie das Ergebnis von einem Typ in einen anderen umwandeln. Über das folgende Beispiel werden CatalogBrands-Elemente abgerufen, die nach Namen sortiert und anhand der Eigenschaft „Enabled“ (Aktiviert) sortiert sind und auf einen SelectListItem-Typ projiziert werden:

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

Im obenstehenden Beispiel ist es wichtig, dass der Aufruf zu ToListAsync hinzugefügt wird, um die Abfrage ohne Umschweife auszuführen. Andernfalls weist die Anweisung ein IQueryable<SelectListItem>-Element brandItems-Elementen zu, die erst ausgeführt werden, nachdem dieses aufgeführt wurde. Das Zurückgeben von IQueryable-Ergebnissen aus Methoden hat sowohl Vorteile als auch Nachteile. Auf der einen Seite kann die Abfrage, die EF Core erstellt, dadurch weiter verändert werden. Auf der anderen Seite können dadurch auch Fehler entstehen, die nur zur Laufzeit entstehen, wenn zu der Abfrage Vorgänge hinzugefügt werden, die EF Core nicht übersetzen kann. In der Regel ist es sicherer, Filter an die Methode zu übergeben, die den Datenzugriff durchführt und eine In-Memory-Auflistung (z.B. List<T>) als Ergebnis zurückzugeben.

EF Core verfolgt Änderungen an Entitäten nach, die aus dem Persistenzspeicher abgerufen werden. Wenn Sie Änderungen an einer nachverfolgten Entität speichern möchten, rufen Sie einfach die SaveChanges-Methode für das DbContext-Element ab, und stellen Sie dabei sicher, dass es sich um die DbContext-Instanz handelt, die auch verwendet wurde, um die Entität abzurufen. Das Hinzufügen und Entfernen von Entitäten geschieht direkt über die entsprechende DbSet-Eigenschaft, während gleichzeitig SaveChanges aufgerufen wird, um die Datenbankbefehle auszuführen. Im folgenden Beispiel wird dargestellt, wie Sie Entitäten zum Persistenzspeicher hinzufügen, diese darin aktualisieren und aus ihm entfernen.

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

EF Core unterstützt sowohl synchrone als auch asynchrone Methoden zum Abrufen und Speichern. In Webanwendungen wird empfohlen, das Async/Await-Muster mit der Async-Methode zu verwenden, damit keine Webserverthreads blockiert werden, während darauf gewartet wird, dass Datenzugriffsvorgänge abgeschlossen werden.

### <a name="fetching-related-data"></a>Abrufen zugehöriger Daten

Wenn EF Core Entitäten abruft, werden alle Eigenschaften aufgefüllt, die direkt mit dieser Entität in der Datenbank gespeichert werden. Navigationseigenschaften wie Listen mit verknüpften Entitäten werden nicht aufgefüllt, und ihr Wert ist möglicherweise auf NULL festgelegt. Dadurch wird sichergestellt, dass EF Core nicht mehr Daten abruft als nötig. Dies ist besonders wichtig für Webanwendungen, die schnell Anforderungen verarbeiten und auf effiziente Weise Antworten zurückgeben müssen. Geben Sie wie im Folgenden dargestellt unter Verwendung der Erweiterungsmethode „Include“ bei der Abfrage die Eigenschaft an, um über _Eager Loading_ Beziehungen zu einer Entität hinzuzufügen:

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

Sie können unter Verwendung von ThenInclude mehrere Beziehungen sowie untergeordnete Beziehungen hinzufügen. EF Core führt dann eine einzelne Abfrage aus, um die daraus entstehenden Entitäten abzurufen.

Sie können auch das _explizite Laden_ verwenden, um verknüpfte Daten zu laden. Beim expliziten Laden können Sie zusätzliche Daten in eine Entität laden, die bereits abgerufen wurde. Da dies eine separate Anforderung an die Datenbank umfasst, wird dies nicht für Webanwendungen empfohlen, die die Anzahl von Datenbankroundtrips pro Anforderung reduzieren sollen.

Beim _verzögerten Laden_ handelt es sich um ein Feature, das automatisch verknüpfte Daten lädt, wenn die Anwendung auf dieses verweist. EF Core Version 2.1 unterstützt verzögertes Laden. Verzögertes Laden ist standardmäßig deaktiviert und erfordert die Installation von `Microsoft.EntityFrameworkCore.Proxies`. Ähnlich wie das explizite Laden sollte das verzögerte Laden in der Regel für Webanwendungen deaktiviert sein, da dessen Verwendung zu zusätzlichen Datenbankabfragen in jeder Webanforderung führt. Der vom verzögerten Laden verursachte zeitliche Mehraufwand wird zur Entwicklungszeit oft nicht beachtet, wenn die Wartezeit kurz ist und die für die Tests verwendeten Datasets klein sind. Allerdings können die zusätzlichen Datenbankanforderungen oft zu schlechter Leistung bei Webanwendungen führen, die intensiven Gebrauch vom verzögerten Laden machen, da in der Produktion mehr Benutzer sowie Daten vorhanden sind und höhere Wartezeiten auftreten.

[Avoid Lazy Loading Entities in Web Applications (Vermeiden von verzögertem Laden von Entitäten in Webanwendungen)](https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications)

### <a name="resilient-connections"></a>Robuste Verbindungen

Es kann sein, dass externe Ressourcen wie SQL-Datenbanken zeitweise nicht verfügbar sind. Wenn es zu einem temporären Ausfall kommen sollte, können Anwendungen die Wiederholungslogik verwenden, damit keine Ausnahmen ausgelöst werden. Diese Technik wird als _Verbindungsresilienz_ bezeichnet. Sie können Ihre eigene Technik für [Wiederholungen mit exponentiellem Backoff verwenden](https://docs.microsoft.com/azure/architecture/patterns/retry), indem Sie so viele Wiederholungen durchführen, bis die maximale Anzahl von möglichen Wiederholungen erreicht ist, und dabei die Wartezeit zwischen den einzelnen Wiederholungen immer weiter ausdehnen. Diese Technik berücksichtigt den Umstand, dass Cloudressourcen zeitweise nicht verfügbar sein können, wodurch einige Anforderungen fehlschlagen.

Entity Framework Core bietet bereits interne Datenbankverbindungsresilienz und Wiederholungslogik für Azure SQL DB. Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede DbContext-Verbindung aktivieren, wenn Sie robuste EF Core-Verbindungen erzielen wollen.

Zum Beispiel aktiviert der folgende Code auf der EF Core-Verbindungsebene robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.EnableRetryOnFailure(
            maxRetryCount: 5,
            maxRetryDelay: TimeSpan.FromSeconds(30),
            errorNumbersToAdd: null);
        });
    });
}
//...
```

#### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Ausführungsstrategien und explizite Transaktionen mit „BeginTransaction“ und mehreren DbContext-Objekten

Wenn Wiederholungen in EF Core-Verbindungen aktiviert sind, wird jeder Vorgang, den Sie mit EF Core durchführen, zu einem individuell wiederholbaren Vorgang. Jede Abfrage und jeder Aufruf von „SaveChanges“ wird als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.

Wenn Ihr Code jedoch eine Transaktion mit „BeginTransaction“ ausführt, definieren Sie Ihre eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen. Alles innerhalb dieser Transaktion wird zurückgesetzt, wenn ein Fehler auftritt. Eine Ausnahme wie die Folgende wird angezeigt, wenn Sie versuchen, diese Transaktion auszuführen, wenn Sie die EF-Ausführungsstrategie verwenden (Wiederholungsrichtlinie) und der Transaktion mehrere SaveChanges-Elemente von mehreren DbContext-Objekten hinzufügen.

System.InvalidOperationException: Die konfigurierte Ausführungsstrategie „SqlServerRetryingExecutionStrategy“ unterstützt keine vom Benutzer instanziierten Transaktionen. Verwenden Sie die Ausführungsstrategie, die von „DbContext.Database.CreateExecutionStrategy()“ zurückgegeben wird, um alle Vorgänge in der Transaktion als wiederholbare Einheit auszuführen.

Die Lösung ist, die EF-Ausführungsstrategie mit einem Delegaten manuell aufzurufen, der alle Komponenten darstellt, die ausgeführt werden müssen. Die Ausführungsstrategie ruft den Delegaten erneut auf, wenn ein vorübergehender Fehler auftritt. Im folgenden Codebeispiel wird die Implementierung dieses Ansatzes veranschaulicht:

```csharp
// Use of an EF Core resiliency strategy when using multiple DbContexts
// within an explicit transaction
// See:
// https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
var strategy = _catalogContext.Database.CreateExecutionStrategy();
await strategy.ExecuteAsync(async () =>
{
    // Achieving atomicity between original Catalog database operation and the
    // IntegrationEventLog thanks to a local transaction
    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);
        await _catalogContext.SaveChangesAsync();

        // Save to EventLog only if product price changed
        if (raiseProductPriceChangedEvent)
        await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
    }
});
```

Das erste DbContext-Objekt ist \_catalogContext und das zweite befindet sich im Objekt \_integrationEventLogService. Zum Schluss wird die Commitaktion unter Verwendung einer EF-Ausführungsstrategie für mehrere DbContext-Objekte ausgeführt.

> ### <a name="references--entity-framework-core"></a>Ressourcen: Entity Framework Core
>
> - **EF Core-Dokumentation**  
>   <https://docs.microsoft.com/ef/>
> - **EF Core: Related Data (EF Core: Verknüpfte Daten)**  
>   <https://docs.microsoft.com/ef/core/querying/related-data>
> - **Avoid Lazy Loading Entities in ASPNET Applications (Vermeiden von verzögertem Laden von Entitäten in ASP.NET-Anwendungen)**  
>   <https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications>

## <a name="ef-core-or-micro-orm"></a>EF Core oder Mikro-ORM?

EF Core eignet sich gut zum Verwalten der Persistenz und kapselt vor allem die von Anwendungsentwicklern bereitgestellten Datenbankinformationen. Es gibt hierfür jedoch auch andere Möglichkeiten. [Dapper](https://github.com/StackExchange/Dapper) ist z.B. eine Open-Source-Alternative, die häufig verwendet wird. Dabei handelt es sich um eine Mikro-ORM. Bei einer Mikro-ORM handelt es sich um ein Tool mit allen Features, die zum Zuordnen von Objekten zu Datenstrukturen benötigt werden. Bei Dapper hat man sich vor allem auf das Thema Leistung konzentriert, anstatt die zugrunde liegenden Abfragen, die verwendet werden, um Daten abzurufen und zu aktualisieren, vollständig zu kapseln. Da Dapper SQL nicht vom Entwickler abstrahiert, kann dieser sich mehr an der Hardware orientierten und genau die Abfragen schreiben, die er für einen bestimmten Vorgang zum Zugreifen auf Daten verwenden möchte.

EF Core enthält zwei wichtige Features, durch die sich dieses Tool zwar von Dapper unterscheidet, die aber gleichzeitig den Leistungsaufwand erhöhen. Das eine Feature ist dafür zuständig, LINQ-Ausdrücke in SQL zu übersetzen. Diese Übersetzungen werden zwar zwischengespeichert, aber es ist trotzdem sehr aufwändig, wenn sie das erste Mal erstellt werden müssen. Das andere Feature ist dafür zuständig, Änderungen an Entitäten nachzuverfolgen, damit effiziente Updateanweisungen generiert werden können. Dieses Verhalten kann für bestimmte Abfragen mit der AsNotTracking-Erweiterung deaktiviert werden. Außerdem generiert EF Core SQL-Abfragen, die sehr effizient sind und kein zu hohes Maß an Leistung erfordern. Wenn Sie zudem die Abfragen, die ausgeführt werden sollen, genau steuern möchten, können Sie auch benutzerdefinierte SQL-Elemente hinzufügen oder eine gespeicherte Prozedur mit EF Core ausführen. In diesem Szenario ist Dapper im Hinblick auf die Leistung zwar nützlicher als EF Core, aber der Unterschied ist nur gering. Julie Lerman führt in Ihrem MSDN-Artikel mit dem Titel [Datenpunkte – Dapper, Entity Framework und Hybrid-Apps](https://msdn.microsoft.com/magazine/mt703432.aspx) vom Mai 2016 einige Leistungsdaten auf. Außerdem finden Sie auf der [Dapper-Website](https://github.com/StackExchange/Dapper) zusätzliche Vergleichsdaten zur Leistung für verschiedene Datenzugriffsmethoden.

Wenn Sie sehen möchten, wie sich die Dapper-Syntax von der EF Core-Syntax unterscheidet, können Sie auf zwei unterschiedliche Versionen einer Methode zurückgreifen, die eine Liste von Elementen abruft:

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

Wenn Sie komplexere Objektgraphen mit Dapper erstellen möchten, müssen Sie die jeweiligen Abfragen selbst erstellen. Im Gegensatz dazu müssen Sie in EF Core nur ein Include-Element hinzufügen. Sie können zum Erstellen dieser Graphen verschiedene Syntaxmöglichkeiten verwenden, z.B. ein sogenanntes Multi Mapping-Feature, über das Sie mehreren zugeordneten Objekten einzelne Zeilen zuordnen können. Angenommen, Sie verfügen über eine Post-Klasse mit einer Owner-Eigenschaft des User-Typs. Dann gibt das folgende SQL-Element alle notwendigen Daten zurück:

```sql
select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id
```

Jede zurückgegebene Zeile umfasst sowohl User- als auch Post-Daten. Da die User-Daten über die Owner-Eigenschaft an die Post-Daten angefügt werden sollten, wird die folgende Funktion verwendet:

```csharp
(post, user) => { post.Owner = user; return post; }
```

Im Folgenden wird die vollständig Codeliste dargestellt, über die eine Auflistung von Post-Daten mit der jeweiligen Owner-Eigenschaft, die mit den zugewiesenen User-Daten aufgefüllt ist, zurückgegeben werden kann:

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

Da Entwickler im Zusammenhang mit Dapper weniger Kapselungen vornehmen müssen, ist es erforderlich, dass diese wissen, wie ihre Daten gespeichert werden, wie sie diese effizient abfragen können und wie sie mehr Code schreiben können, um diese Daten abzurufen. Wenn das Modell verändert wird, darf nicht bloß eine neue Migration erstellt werden (ein anderes EF Core-Feature) und/oder Informationen einem Ort in DbContext zugeordnet werden. Stattdessen muss jede Abfrage, die betroffen ist, aktualisiert werden. Für diese Abfragen gibt es keine Garantien hinsichtlich der Kompilierzeit – das kann zur Laufzeit zu Unterbrechungen führen, wenn Änderungen an dem Modell oder der Datenbank vorgenommen werden, sodass es schwieriger wird, Fehler direkt zu ermitteln. Nichtsdestotrotz bietet Dapper eine schnelle Leistung.

Sowohl für die meisten Anwendungen als auch für die meisten Bestandteile von Anwendungen bietet EF Core eine akzeptable Leistung. Somit sind die Vorteile hinsichtlich der Leistung für Entwickler größer als die durch den Leistungsaufwand entstehenden Nachteile. Bei Abfragen, die von Zwischenspeicherungen profitieren können, beansprucht die eigentliche Abfrage nur wenig Zeit, wodurch kleine Unterschiede hinsichtlich der Abfrageleistung nur in der Theorie einen Unterschied machen.

## <a name="sql-or-nosql"></a>SQL und NoSQL im Vergleich

In der Regel werden vorzugsweise relationale Datenbanken wie SQL Server als beständige Datenspeicher verwendet. Es gibt jedoch auch noch andere Möglichkeiten. Beispielsweise bieten NoSQL-Datenbanken wie [MongoDB](https://www.mongodb.com/what-is-mongodb) eine andere Möglichkeit zum Speichern von Objekten. Sie müssen nicht unbedingt Tabellen oder Zeilen Objekten zuordnen, sondern können auch den vollständigen Objektgraphen serialisieren und das Ergebnis speichern. Dieser Ansatz ist, zumindest auf den ersten Blick, einfacher anzuwenden und hat positive Auswirkungen auf die Leistung. Natürlich ist es einfacher, ein serialisiertes Objekt mit einem Schlüssel zu speichern, als das Objekt in mehrere Tabellen zu zerlegen, die in Beziehung miteinander stehen und aktualisiert werden müssen. Dabei kann es nämlich sein, dass Änderungen an den einzelnen Zeilen vorgenommen wurden, nachdem das Objekt zum letzten Mal aus der Datenbank abgerufen wurde. Gleichzeitig ist das Abrufen und Deserialisieren eines einzelnen Objekts aus einem schlüsselbasiertem Speicher viel einfacher und schneller als bei komplizierten Verknüpfungen oder mehreren Datenbankabfragen, die erforderlich sind, um dieses Objekt vollständig aus einer relationalen Datenbank herzustellen. Im Zusammenhang mit NoSQL-Datenbanken gibt es keine Sperren, Transaktionen oder festgelegte Schemata, wodurch die Skalierung für mehrere Computer, die sehr große Datenbanken unterstützen, einfacher wird.

Trotzdem haben NoSQL-Datenbanken auch Nachteile. Relationale Datenbanken verwenden das Prinzip der Normalisierung, um Konsistenz zu erzwingen und zu vermeiden, dass Daten dupliziert werden. Dadurch wird die Gesamtgröße der Datenbank reduziert und sichergestellt, dass Updates von freigegebenen Daten unmittelbar nach deren Freigabe auch für die gesamte Datenbank verfügbar sind. In einer relationalen Datenbank kann es vorkommen, dass eine Tabelle mit Adressen mithilfe einer ID auf eine Tabelle mit Ländern verweist. Wenn dann der Name eines Landes geändert wird, profitiert die Tabelle mit den Adressen zwar auch davon, muss aber an sich nicht aktualisiert werden. Dann kann es hingegen sein, dass die Adresse und das zugehörige Land in einer NoSQL-Datenbank als Bestandteile vieler gespeicherter Objekte serialisiert werden. Wenn ein Update für einen Ländernamen ausgeführt wird, muss nicht nur eine Zeile aktualisiert werden, sondern all diese Objekte. Relationale Datenbanken können auch die relationale Integrität gewährleisten, indem sie Regeln wie Fremdschlüssel erzwingen. NoSQL-Datenbanken bieten solche Einschränkungen für ihre Daten in der Regel nicht.

Außerdem muss im Zusammenhang mit NoSQL-Datenbanken der komplizierte Aspekt der Versionsverwaltung beachtet werden. Wenn sich die Eigenschaften eines Objekts ändern, kann es sein, dass dieses nicht aus früheren gespeicherten Versionen deserialisiert werden kann. Daher müssen alle vorhandenen Objekte, die über eine serialisierte (Vorgänger-)Version des Objekts verfügen, aktualisiert werden, damit sie dem neuen Schema entsprechen. Dieses Konzept unterscheidet sich von der Vorgehensweise bei relationalen Datenbanken, denn in diesem Zusammenhang erfordern Schemaänderungen häufig die Aktualisierung von Skripts oder das Zuordnen von Updates. Die Anzahl von Einträgen, die geändert werden müssen, ist jedoch beim NoSQL-Ansatz häufig viel höher, da mehr Daten dupliziert werden.

In NoSQL-Datenbanken ist es möglich, mehrere Versionen von Objekten zu speichern. Dies wird von relationalen Datenbanken mit festem Schema in der Regel nicht unterstützt. In diesem Fall muss Ihr Anwendungscode erfassen, ob Vorgängerversionen von Objekten vorhanden sind. Dies macht das Konzept zusätzlich komplexer.

NoSQL-Datenbanken erzwingen in der Regel nicht das [ACID](https://en.wikipedia.org/wiki/ACID)-Prinzip, weshalb sie im Hinblick auf die Leistung und Skalierbarkeit einen Vorteil gegenüber relationalen Datenbanken aufweisen. Sie eignen sich besonders gut für extrem große Datasets und Objekte, die sich nicht zum Speichern in genormten Tabellenstrukturen eignen. Sie müssen sich aber nicht zwischen relationalen Datenbanken und NoSQL-Datenbanken entscheiden: Sie können sogar innerhalb einer Anwendung für jeden einzelnen Bestandteil entscheiden, welche Art von Datenbank sich besser eignet.

## <a name="azure-documentdb"></a>Azure DocumentDB

Azure DocumentDB ist ein vollständig verwalteter Dienst für NoSQL-Datenbanken, der einen cloudbasierten schemalosen Datenspeicher umfasst. DocumentDB ist auf schnelle und vorhersagbare Leistung, Hochverfügbarkeit, elastische Skalierung und globale Verteilung ausgerichtet. Obwohl es sich um einen Dienst für NoSQL-Datenbanken handelt, können Entwickler aufwändige und vertraute SQL-Abfragefunktionen für JSON-Daten verwenden. Alle Ressourcen in DocumentDB werden als JSON-Dokumente gespeichert. Ressourcen werden als _Elemente_, bei denen es sich um Dokumente mit Metadaten handelt, und als _Feeds_ verwaltet, bei denen es sich um Auflistungen von Elementen handelt. In Abbildung 8–2 wird die Beziehung zwischen verschiedenen DocumentDB-Ressourcen dargestellt.

![Die hierarchische Beziehung zwischen Ressourcen in DocumentDB; eine NoSQL-Datenbank im JSON-Format](./media/image8-2.png)

**Abbildung 8–2.** Ressourcenorganisation in DocumentDB

Bei der DocumentDB-Abfragesprache handelt es sich um eine einfache, aber leistungsstarke Schnittstelle zum Abfragen von JSON-Dokumenten. Diese Sprache unterstützt einen Teil der durch das American National Standards Institute (ANSI) festgelegten Grammatik und umfasst eine ausführliche Integration von JavaScript-Objekten, Arrays, Objektkonstruktionen und Funktionsaufrufen.

**Ressourcen: DocumentDB**

- Einführung in DocumentDB  
  <https://docs.microsoft.com/azure/documentdb/documentdb-introduction>

## <a name="other-persistence-options"></a>Andere Persistenzoptionen

Neben relationalen Speicheroptionen und NoSQL-Optionen können ASP.NET Core-Anwendungen auch Azure Storage verwenden, um verschiedene Datenformate und Dateien auf cloudbasierte, skalierbare Weise zu speichern. Azure Storage ist im großen Umfang skalierbar, d.h., Sie können zunächst kleine Mengen von Daten speichern und zentral hochskalieren, und den Umfang dann auf mehrere Hundert Terrabyte ausweiten, falls dies die Anwendung erfordert. Azure Storage unterstützt vier verschiedene Arten von Daten:

- Blob Storage für unstrukturierten Text oder als Binärspeicher (auch als Objektspeicher bezeichnet)

- Table Storage für strukturierte Datasets, auf die über Zeilenschlüssel zugegriffen werden kann

- Queue Storage für zuverlässiges warteschlangenbasiertes Messaging

- File Storage für den Zugriff auf freigegebene Dateien zwischen virtuellen Azure-Computern und lokalen Anwendungen

**Ressourcen: Azure Storage**

- Einführung in Azure Storage  
  <https://docs.microsoft.com/azure/storage/storage-introduction>

## <a name="caching"></a>Zwischenspeicherung

In Webanwendungen sollte jede Webanforderung so schnell wie möglich abgeschlossen werden. Um dies zu erreichen, können Sie z.B. die Anzahl der externen Aufrufe beschränken, die der Server ausführen muss, um eine Anforderung abzuschließen. Das Zwischenspeichern umfasst das Speichern einer Kopie von Daten auf dem Server oder in einem anderen Datenspeicher, der leichter abgefragt werden kann als die Datenquelle. Webanwendungen und insbesondere traditionelle Webanwendungen, bei denen es sich nicht um Single-Page-Webanwendung handelt, müssen mit jeder Anforderung die gesamte Benutzeroberfläche erstellen. Darum müssen häufig dieselben Datenbankabfragen wiederholt von einer Benutzeranforderung zur nächsten durchgeführt werden. In den meisten Fällen ändern sich diese Daten nur selten, sodass es keinen Grund gibt, sie ständig aus der Datenbank abzufragen. ASP.NET Core unterstützt das Zwischenspeichern von Antworten, ganzen Seiten sowie Daten und somit ein präziseres Zwischenspeicherungsverhalten.

Wenn Sie die Zwischenspeicherung implementieren, müssen Sie das Prinzip „Separation of Concerns“ im Hinterkopf behalten. Fügen Sie möglichst keine Logik für die Zwischenspeicherung in Ihre Logik für den Datenzugriff oder Ihre Benutzeroberfläche ein. Kapseln Sie die Zwischenspeicherung stattdessen in ihren eigenen Klassen, und verwenden Sie die Konfiguration, um ihr Verhalten zu steuern. Dies entspricht dem Offen/Geschlossen-Prinzip und dem Prinzip der einzigen Verantwortung (Single Responsibility) und vereinfacht die Verwaltung der Verwendungsweise der Zwischenspeicherung in Ihrer Anwendung, während diese immer umfangreicher wird.

### <a name="aspnet-core-response-caching"></a>Zwischenspeichern von Antworten mit ASP.NET Core

ASP.NET Core unterstützt zwei Ebenen des Zwischenspeicherns von Antworten. Auf der ersten Ebene werden zwar keine Elemente auf dem Server zwischengespeichert, aber es werden HTTP-Header hinzugefügt, die Clients und Proxyserver anweisen, Antworten zwischenzuspeichern. Dies wird implementiert, indem das ResponseCache-Attribut individuellen Controllern oder Aktionen hinzugefügt wird:

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }

    ViewData["Message"] = "Your contact page.";
    return View();
}
```

Im vorherigen Beispiel wird der folgende Header der Antwort hinzugefügt, der Clients dazu auffordert, das Ergebnis bis zu 60 Sekunden lang zwischenzuspeichern.

Cache-Control: public,max-age=60

Damit die serverseitige Zwischenspeicherung im Arbeitsspeicher der Anwendung hinzugefügt werden kann, müssen Sie auf das NuGet-Paket „Microsoft.AspNetCore.ResponseCaching“ verweisen, und dann die Antworten zwischenspeichernde Middleware hinzufügen. Diese Middleware wird beim Start sowohl in „ConfigureServices“ als auch in „Configure“ konfiguriert:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

Die Antworten zwischenspeichernde Middleware speichert automatisch auf der Grundlage von einigen Bedingungen Antworten zwischen, die Sie anpassen können. Standardmäßig werden nur „200 – OK“-Antworten zwischengespeichert, die über die Methoden GET oder HEAD angefordert werden. Außerdem müssen Anforderungen über eine Antwort mit Cache-Control und öffentlichen Headers verfügen und können keine Header für das Authorization- oder Set-Cookie umfassen. Weitere Informationen finden Sie in einer [vollständigen Liste von Zwischenspeicherungsbedingungen, die von der Antworten zwischenspeichernden Middleware verwendet werden](/aspnet/core/performance/caching/middleware#conditions-for-caching).

### <a name="data-caching"></a>Zwischenspeichern von Daten

Anstelle des oder neben dem Zwischenspeichern vollständiger Webantworten können Sie auch die Ergebnisse einzelner Datenabfragen zwischenspeichern. Dafür können Sie speicherinternes Caching auf dem Webserver oder einen [verteilten Cache verwenden](/aspnet/core/performance/caching/distributed). In diesem Abschnitt erfahren Sie, wie Sie das speicherinterne Caching implementieren.

Sie fügen in ConfigureServices Unterstützung für speicherinternes oder verteiltes Zwischenspeichern hinzu:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

Achten Sie darauf, dass auch das NuGet-Paket „Microsoft.Extensions.Caching.Memory“ hinzugefügt wird.

Sobald Sie den Dienst hinzugefügt haben, fordern Sie über Dependency Injection IMemoryCache an, wenn Sie auf den Cache zugreifen müssen. In diesem Beispiel verwendet CachedCatalogService das Entwurfsmuster „Proxy“ (oder „Decorator“), indem eine alternative Implementierung von ICatalogService bereitgestellt wird, die den Zugriff auf die zugrunde liegende CatalogService-Implementierung steuert (oder Verhalten zu dieser hinzufügt).

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }

    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }

    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }

    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

Wenn Sie die Anwendung so konfigurieren möchten, dass zwar die zwischengespeicherte Version des Diensts verwendet wird, der Dienst aber immer noch die Instanz von CatalogService abrufen kann, die er in seinem Konstruktor benötigt, können Sie Folgendes zu ConfigureServices hinzufügen:

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

Wenn dies funktioniert, sendet die Datenbank anstatt bei jeder Anforderung nur einmal pro Minute einen Aufruf, um die Katalogdaten abzurufen. Je nachdem, wie viel Datenverkehr an die Website gesendet wird, kann dies deutliche Auswirkungen auf die Anzahl von Abfragen, die an die Datenbank gesendet werden, und die durchschnittliche Seitenladezeit der Startseite haben, die zu diesem Zeitpunkt von allen drei Abfragen abhängig ist, die von diesem Dienst zur Verfügung gestellt werden.

Wenn Sie allerdings das Caching implementieren, kann dies dazu führen, dass _veraltete Daten_ verwendet werden. Damit sind Daten gemeint, die in der Quelle verändert wurden, von denen aber eine veraltete Version im Cache erhalten bleibt. Dieses Problem können Sie umgehen, wenn Sie eine kurze Cachedauer verwenden, da es für häufig verwendete Anwendungen nur wenig hilfreich ist, diese Dauer auszuweiten. Angenommen, Sie verfügen z.B. über eine Seite, die eine einzelne Datenbankabfrage sendet und zehnmal pro Sekunde abgerufen wird. Wenn diese Seite für eine Minute zwischengespeichert wird, hat dies zur Folge, dass die Anzahl der Datenbankabfragen pro Minute von 600 auf 1, also um 99,8 %, reduziert wird. Wenn die Cachedauer stattdessen auf eine Stunde festgelegt werden würde, würde die Anzahl der Abfragen insgesamt um 99,997 % reduziert werden. Dann kann es jedoch sein, dass die zwischengespeicherten Daten viel häufiger veralten.

Stattdessen können Sie proaktiv Cacheeinträge entfernen, wenn die darin enthaltenen Daten aktualisiert werden. Jeder einzelne Eintrag kann entfernt werden, wenn dessen Schlüssel bekannt ist:

```csharp
_cache.Remove(cacheKey);
```

Wenn in Ihrer Anwendung Funktionen zum Aktualisieren von zwischengespeicherten Einträgen enthalten sind, können Sie die jeweiligen Cacheeinträge aus dem Code entfernen, der die Updates ausführt. Es kann manchmal sein, dass es viele verschiedene Einträge gibt, die von verschiedenen Daten abhängig sind. In diesem Fall kann es hilfreich sein, mithilfe von CancellationChangeToken Abhängigkeiten zwischen Cacheeinträgen zu erstellen. Mit einem CancellationChangeToken-Element können Sie festlegen, dass mehrere Cacheeinträge gleichzeitig ablaufen, indem Sie das Token entfernen.

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

Die Zwischenspeicherung kann die Leistung von Webseiten drastisch verbessern, die immer wieder die gleichen Werte von der Datenbank anfordern. Stellen Sie sicher, dass Sie den Datenzugriff und die Seitenleistung messen, bevor Sie die Zwischenspeicherung hinzufügen. Wenden Sie die Zwischenspeicherung nur für notwendige Verbesserungen an. Das Zwischenspeichern verbraucht Arbeitsspeicherressourcen des Webservers, und die Anwendung wird komplexer, weshalb es wichtig ist, dass Sie diese Art von Optimierung nicht voreilig durchführen.

>[!div class="step-by-step"]
[Zurück](develop-asp-net-core-mvc-apps.md)
[Weiter](test-asp-net-core-mvc-apps.md)
