---
title: Arbeiten Sie mit Daten in ASP.NET Core-Apps
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Arbeiten mit Daten in asp
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 648e0a4cdd388cf4a322f0fc049d5dcfca53d54b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a>Arbeiten mit Daten in ASP.NET Core-Apps

> "Daten ist etwas wertvolle und dauert länger als die Systeme selbst".

Tim Berners-Lee

## <a name="summary"></a>Zusammenfassung

Datenzugriff ist ein wichtiger Bestandteil nahezu jede softwareanwendung. ASP.NET Core unterstützt eine Vielzahl von Datenzugriffsoptionen, einschließlich Entity Framework Core (und Entity Framework 6 sowie) und können mit jeder beliebigen .NET Data Access-Framework arbeiten. Die Auswahl, von der Framework mit Datenzugriff, hängt von den Anforderungen der Anwendung ab. Diese Auswahl aus den ApplicationCore und UI-Projekten werden so abstrahiert und das Kapseln von Implementierungsdetails in Infrastruktur, erleichtert um lose, testfähig Software zu erzeugen.

## <a name="entity-framework-core-for-relational-databases"></a>Entity Framework Core (für relationale Datenbanken)

Wenn Sie eine neue ASP.NET Core-Anwendung, die zum Arbeiten mit relationalen Daten benötigt schreiben, wird Entity Framework Core (EF Core) die empfohlene Vorgehensweise für Ihre Anwendung auf ihre Daten zugreifen. EF Core handelt es sich um eine objektrelationale Mapper (O/RM), die .NET Entwicklern Objekte in und aus einer Datenquelle beibehalten werden. Er wird für die meisten der Datenzugriffscode, die Entwicklern in der Regel würden schreiben überflüssig. Wie ASP.NET Core wurde von Grund auf neu bis hin zu Support modulare plattformübergreifende Anwendungen EF Core umgeschrieben. Fügen Sie es als ein NuGet-Paket an die Anwendung, in den Starttasks zu konfigurieren, und über Abhängigkeitsinjektion anfordern, wo Sie ihn benötigen.

Um EF-Core mit einer SQL Server-Datenbank verwenden möchten, führen Sie den folgenden Dotnet-CLI-Befehl ein:

Dotnet Paket Microsoft.EntityFrameworkCore.SqlServer hinzufügen

So fügen Sie Unterstützung für eine Datenquelle InMemory für Testzwecke hinzu:

Dotnet Paket Microsoft.EntityFrameworkCore.InMemory hinzufügen

### <a name="the-dbcontext"></a>Die DbContext

Um mit EF Core arbeiten, benötigen Sie eine Unterklasse von ' DbContext ' aus. Diese Klasse enthält Eigenschaften, die Auflistungen von Entitäten, denen mit Ihrer Anwendung verwendet werden kann. Das eShopOnWeb-Beispiel enthält eine CatalogContext mit Sammlungen für Elemente, Marken und -Typen:

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

Die DbContext muss einen Konstruktor, der DbContextOptions akzeptiert haben und dieses Argument auf der Basis DbContext-Konstruktor übergeben. Beachten Sie, dass, wenn Sie nur ein ' DbContext ' in der Anwendung haben, können Sie eine Instanz von DbContextOptions übergeben, aber haben müssen Sie mehrere generische DbContextOptions verwenden<T> Typ, in der DbContext-Typ als generische Parameter übergeben.

### <a name="configuring-ef-core"></a>Konfigurieren von EF Core

In der Anwendung ASP.NET Core konfigurieren Sie in der Regel EF Core in der ConfigureServices-Methode. EF-Kern verwendet eine DbContextOptionsBuilder, die mehrere nützliche Erweiterungsmethoden zum Optimieren der Konfigurations unterstützt. Um CatalogContext Verwendung eine SQL Server-Datenbank mit einer Verbindungszeichenfolge, die in der Konfiguration definierte zu konfigurieren, würden Sie ConfigureServices den folgenden Code hinzufügen:

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

So verwenden Sie die Datenbank im Arbeitsspeicher

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

