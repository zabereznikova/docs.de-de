---
title: Implementieren die Persistenz Infrastrukturebene mit Entity Framework Core
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren die Persistenz Infrastrukturebene mit Entity Framework Core"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 508d60d73eb7c0f0cc2cc909613cc4f8712b4aba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Implementieren die Persistenz Infrastrukturebene mit Entity Framework Core

Bei Verwendung von relationalen Datenbanken, z. B. SQL Server, Oracle oder PostgreSQL ist eine empfohlene Vorgehensweise zum Implementieren der Persistenzebene basierend auf Entity Framework (EF). EF unterstützt LINQ und stellt stark typisierte Objekte für Ihr Modell als auch vereinfachte Persistenz in die Datenbank bereit.

Entity Framework verfügt über eine lange Verlaufsdaten als Teil von .NET Framework. Wenn Sie .NET Core verwenden, sollten Sie auch Entity Framework Core, verwenden die unter Windows oder Linux ausgeführt, auf die gleiche Weise wie .NET Core wird. EF Core handelt es sich um eine vollständig neue Version von Entity Framework, mit einer wesentlich kleineren Platzbedarf und wichtige Verbesserungen der Leistung implementiert.

## <a name="introduction-to-entity-framework-core"></a>Einführung in Entity Framework Core

Entity Framework (EF) Core ist eine einfache, die erweiterbar sind, und plattformübergreifende-Version des beliebten Entity Framework-Daten zugreifen, Technologie. Es wurde in der Mitte 2016 mit .NET Core eingeführt.

Da eine Einführung in EF Core bereits in der Microsoft-Dokumentation verfügbar ist, bieten wir hier lediglich Links zu diesen Informationen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)

-   **Erste Schritte mit ASP.NET Core und Entity Framework Core mithilfe von Visual Studio**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)

-   **DbContext-Klasse**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)

-   **Vergleichen von EF Core & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>Die Infrastruktur in Entity Framework Core im Hinblick auf DDD

Aus Sicht des eine DDD ist eine wichtige Funktion von EF die Möglichkeit zur Verwendung von POCO-Domain-Entitäten, auch in der EF-Terminologie als POCO bezeichnet *Code First Entitäten*. Bei Verwendung von POCO-Domänenentitäten werden Ihren Modellklassen Domäne Dauerhaftigkeit ignorierende, nach der [Persistenz Unkenntnis](http://deviq.com/persistence-ignorance/) und [Infrastruktur Unkenntnis](https://ayende.com/blog/3137/infrastructure-ignorance) Prinzipien.

Pro DDD-Muster sollten Sie Domänenverhalten und Regeln in die Entitätsklasse, die selbst kapseln, damit es invarianten, Validierungen und Regeln steuern kann, wenn Sie eine beliebige Sammlung zugreifen. Aus diesem Grund ist es nicht empfiehlt sich in DDD, öffentlicher Zugriff auf Auflistungen von untergeordneten Entitäten oder rückgabewertobjekte erlauben. Sie möchten stattdessen verfügbar machen, Methoden, die steuern, wie und wann die Felder und eigenschaftenauflistungen aktualisiert werden können, und welche Verhalten und Aktionen erfolgen soll, wenn dies geschieht.

In Version 1.1 EF-Core damit diese DDD-Anforderungen erfüllt werden möglich plain Felder in Ihren Entitäten anstelle von Eigenschaften mit öffentlichen und privaten Setter. Wenn Sie nicht wünschen, dass ein Entitätsfeld extern zugegriffen werden kann, können Sie nur das Attribut oder ein Feld statt einer Objekteigenschaft erstellen. Es ist nicht erforderlich, private Setter verwenden, falls dieses saubere gewünscht.

Auf ähnliche Weise, Sie haben jetzt nur-Lese Zugriff auf Auflistungen mithilfe einer öffentlichen Eigenschaft, die als IEnumerable typisiert&lt;T&gt;, denen von einem Mitglied privates Feld für die Sammlung gesichert ist (z. B. eine Liste&lt;&gt;) in Ihrer Entität, die für den permanenten Speicher EF abhängt. Frühere Versionen von Entity Framework benötigten Sammlungseigenschaften zur Unterstützung von ICollection&lt;T&gt;, die vorgesehen, dass alle Entwickler, die mit der übergeordneten Entität-Klasse konnte hinzufügen oder Entfernen von Elementen aus der eigenschaftenauflistungen. Diese Möglichkeit wäre für die empfohlene Muster in DDD.

Sie können eine private Auflistung beim Verfügbarmachen einer nur-Lese IEnumerable-Objekt verwenden, wie im folgenden Codebeispiel wird gezeigt:

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...
    private readonly List<OrderItem> _orderItems;

    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        // Initializations ...
    }

    public void AddOrderItem(int productId, string productName,
        decimal unitPrice, decimal discount,
        string pictureUrl, int units = 1)
    {
        // Validation logic...
        var orderItem = new OrderItem(productId, productName, unitPrice, discount,
            pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

Beachten Sie, dass die Eigenschaft OrderItems nur zugegriffen werden kann mithilfe der Liste als schreibgeschützt&lt;&gt;. AsReadOnly(). Diese Methode erstellt einen schreibgeschützten Wrapper für private Liste, sodass er gegen externe Updates geschützt ist. Ist wesentlich kostengünstiger als die Verwendung der ToList-Methode, da sie keinen kopieren Sie alle Elemente in einer neuen Auflistung. Stattdessen führt es nur ein Heap Alloc-Vorgang für die Wrapperinstanz.

EF Core bietet eine Möglichkeit der physischen Datenbank Domänenmodell zuzuordnen, ohne die Domänenmodell Programme. Es ist rein POCO .NET Code, da die Zuordnung Aktion in der Persistenzebene implementiert wird. In dieser Zuordnung Aktion müssen Sie die Zuordnung der Felder in Datenbank konfigurieren. Im folgenden Beispiel einer OnModelCreating-Methode weist der hervorgehobene Code EF-Kerne und der OrderItems-Eigenschaft über dem Feld zugreifen.

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    // ...
    modelBuilder.Entity<Order>(ConfigureOrder);
    // Other entities ...
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    // Other configuration ...
    var navigation = orderConfiguration.Metadata.
    FindNavigation(nameof(Order.OrderItems));
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);
    // Other configuration ...
}
```

Bei Verwendung von Feldern anstelle von Eigenschaften wird die OrderItem Entität beibehalten, als ob es sich um eine Liste hatte&lt;OrderItem&gt; Eigenschaft. Allerdings macht einen einzelnen Accessor (AddOrderItem-Methode) für neue Elemente hinzufügen, um die Reihenfolge verfügbar. Daher Verhalten und die Daten miteinander verbunden sind, und Sie in der gesamten Anwendungscode, der die Domänenmodell verwendet konsistent sein werden.

## <a name="implementing-custom-repositories-with-entity-framework-core"></a>Implementieren von benutzerdefinierten Repositorys mit Entity Framework Core

Der Ebene der Implementierung ist ein Repository einfach eine Klasse mit Persistenz Datencode eine Arbeitseinheit (DBContext in EF Core) koordinierte Weltzeit. die Ausführung der Updates, wie in der folgenden Klasse dargestellt:

```csharp
// using statements...
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class BuyerRepository : IBuyerRepository
    {
        private readonly OrderingContext _context;

        public IUnitOfWork UnitOfWork
        {
            get
            {
                return _context;
            }
        }
    }

    public BuyerRepository(OrderingContext context)
    {
        if (context == null)
        {
            throw new ArgumentNullException(
                nameof(context));
        }
        _context = context;
    }

    public Buyer Add(Buyer buyer)
    {
        return _context.Buyers.Add(buyer).Entity;
    }

    public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
    {
        var buyer = await _context.Buyers.Include(b => b.Payments)
            .Where(b => b.FullName == BuyerIdentityGuid)
            .SingleOrDefaultAsync();
        return buyer;
    }
}
```

Beachten Sie, dass die IBuyerRepository-Schnittstelle von der Ebene der Domäne stammen. Allerdings erfolgt die Repository-Implementierung zur Persistenz und Infrastrukturebene.

EF DbContext wird über den Konstruktor über Abhängigkeitsinjektion. Es wird von mehreren Repositorys innerhalb des Bereichs der gleiche HTTP-Anforderung, Dank seiner Standardlebensdauer (ServiceLifetime.Scoped) in der IoC-Container gemeinsam genutzt (die auch explizit mit Diensten festgelegt werden kann. AddDbContext&lt;&gt;).

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Methoden, die in einem Repository (Updates oder Transaktionen im Vergleich zu Abfragen) implementiert.

Innerhalb jedes Repository-Klasse sollten Sie die persistenzmethoden abgelegt, die den Status der von seiner verwandten Aggregat enthaltenen Entitäten zu aktualisieren. Denken Sie daran, dass zwischen ein Aggregat und seine zugehörigen Repository: 1-Beziehung vorhanden ist. Müssen Sie berücksichtigen, dass ein Entitätsobjekt aggregieren Stamm untergeordneten Entitäten innerhalb seines Diagramms EF eingebettet haben kann. Z. B. möglicherweise ein Käufer mehrere Zahlungsmethoden als verknüpfte untergeordnete Entitäten.

Da der Ansatz für die Sortierung Microservice in eShopOnContainers auch CQS/CQRS basiert, sind die meisten Abfragen in benutzerdefinierten Repositorys nicht implementiert. Entwickler haben die Möglichkeit zum Erstellen der Abfragen und Joins, die ohne den Einschränkungen von Aggregate, benutzerdefinierte Repositorys pro zusammenzufassen und DDD im Allgemeinen für die Darstellungsschicht erforderlich. Die meisten der benutzerdefinierten Repositorys wird in diesem Handbuch vorgeschlagene haben mehrere Update- oder transaktionale Methoden, aber nur die Abfragemethoden benötigt wird, zum Abrufen von Daten aktualisiert werden. Beispielsweise implementiert BuyerRepository Repository eine FindAsync-Methode, da die Anwendung muss wissen, ob ein bestimmtes kaufen, die vor dem Erstellen eines neuen Käufers im Zusammenhang mit der Reihenfolge vorhanden ist.

Allerdings werden die echte Abfragemethoden zum Abrufen von Daten an die Präsentation Ebene oder Client-apps implementiert, wie erwähnt, in den CQRS-Abfragen basierend auf flexible Abfragen, die mit dapper, durch.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>Verwenden einer benutzerdefinierten Repository im Vergleich zum Verwenden von EF DbContext direkt

Die Entity Framework DbContext-Klasse basiert auf den Mustern Unit of Work und des Repositorys und genutzt werden direkt aus Ihrem Code, z. B. auf einem ASP.NET Core MVC-Controller. D. h. die Möglichkeit können Sie den einfachsten Code, wie die CRUD-Katalog Microservice in eShopOnContainers erstellen. In Fällen den einfachsten Code möglich, sollten Sie die DbContext-Klasse direkt verwenden, wie viele Entwickler.

Implementieren benutzerdefinierte Repositorys bietet jedoch mehrere Vorteile beim komplexere Microservices oder Anwendungen zu implementieren. Die Muster Unit of Work und des Repositorys sollen die Persistenz-Infrastrukturebene zu kapseln, damit diese von der Anwendung und die Domäne Modell Ebenen entkoppelt wird. Implementieren diese Muster Endprodukts bei der Verwendung von simulierten Repositorys, die Zugriff auf die Datenbank zu simulieren.

In Abbildung 9 – 18 können Sie die Unterschiede zwischen der Verwendung nicht Repositorys (direkt mit EF DbContext) anzeigen, im Vergleich zum Verwenden des Repositorys, die diese Repositorys modellieren vereinfachen.

![](./media/image19.png)

**Abbildung 9 – 18**. Verwenden von benutzerdefinierten Repositorys im Vergleich zu einer einfachen DbContext

Es gibt mehrere alternativen imitieren. Konnten Sie nur Repositorys modellieren, oder Sie können eine gesamte Arbeitseinheit modellieren. Simulieren einfach den Repositorys in der Regel reicht aus, und die Komplexität zu abstrahieren simulieren Sie eine gesamte Arbeitseinheit ist in der Regel nicht erforderlich.

Später, wenn wir uns auf die Anwendungsschicht konzentrieren, sehen Sie Abhängigkeitsinjektion in ASP.NET Core wie funktioniert und wie es bei Verwendung des Repositorys implementiert wird.

Kurz gesagt, können mit benutzerdefinierten Repositorys Code leichter mit Komponententests zu testen, die durch den Data-Tier-Zustand nicht beeinträchtigt werden. Wenn Sie Tests, die auch Zugriff auf die aktuelle Datenbank über das Entity Framework ausführen, sind sie nicht Komponententests jedoch Integrationstests, die viel langsamer sind.

Wenn DbContext direkt verwendet haben, wäre die einzige Option, die Sie zum Ausführen von Komponententests mithilfe einer in-Memory-SQL-Server mit vorhersagbaren Daten für Komponententests. Steuern von Pseudoobjekten und falschen Daten auf die gleiche Weise auf die Repository-Ebene ist nicht möglich. Natürlich können Sie immer die MVC-Controller testen.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>EF DbContext und IUnitOfWork Instanz Lebensdauer im IoC-container

Die DbContext-Objekt (die als IUnitOfWork Objekt verfügbar gemacht) möglicherweise von mehreren Repositorys innerhalb desselben Gültigkeitsbereichs der HTTP-Anforderung gemeinsam genutzt werden. Beispielsweise gilt dies, wenn der Vorgang ausgeführt wird, mehrere Aggregate oder einfach beschäftigen muss, da Sie mehrere Instanzen von Repository verwenden. Es ist auch wichtig zu erwähnen, dass die Schnittstelle IUnitOfWork Teil der Domäne sind, keinen EF-Typ ist.

Zu diesem Zweck muss die Instanz des Objekts DbContext seine Lebensdauer von Diensten auf ServiceLifetime.Scoped festgelegt haben. Dies ist die Standardlebensdauer Wenn services registrieren ein ' DbContext ' mit. AddDbContext im IoC-Container aus der Datei "Startup.cs" in Ihrem Projekt ASP.NET Core Web-API der ConfigureServices-Methode. Dies wird im folgenden Code veranschaulicht.

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(HttpGlobalExceptionFilter));
    }).AddControllersAsServices();

    services.AddEntityFrameworkSqlServer()
    .AddDbContext<OrderingContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlop => sqlop.MigrationsAssembly(typeof(Startup).GetTypeInfo().
        Assembly.GetName().Name));
    },
    ServiceLifetime.Scoped // Note that Scoped is the default choice
    // in AddDbContext. It is shown here only for
    // pedagogic purposes.
    );
}
```