Sobald Sie EF Core, erstellt einen ' DbContext ' untergeordneter Typ installiert und konfiguriert ihn im ConfigureServices, können Sie mithilfe von EF Core. Sie können anfordern eine Instanz von der DbContext-Typ in einem Dienst, der benötigt, und Arbeiten mit Ihrem persistenten Entitäten, die mithilfe von LINQ, als wären sie einfach in einer Auflistung. EF Core funktioniert die Übersetzung der LINQ-Ausdrücke in SQL-Abfragen zum Speichern und Abrufen Ihrer Daten.

Sie können die EF Core ausgeführt wird, indem Sie eine Protokollierung konfigurieren und sicherstellen, die standardvertrauensebene ist mindestens Abfragen finden Sie unter Informationen, wie in Abbildung 8 – 1 gezeigt.

![](./media/image8-1.png)

Abbildung 8: 1-Protokollierung EF Core Abfragen an die Konsole

### <a name="fetching-and-storing-data"></a>Das Abrufen und Speichern von Daten

Abrufen von Daten aus EF Core Zugriff auf die entsprechende Eigenschaft und Verwenden von LINQ zum Filtern des Resultsets. LINQ können auch die Projektion, führen Sie das Ergebnis von einem Typ in eine andere transformieren. Im folgende Beispiel würde CatalogBrands, nach Namen sortiert, gefiltert nach deren Enabled-Eigenschaft und auf einen SelectListItem-Typ projiziert abgerufen werden:

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

Es ist wichtig, im obigen Beispiel den Aufruf von ToListAsync, damit er sofort ausführen die Abfrage hinzufügen. Ordnen Sie andernfalls die Anweisung wird eine IQueryable<SelectListItem> zu BrandItems, die nicht ausgeführt werden, bis diese aufgelistet wird. Es gibt vor- und Nachteile, IQueryable-Ergebnisse aus Methoden zurückgegeben. Sie können die Abfrage, die EF Core erstellt wird, um weitere geändert werden, jedoch können auch nur während der Laufzeit auftretende Fehler führen, wenn Vorgänge zur Abfrage hinzugefügt werden, die EF Core übersetzt werden kann. Es ist im Allgemeinen sicherer zur Übergabe von alle Filter in der Methode, die den Datenzugriff ausführen und Rückgabe Sichern einer Auflistung im Arbeitsspeicher (z. B. Liste<T>) als Ergebnis.

EF Core verfolgt Änderungen auf Entitäten, die aus der Persistenz abgerufen. Zum Speichern von Änderungen auf eine nachverfolgte Entität, rufen Sie einfach die SaveChanges-Methode für DbContext, stellen Sie sicher, dass er der gleichen DbContext-Instanz ist, die verwendet wurde, um die Entität abzurufen. Hinzufügen und Entfernen von Entitäten befindet sich direkt auf die entsprechende DbSet-Eigenschaft erneut mit einem Aufruf von SaveChanges zur Ausführung der Datenbankbefehle. Das folgende Beispiel veranschaulicht das Hinzufügen, aktualisieren und Löschen von Entitäten aus der Persistenz.

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

EF Core unterstützt beide synchrone und asynchrone Methoden zum Abrufen und speichern. In Webanwendungen wurde empfohlen, das Async/await-Muster mit dem Async-Methoden verwenden, damit Threads für Web-Server beim Warten auf den auf den Abschluss Zugriffsvorgänge für Daten nicht blockiert werden.

### <a name="fetching-related-data"></a>Abrufen von verknüpften Daten

Wenn EF Core Entitäten abgerufen werden, füllt es alle Eigenschaften, die direkt mit dieser Entität in der Datenbank gespeichert sind. Navigationseigenschaften, z. B. Listen von verknüpften Entitäten werden nicht aufgefüllt und möglicherweise ihren Wert auf null. Dadurch wird sichergestellt, dass EF Core nicht mehr Daten als erforderlich ist, Abrufen von ist dies besonders wichtig für Webanwendungen, die schnell verarbeiten von Anforderungen und Antworten auf effiziente Weise zurückgeben muss. Um Beziehungen mit einer Entität enthalten *unverzüglichem Laden*, wie dargestellt, geben Sie die Eigenschaft, die mithilfe der Include-Erweiterungsmethode für die Abfrage:

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