Der Modus der DbContext-Instanziierung sollte nicht als ServiceLifetime.Transient oder ServiceLifetime.Singleton konfiguriert werden.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>Die Lebensdauer der Repository-Instanz im IoC-container

Auf ähnliche Weise sollte die Lebensdauer des Repositorys in der Regel als Bereichsbezogene (InstancePerLifetimeScope in Autofac) festgelegt werden. Unter Umständen liegen auch vorübergehend (InstancePerDependency in Autofac), aber der Dienst wird hinsichtlich Arbeitsspeicher effizienter sein, wenn Sie die Bereichsbezogene Lebensdauer verwenden.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

Beachten Sie, dass die Singleton-Lebensdauer für das Repository Sie schwerwiegende Probleme verursachen könnte, wenn Ihre ' DbContext ' festgelegt ist, beschränkt (InstancePerLifetimeScope) Lebensdauer (den Standard-Lebensdauer für ein ' DbContext ').

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Implementieren das Repository und die Einheit der Arbeit Muster in einer ASP.NET MVC-Anwendung**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)

-   **Jonathan Abläufe. Implementierungsstrategien für das Repository mit Entity Framework, Dapper, Muster und verketten**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)

-   **Cesar de la Torre. Vergleichen von ASP.NET Core IoC-Container Dienst Lebensdauer mit Autofac IoC-Container Instanz Bereichen**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="table-mapping"></a>Zuordnung zu einer Tabelle