Sie können mehrere Beziehungen einschließen, und Sie können auch untergeordnete Beziehungen einschließen ThenInclude verwenden. EF Core führt eine einzelne Abfrage, um die resultierende Menge der Entitäten abzurufen.

Eine weitere Option zum Laden von verknüpften Daten ist die Verwendung *explizites Laden*. Explizites Laden können Sie zusätzliche Daten in einer Entität zu laden, die bereits abgerufen wurden. Da dies eine separate Anforderung an die Datenbank umfasst, wird nicht empfohlen, Webanwendungen, die die Anzahl der Datenbank zu minimieren, sollten Roundtrips pro Anforderung vorgenommen.

*Verzögertes Laden* ist ein Feature, das automatisch verknüpfte Daten lädt, wie er von der Anwendung verwiesen wird. Es ist von EF Core derzeit nicht unterstützt, als mit expliziten Laden er jedoch sollte in der Regel deaktiviert werden für Webanwendungen.

### <a name="resilient-connections"></a>Robuste Verbindungen

Externe Ressourcen wie SQL-Datenbanken möglicherweise gelegentlich nicht verfügbar. Anwendungen können in Fällen von vorübergehenden Ausfall Wiederholungslogik verwenden, um zu vermeiden, durch das Auslösen einer Ausnahme. Diese Technik wird häufig als bezeichnet *verbindungsstabilität*. Sie implementieren können Ihre [eigenen-Wiederholung wird mit exponenzieller](https://docs.microsoft.com/azure/architecture/patterns/retry) Technik, indem er versucht, folgt mit einer exponentiell zunehmenden Wartezeit, bis eine maximale Anzahl von Wiederholungsversuchen überschritten wurde. Diese Technik Verwaltungsteam die Tatsache, dass Cloudressourcen zeitweise für kurze Zeit, was zu fehlschlagen einiger Anforderungen ist möglicherweise nicht verfügbar.

Für Azure SQL-Datenbank bietet Entity Framework Core bereits interne Datenbank Connection Resiliency und Wiederholungslogik. Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede Verbindung DbContext aktivieren, wenn Sie robuste EF Core Verbindungen haben möchten.

Der folgende Code auf der Verbindungsebene EF Core ermöglicht z. B. robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.

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

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Ausführungsstrategien und explizite Transaktionen mit BeginTransaction und mehrere DbContexts 
  
  Wenn Wiederholungen in EF Core Verbindungen aktiviert sind, wird jeden Vorgang, die Sie mit EF Core ausführen eigener wiederholbar Vorgang. Jede Abfrage und jeder Aufruf von SaveChanges werden als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.
  
  Jedoch, wenn Ihr Code eine Transaktion mit BeginTransaction initiiert wird, definieren Sie eine eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen – alles innerhalb der Transaktion wurde ein Rollback ausgeführt zurück, wenn ein Fehler auftritt. Eine Ausnahme wie im folgenden sehen, wenn Sie versuchen, diese Transaktion ausgeführt werden, wenn eine EF Ausführungsstrategie (wiederholungsrichtlinie) verwenden und Sie mehrere SaveChanges aus mehreren DbContexts darin enthalten.

System.InvalidOperationException: Die konfigurierte Ausführungsstrategie 'SqlServerRetryingExecutionStrategy' unterstützt keine vom Benutzer initiierten Transaktionen. Verwenden Sie die Ausführungsstrategie "DbContext.Database.CreateExecutionStrategy()" zurückgegebene, um alle Vorgänge in der Transaktion als Einheit mit möglichem auszuführen.

Die Lösung besteht darin, manuell aufrufen Ausführungsstrategie EF mit einen Delegaten, die alle Elemente darstellt, die ausgeführt werden muss. Um ein vorübergehender Fehler auftritt, wird die Ausführungsstrategie den Delegaten erneut aufrufen. Der folgende Code zeigt, wie Sie diesen Ansatz zu implementieren:

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

Ist die erste DbContext der \_CatalogContext und das zweite ist ' DbContext ' innerhalb der \_IntegrationEventLogService-Objekt. Schließlich ausgeführt die Commit-Aktion wäre mehrere DbContexts und eine Ausführungsstrategie EF verwenden.

> ### <a name="references--entity-framework-core"></a>Verweise – Entity Framework Core
> - **EF zentrale Dokumente**  
> <https://docs.microsoft.com/ef/>
> - **EF Core: Verwandte Daten**  
> <https://docs.microsoft.com/ef/core/querying/related-data>
> - **Vermeiden Sie Lazy Loading Entitäten im ASPNET-Anwendungen**  
> <http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications>

## <a name="ef-core-or-micro-orm"></a>EF Core "oder" Micro-ORM, "?

Während EF Core eine gute Wahl ist für die Verwaltung von Persistenz und zum größten Teil vom Anwendungsentwickler Datenbankdetails kapselt, ist es nicht die einzige Auswahlmöglichkeit. Eine beliebte open Source-Alternative ist die [dapper, durch](https://github.com/StackExchange/Dapper), eine so genannte Micro-ORM. Ein Micro-ORM ist ein Lightweight-weniger mit umfassenden Tools für die Zuordnung von Objekten in Datenstrukturen. Im Fall von dapper, durch verwendet seinen Entwurf auf die Leistung, Ziele konzentrieren, anstatt vollständig kapseln die zugrunde liegende Abfragen zum Abrufen und Aktualisieren von Daten. Da es SQL seitens des Entwicklers abstrahieren nicht, dapper, durch "näher an die Metall" und können Entwickler die genaue schreiben Zugriffsvorgang für Abfragen, die sie für einen angegebenen Daten verwenden möchten.

EF Core verfügt über zwei wichtige Features, die es bietet, die von dapper, durch trennen, aber auch der Verwaltungsaufwand hinzufügen. Das erste ist die Übersetzung von LINQ-Ausdrücke in SQL. Diese Übersetzungen werden zwischengespeichert, aber auch also, dass sich Aufwand in die sie beim ersten ausführen. Das zweite ist die änderungsnachverfolgung für Entitäten (sodass effiziente Update-Anweisungen generiert werden können). Dieses Verhalten kann für bestimmte Abfragen deaktiviert werden, mithilfe der AsNotTracking-Erweiterungs. EF Core generiert auch SQL-Abfragen, die in der Regel sehr effizient und leistungsoptimierung in jedem Fall durchaus akzeptabel sind, aber wenn Sie, und Kontrolle über die genaue Abfrage Ordnung müssen ausgeführt werden, können Sie benutzerdefinierte SQL übergeben (oder Ausführen einer gespeicherten Prozedur) mithilfe von EF. Core, zu. In diesem Fall übertrifft Dapper noch EF Kern ausgeführt, aber nur geringfügig. Julie Lerman zeigt einige Leistungsdaten in ihrem möglicherweise 2016 MSDN-Artikel [dapper, durch Entity Framework und Hybrid-Apps](https://msdn.microsoft.com/magazine/mt703432.aspx). Zusätzliche Leistung Benchmark-Daten für eine Vielzahl von Methoden für den Datenzugriff finden Sie in der [Dapper Website](https://github.com/StackExchange/Dapper).

Um anzuzeigen, wie dapper, durch die Syntax von EF Kern variiert, betrachten Sie diese zwei Versionen der gleichen Methode zum Abrufen einer Liste von Elementen aus:

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

Wenn Sie komplexere Objektdiagramme mit dapper, durch erstellen möchten, müssen Sie die zugehörigen Abfragen, die selbst (im Gegensatz zu einer Include hinzufügen, wie in EF Core) schreiben. Dies wird unterstützt, über eine Reihe von Syntax, z. B. eine Funktion namens mehrfach zuordnen, in dem Sie einzelne Zeilen auf mehrere zugeordnete Objekte zuordnen können. Z. B. zurück eine Klasse Post mit Owner-Eigenschaft des Typs Benutzer, die folgende SQL-Anweisung alle erforderlichen Daten:

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

Jede zurückgegebene Zeile enthält sowohl Benutzer-als auch Post-Daten. Da die Benutzerdaten der Post-Daten über die Eigenschaft "Besitzer" angefügt werden soll, wird die folgende Funktion verwendet:

```csharp
(post, user) => { post.Owner = user; return post; }
```

Die vollständige Codeliste eine Auflistung von Beiträgen ihre Eigenschaft "Besitzer" mit den zugehörigen Benutzerdaten aufgefüllt zurückgegeben würde folgendermaßen lauten:

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

Er weniger Kapselung bietet, dapper, durch Quellformat, sodass Entwickler wissen, wie ihre Daten gespeichert sind, werden Informationen zum effizienten Abfragen der und Schreiben weiteren Code, um sie abzurufen. Wenn das Modell ändert statt einfach erstellen eine neue Migration (Feature von einem anderen EF Core), und/oder Aktualisieren von Zuordnungsinformationen an einem Ort in ein ' DbContext ', muss jeder Abfrage, die betroffen ist, aktualisiert werden. Diese Abfragen haben nicht kompilieren Zeit Garantien, damit sie zur Laufzeit als Reaktion auf Änderungen am Modell oder die Datenbank, was Fehler schnell erkennen erschwert unterbrechen können. Für diese Nachteile bietet dapper, durch extrem hohe Leistung.

Für die meisten Anwendungen und die meisten Elemente der fast alle Anwendungen bietet EF Core akzeptable Leistung. Daher werden seine Developer Produktivitätsvorteile wahrscheinlich überwiegen im Vergleich zu der Verwaltungsaufwand. Für Abfragen, die vom Cachedienst profitieren können, die eigentliche Abfrage kann nur ausgeführt werden ein kleiner Prozentsatz der Zeit, wodurch relativ kleine Abfragen Leistung Unterschiede Moot.

## <a name="sql-or-nosql"></a>SQL oder NoSQL

In der Regel, relationalen SQL Server-Datenbanken haben dominiert Marketplace für persistente Speicherung von Daten, aber sie sind nicht die einzige verfügbare Lösung. NoSQL-Datenbanken wie [MongoDB](https://www.mongodb.com/what-is-mongodb) bieten einen anderen Ansatz zum Speichern von Objekten. Anstatt das mapping von Objekten zu Tabellen und Zeilen, ist eine weitere Option des gesamten Objektdiagramms serialisieren und Speichern des Ergebnisses. Die Vorteile dieses Ansatzes sind zumindest am Anfang der Einfachheit und Leistung. Es ist sicherlich einfacher zum Speichern eines einzelnen serialisierten Objekts mit einem Schlüssel als das Objekt in viele Tabellen mit Beziehungen zu zerlegen und Update- und Zeilen, die seit das Objekt zuletzt geändert wurden möglicherweise aus der Datenbank abgerufen. Ebenso ist das Abrufen und Deserialisieren eines Objekts aus einem Schlüssel-basierten Speicher in der Regel wesentlich schneller und einfacher, als komplexe Joins oder mehrere Datenbankabfragen erforderlich, um das gleiche Objekt aus einer relationalen Datenbank vollständig zu verfassen. Das Fehlen von Sperren, Transaktionen oder ein festes Schema macht keine NoSQL-Datenbanken auch sehr vielen Computern, die Unterstützung sehr großer Datasets Skalierung unterziehen.

Andererseits, haben (wie sie in der Regel aufgerufen werden) keine NoSQL-Datenbanken jeweils vor-und Nachteile. Relationale Datenbanken verwendet die Normalisierung erzwingt die Konsistenz und vermeiden doppelte Daten. Dies verringert die Gesamtgröße der Datenbank und stellt sicher, dass die Updates auf freigegebene Daten in der gesamten Datenbank sofort verfügbar sind. In einer relationalen Datenbank möglicherweise eine Tabelle nach ID, eine Country-Tabelle verweisen, wenn ein Land Namen geändert wurden, die Adressdatensätze aus dem Update ohne selbst zu aktualisierenden profitieren würden. Allerdings kann in einer NoSQL-Datenbank, Adresse und die zugehörigen Land im Rahmen des viele gespeicherten Objekte serialisiert werden. Alle betroffenen Objekte aktualisiert werden, anstatt eine einzelne Zeile, ein Update auf eine landnamen müsste. Relationale Datenbanken können auch die relationale Integrität sicherstellen, durch das Durchsetzen von Regeln, z. B. Fremdschlüssel. NoSQL-Datenbanken bieten diese Einschränkungen für ihre Daten in der Regel nicht.

Die Komplexität NoSQL-Datenbanken behandelt werden müssen, eine andere ist versionsverwaltung. Wenn die Eigenschaften eines Objekts ändern, kann er werden nicht aus früheren Versionen nicht deserialisiert werden, die gespeichert wurden. Daher müssen alle vorhandenen Objekte, die eine serialisierte (Vorgängerversion) des Objekts verfügen aktualisiert werden, um das neue Schema entsprechen. Dies unterscheidet sich nicht grundsätzlich aus einer relationalen Datenbank, wobei manchmal schemaänderungen Update Skripts erfordern oder die Zuordnung von Updates. Die Anzahl von Einträgen, die geändert werden müssen, ist jedoch häufig wesentlich größer im NoSQL-Ansatz, da mehrere Kopien der Daten vorhanden ist.

Es ist möglich, NoSQL-Datenbanken zum Speichern von mehreren Versionen von Objekten, relationale Datenbanken ein festes Schema in der Regel nicht unterstützt. Allerdings wird in diesem Fall der Anwendungscode müssen das Vorhandensein von früheren Versionen von Objekten, die zusätzliche Komplexität hinzufügen, berücksichtigen.

NoSQL-Datenbanken in der Regel nicht erzwingen [ACID](http://en.wikipedia.org/wiki/ACID), das bedeutet, dass sie Leistungs-und Skalierbarkeitsvorteile über relationale Datenbanken. Sie sind gut geeignet für extrem großen Datasets und Objekte, die nicht in den Speicher im normalisierte Tabellenstrukturen gut geeignet sind. Es gibt keinen Grund, warum eine einzelne Anwendung kann nicht nutzen beide relationalen und NoSQL-Datenbanken, die mit den einzelnen, in denen ist es am besten geeignet.

## <a name="azure-documentdb"></a>Azure DocumentDB

Azure DocumentDB ist ein vollständig verwalteter NoSQL-Datenbankdienst, der Cloud-basierten schemafreier Datenspeicher bietet. DocumentDB ist für die schnelle und zuverlässige Leistung, hohe Verfügbarkeit, flexible Skalierung und globale Verteilung integriert. Obwohl ein NoSQL-Datenbank, können Entwickler umfangreiche und vertraute SQL-Abfragefunktionen JSON-Daten verwenden. Alle Ressourcen in DocumentDB werden als JSON-Dokumente gespeichert. Ressourcen werden als verwaltet *Elemente*, welche werden alle Dokumente, die Metadaten, und *feeds*, wobei es sich um Auflistungen von Elementen. Abbildung 8 – 2 zeigt die Beziehung zwischen verschiedenen DocumentDB-Ressourcen.


![Die hierarchische Beziehung zwischen Ressourcen in DocumentDB, eine JSON NoSQL-Datenbank](./media/image8-2.png)

**Abbildung 8-2.** DocumentDB-Ressourcen-Organisation.

Die DocumentDB-Abfragesprache ist eine einfache, aber leistungsstarker Schnittstelle zum Abfragen von JSON-Dokumente. Die Sprache unterstützt eine Teilmenge der ANSI SQL-Grammatik und fügt die enge Integration der JavaScript-Objekt, Arrays, Objektkonstruktion und Funktionsaufruf hinzu.

**Verweise – DocumentDB**

-   DocumentDB Introduction\
    <https://docs.microsoft.com/azure/documentdb/documentdb-introduction>

## <a name="other-persistence-options"></a>Andere Optionen Persistenz

ASP.NET Core-Anwendungen können zusätzlich zum relationalen und NoSQL-Speicheroptionen Azure-Speicher verwenden, um eine Vielzahl von Datenformaten und Dateien in einer Cloud-basierte, skalierbare Weise zu speichern. Azure-Speicher ist hochgradig skalierbare, damit Sie starten können, speichern kleine Mengen von Daten und skaliert und an Hunderte oder Terabyte gespeichert werden, wenn die Anwendung dies erfordert. Azure-Speicher unterstützt vier Arten von Daten:

-   BLOB-Speicher für unstrukturiertem Text oder binär Speicher, auch als Objektspeicher bezeichnet.

-   Tabellenspeicher für strukturierte Datasets, die über Zeilenschlüsseln zugegriffen werden kann.

-   Warteschlangenspeicher für zuverlässige warteschlangenbasierte messaging.

-   Dateispeicher für den Zugriff auf freigegebene Dateien zwischen Azure Virtual Machines und lokale Anwendungen.

**Verweise – Azure-Speicher**

-   Azure-Speicher Introduction\
    <https://docs.microsoft.com/azure/storage/storage-introduction>

## <a name="caching"></a>Zwischenspeicherung

In Webanwendungen sollte jeder webanforderung in der kürzestmöglichen Zeit abgeschlossen werden. Eine Möglichkeit, dies zu erreichen, ist die Anzahl der externen Aufrufe zu begrenzen, die der Server vornehmen muss, um die Anforderung abzuschließen. Zwischenspeichern umfasst eine Kopie der Daten auf dem Server gespeichert (oder einem anderen Datenspeicher also mehr als die Quelle der Daten leicht abgefragt). Webanwendungen und vor allem nicht SPA herkömmlichen Web-Anwendungen müssen die vollständige Benutzeroberfläche mit jeder Anforderung erstellen. Dabei werden häufig viele der gleichen Datenbankabfragen wiederholt aus einer benutzeranforderung zur nächsten. In den meisten Fällen ändert diese Daten in seltenen Fällen gibt es also ratsam ständig es aus der Datenbank anfordern. ASP.NET Core unterstützt Zwischenspeichern von Antworten zum Zwischenspeichern von ganzen Seiten und Zwischenspeichern von Daten, die präziseren Verhalten beim Zwischenspeichern unterstützt.

Beim caching implementieren, ist es wichtig zu beachten Sie die Trennung von Anliegen. Vermeiden Sie Cachelogik implementieren, in der darauf von Datenzugriffslogik oder in der Benutzeroberfläche. Stattdessen kapseln Sie Zwischenspeichern in einem eigenen Klassen, und verwenden Sie der Konfiguration zum Verwalten des Verhaltens. Dies folgt die Öffnen/geschlossen und die einzelnen Verantwortung Prinzipien und erleichtert die Verwendung von caching in Ihrer Anwendung, während diese wächst verwalten.

### <a name="aspnet-core-response-caching"></a>ASP.NET Core Zwischenspeichern von Antworten

ASP.NET Core unterstützt zwei Ebenen Zwischenspeichern von Antworten. Die erste Ebene nicht alles auf dem Server zwischenspeichert, fügt jedoch HTTP-Header, mit die Clients und Proxyservern zum Zwischenspeichern von Antworten angewiesen. Dies wird durch Hinzufügen von Attributs ResponseCache auf einzelnen Domänencontrollern oder Aktionen implementiert:

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

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

Die Antwort zwischenspeichern Middleware werden Antworten, die basierend auf einem Satz von Bedingungen, die Sie anpassen können, automatisch zwischengespeichert werden. Standardmäßig werden nur 200 (OK), über GET oder HEAD Methoden angeforderte Antworten zwischengespeichert. Darüber hinaus benötigen Anfragen eine Antwort mit dem Cache-Control: öffentlichen Header und schließen Sie kann nicht für die Autorisierung oder Set-Cookie-Header. Finden Sie unter einem [Aufstellung der zwischenspeichernden Bedingungen dar, die von der Antwort zwischenspeichern Middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).

### <a name="data-caching"></a>Zwischenspeichern von Daten

Statt (oder zusätzlich) vollständige Web zwischenspeichern, können Sie die Ergebnisse der einzelnen Datenabfragen Zwischenspeichern. Hierzu können Sie im Arbeitsspeicher Zwischenspeichern auf dem Webserver verwenden, oder [einen verteilten Cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed). In diesem Abschnitt wird im Arbeitsspeicher Zwischenspeichern Implementierung veranschaulichen.

Sie fügen Sie Unterstützung für den Speicher hinzu (oder verteilt) in ConfigureServices Zwischenspeichern:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

Achten Sie darauf, dass das Microsoft.Extensions.Caching.Memory NuGet-Paket hinzufügen.

Nachdem Sie den Dienst hinzugefügt haben, fordern Sie IMemoryCache über Abhängigkeitsinjektion, wo Sie auf den Cache zugreifen müssen. In diesem Beispiel ist der CachedCatalogService das Entwurfsmuster Proxy (oder Decorator-Element), durch die Bereitstellung einer alternativen Implementierung des ICatalogService, die steuert den Zugriff auf (oder Verhalten fügt) mithilfe der zugrunde liegenden CatalogService-Implementierung.

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

Um die Anwendung die zwischengespeicherte Version des Diensts verwenden, aber dennoch kann der Dienst zum Abrufen einer Instanz des CatalogService in seinem Konstruktor benötigten zu konfigurieren, würden Sie Folgendes in ConfigureServices hinzufügen:

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

Mit diesem vorhanden werden die Datenbankaufrufe zum Abrufen der Katalogdaten nur einmal pro Minute und nicht bei jeder Anforderung vorgenommen werden. Abhängig von der Datenverkehr an den Standort kann dies einen sehr entscheidenden Einfluss auf die Anzahl der Abfragen, die mit der Datenbank und die durchschnittliche Seitenladezeit auf der Startseite, von denen die Abfragen, die von diesem Dienst verfügbar gemacht werden alle drei derzeit abhängig gemacht haben.

Ist ein Problem, das entsteht, wenn das Zwischenspeichern implementiert ist *abgelaufene Daten* – d. h. die Quelle jedoch eine veraltete Version geänderten Daten verbleiben im Cache. Eine einfache Möglichkeit, dieses Problem zu beheben ist die Verwendung von kleinen Cache Dauerangaben, Pflege, weil für eine ausgelastete Anwendung beschränkt zusätzlicher Vorteil auf, erweitern die Länge, die Daten zwischengespeichert werden. Betrachten Sie beispielsweise eine Seite, die eine einzelnen Datenbankabfrage macht und 10 Mal pro Sekunde angefordert wird. Wenn diese Seite eine Minute lang zwischengespeichert wird, führt dies zu der Anzahl von Datenbankabfragen vorgenommen pro Minute auf 1, eine Reduzierung der 99,8 % von 600 gelöscht. Wenn stattdessen die Cachedauer einstündigen vorgenommen wurden, die allgemeine Reduzierung wäre 99.997 %, aber jetzt die Wahrscheinlichkeit und potenzielle Alter der veraltete Daten werden sowohl erhöht erheblich.

Ein anderer Ansatz besteht darin, Cacheeinträge proaktiv zu entfernen, wenn die darin enthaltenen Daten aktualisiert werden. Einzelne Einträge kann entfernt werden, wenn der Schlüssel bekannt ist:

```csharp
_cache.Remove(cacheKey);
```

Wenn Ihre Anwendung verfügbar macht, Funktionen zum Aktualisieren der Einträge, die zwischengespeichert werden, können Sie die entsprechenden Einträge in Ihrem Code entfernen, die die Updates ausführt. In einigen Fällen möglicherweise viele verschiedene Einträge, die einen bestimmten Satz von Daten abhängig sind. In diesem Fall kann es zum Erstellen von Abhängigkeiten zwischen Cacheeinträge mithilfe einer CancellationChangeToken hilfreich sein. Mit einem CancellationChangeToken können Sie das Token abgebrochen gleichzeitig mehrere Einträge im Cache ablaufen.

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

>[!div class="step-by-step"]
[Vorherigen] (Develop-asp-net-core-mvc-apps.md) [weiter] (Test-asp-net-core-mvc-apps.md)