Tabellenzuordnung identifiziert die Tabellendaten aus abgefragt werden und in der Datenbank gespeichert. Zuvor haben Sie gesehen, wie Domänenentitäten (z. B. ein Produkt oder eine Bestellung Domäne) generieren eines Schemas für die verbundene Datenbank verwendet werden können. EF dient stark auf dem Konzept von *Konventionen*. Konventionen Adresse Fragen wie "Welche der Namen einer Tabelle werden?" oder "welche Eigenschaft ist der primäre Schlüssel?" Konventionen basieren normalerweise auf herkömmliche Namen – z. B. befindet er sich typisch für den primären Schlüssel als eine Eigenschaft, die mit der ID endet

Gemäß der Konvention jede Entität wird eingerichtet sein, dass eine Tabelle mit dem gleichen Namen wie die DbSet zuordnen&lt;TEntity&gt; Eigenschaft, die die Entität für den abgeleiteten Kontext verfügbar macht. Wenn keine DbSet&lt;TEntity&gt; Wert ist, sofern für die angegebene Entität, der Name der Klasse verwendet wird.

### <a name="data-annotations-versus-fluent-api"></a>Datenanmerkungen im Vergleich zu Fluent-API

Es gibt viele weitere EF-Core-Konventionen, und die meisten von ihnen können mithilfe von datenanmerkungen oder der Fluent-API implementiert, innerhalb der OnModelCreating-Methode geändert werden.

Datenanmerkungen müssen auf den Entitätsklassen für das Modell selbst verwendet werden, dies ist eine auffallendere Methode aus der Sicht eine DDD. Dies liegt daran führen Datenkonsistenz Ihr Modell mit datenanmerkungen im Zusammenhang mit der Infrastruktur-Datenbank beeinträchtigen. Andererseits, ist die Fluent-API eine einfache Möglichkeit, die meisten Konventionen und Zuordnungen in Ihrer Infrastruktur datenpersistenzebene ändern, damit das Entitätsmodell bereinigen und aus der Persistenz-Infrastruktur abgekoppelt werden.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>Fluent-API und der OnModelCreating-Methode

Wie bereits erwähnt, können Sie aus um Konventionen und Zuordnungen, ändern die OnModelCreating-Methode in der DbContext-Klasse verwenden. Das folgende Beispiel zeigt, wie wir dies in der Reihenfolge Microservice in eShopOnContainers durchführen.

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    //Other entities
    modelBuilder.Entity<OrderStatus>(ConfigureOrderStatus);
    //Other entities
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Property(o => o.Id).ForSqlServerUseSequenceHiLo("orderseq", DEFAULT_SCHEMA);
    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    orderConfiguration.Property<string>("Street").IsRequired();
    orderConfiguration.Property<string>("State").IsRequired();
    orderConfiguration.Property<string>("City").IsRequired();
    orderConfiguration.Property<string>("ZipCode").IsRequired();
    orderConfiguration.Property<string>("Country").IsRequired();
    orderConfiguration.Property<int>("BuyerId").IsRequired();
    orderConfiguration.Property<int>("OrderStatusId").IsRequired();
    orderConfiguration.Property<int>("PaymentMethodId").IsRequired();

    var navigation =
    orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
    // DDD Patterns comment:
    // Set as Field (new since EF 1.1) to access
    // the OrderItem collection property as a field
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

    orderConfiguration.HasOne(o => o.PaymentMethod)
        .WithMany()
        .HasForeignKey("PaymentMethodId")
        .OnDelete(DeleteBehavior.Restrict);
        orderConfiguration.HasOne(o => o.Buyer)
        .WithMany()
        .HasForeignKey("BuyerId");
        orderConfiguration.HasOne(o => o.OrderStatus)
        .WithMany()
        .HasForeignKey("OrderStatusId");
}
```

Konnten Sie die Fluent-API-Zuordnungen innerhalb der gleichen OnModelCreating-Methode festgelegt, aber es ist ratsam, Partitionieren diesen Code und mehrere Submethods, eine pro Entität haben, wie im Beispiel gezeigt. Bei besonders großen Modellen kann es auch ratsam, separate Quelldateien (statische Klassen) zur Konfiguration der anderen Entitätstypen sein.

Der Code im Beispiel ist explizit. EF Core Konventionen führen die meisten dieser jedoch automatisch, deshalb ist der tatsächliche Code, den Sie dasselbe Ziel erreichen schreiben müssen wesentlich kleiner.

### <a name="the-hilo-algorithm-in-ef-core"></a>Der Algorithmus Hi/Lo in EF Core

Ein interessanter Aspekt der Code im vorherigen Beispiel ist, verwendet der [Hi/Lo Algorithmus](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) als die Generierung von Zertifizierungsstellenschlüsseln-Strategie.

Der Algorithmus Hi/Lo ist nützlich, wenn Sie eindeutige Schlüssel benötigen. Als eine Zusammenfassung weist der Hi-Lo Algorithmus eindeutige Bezeichner zu Tabellenzeilen aus, während nicht je nach der Zeile sofort in der Datenbank gespeichert. Dadurch können Sie den Einstieg in die Bezeichner sofort, wie bei regulären sequenzielle Datenbank-IDs geschieht.

Der Algorithmus Hi/Lo beschreibt einen Mechanismus zum Generieren von safe-IDs auf der Clientseite und nicht in der Datenbank. *Sichere* bedeutet, dass in diesem Kontext ohne Konflikte. Bei diesem Algorithmus handelt es sich um interessante aus diesen Gründen:

-   Das Muster Unit of Work wird nicht unterbrochen.

-   Sie erfordert keine Roundtrips Weise Sequenz-Generatoren in andere DBMS-Systeme zu tun.

-   Er generiert einen Menschen lesbaren Bezeichner, im Gegensatz zu Techniken, die GUIDs zu verwenden.

EF Core unterstützt [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) mit ForSqlServerUseSequenceHiLo-Methode, wie im vorherigen Beispiel gezeigt.

### <a name="mapping-fields-instead-of-properties"></a>Zuordnen von Feldern anstelle von Eigenschaften

Mit der Funktion von EF Core 1.1, die Spalten zu Feldern zugeordnet werden soll, ist es möglich, die keine Eigenschaften in die Entitätsklasse verwendet werden, und nur Spalten aus einer Tabelle Felder zuordnen. Eine übliche Verwendung für diese wäre private Felder für alle internen Status, die nicht von außerhalb der Entität zugegriffen werden muss.

EF 1.1 unterstützt eine Möglichkeit, ein Feld ohne eine zugehörige Eigenschaft einer Spalte in der Datenbank zugeordnet. Hierzu können Sie einzelne Felder oder auch mit Auflistungen, wie eine Liste&lt; &gt; Feld. Bisher wurde weiter oben erwähnt, werden beim Modellieren der Domäne Modellklassen besprochen, jedoch hier Sie sehen können, wie die Zuordnung ausgeführt wird, mit der PropertyAccessMode.Field-Konfiguration, die im vorherigen Code hervorgehoben.

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a>Verwenden von Shadowing von Eigenschaften in rückgabewertobjekte für ausgeblendete-IDs auf der Infrastrukturebene

Shadowing von Eigenschaften in EF Core sind Eigenschaften, die nicht in Ihrer Klasse Entitätsmodell vorhanden sind. Die Werte und den Status dieser Eigenschaften werden ausschließlich in verwaltet die [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) Klasse auf Infrastrukturebene.

Aus Sicht des eine DDD sind Shadowing von Eigenschaften für eine einfache Möglichkeit, den Wert-Objekte implementieren, indem Sie die ID als primären Schlüssel für eine Schattenkopie ausblenden. Dies ist wichtig, da ein Wertobjekt Identität keinen sollten (über mindestens Sie müssen nicht die ID in der Domäne der Ebene beim Strukturieren der Value-Objekte). Das Hierbei ist, dass zum Zeitpunkt der aktuellen Version von EF Core, EF Core eine Möglichkeit zum Implementieren des Value-Objekte als keinen [komplexe Typen](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), wie möglich in EF 6.x. Aus diesem Grund müssen Sie zurzeit implementieren ein Wertobjekt als eine Entität mit einer ausgeblendeten-ID (Primärschlüssel) als ein Schatten-Eigenschaft festgelegt ist.

Wie in der Sie sehen die [Wert Adressobjekt](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, im Modell Adresse nicht angezeigt. ID:

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }
    //Constructor initializing, etc
}
```

Aber im Hintergrund müssen wir eine ID bereitstellen, sodass EF Core diese Daten in Tabellen der Datenbank beibehalten werden kann. Wir machen, die in der Methode ConfigureAddress der [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) Klasse auf der Infrastrukturebene, damit wir das Domänenmodell mit EF Infrastrukturcode nicht beschädigt sind.

```csharp
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    // DDD pattern comment:
    // Implementing the Address ID as a shadow property, because the
    // address is a value object and an identity is not required for a
    // value object
    // EF Core just needs the ID so it can store it in a database table
    // See: https://docs.microsoft.com/ef/core/modeling/shadow-properties
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Tabelle der Zuordnung**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)

-   **Verwenden Sie zum Generieren von Schlüsseln mit Entity Framework Core HiLo**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)

-   **Sichern die Felder**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)

-   **Steve Smith. Sammlungen in Entity Framework Core gekapselt**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)

-   **Shadowing von Eigenschaften**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)


>[!div class="step-by-step"]
[Vorherigen] (Infrastruktur-Persistenz-Ebene – design.md) [weiter] (Nosql-Datenbank-Persistenz-infrastructure.md)
