---
title: Implementieren der Infrastrukturpersistenzebene mit Entity Framework Core
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Übersicht über Implementierungsdetails für die Infrastrukturpersistenzebene mit Entity Framework Core
ms.date: 01/30/2020
ms.openlocfilehash: 2d28d9246be3e102625ed5bb67ee1ccede03c942
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523325"
---
# <a name="implement-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Implementieren der Infrastrukturpersistenzebene mit Entity Framework Core

Bei der Verwendung von relationalen Datenbanken wie SQL Server, Oracle oder PostgreSQL wird empfohlen, die Persistenzebene auf Entity Framework (EF) basierend zu implementieren. EF unterstützt LINQ und stellt stark typisierte Objekte für Ihr Modell sowie eine vereinfachte Persistenz für Ihre Datenbank bereit.

Entity Framework ist bereits seit geraumer Zeit Bestandteil von .NET Framework. Wenn Sie .NET Core verwenden, sollten Sie auch Entity Framework Core verwenden, das unter Windows oder Linux auf die gleiche Weise wie .NET Core ausgeführt wird. Bei EF Core handelt es sich um eine vollständig neue Version von Entity Framework, die einen wesentlich geringeren Speicherbedarf hat und wichtige Leistungsverbesserungen mit sich bringt.

## <a name="introduction-to-entity-framework-core"></a>Einführung in Entity Framework Core

Entity Framework Core (EF Core) ist eine einfache, erweiterbare und plattformübergreifende Version der beliebten Entity Framework-Datenzugriffstechnologie. Es wurde Mitte 2016 mit .NET Core eingeführt.

Da in der Microsoft-Dokumentation bereits eine Einführung in EF Core verfügbar ist, werden nachfolgend nur die Links zu diesen Informationen aufgelistet.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Entity Framework Core** \
  [https://docs.microsoft.com/ef/core/](/ef/core/)

- **Erste Schritte mit ASP.NET Core MVC und Entity Framework Core mithilfe von Visual Studio** \
  [https://docs.microsoft.com/aspnet/core/data/ef-mvc/](/aspnet/core/data/ef-mvc/)

- **DbContext-Klasse** \
  [https://docs.microsoft.com/dotnet/api/microsoft.entityframeworkcore.dbcontext](xref:Microsoft.EntityFrameworkCore.DbContext)

- **Vergleichen von EF Core und EF 6.x** \
  [https://docs.microsoft.com/ef/efcore-and-ef6/index](/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>Die Infrastruktur in Entity Framework Core aus DDD-Sicht

Aus DDD-Sicht besteht eine wichtige Funktion von EF in der Möglichkeit, POCO-Domänenentitäten zu verwenden. Diese werden in der EF-Terminologie auch als POCO-*Code First-Entitäten* bezeichnet. Wenn Sie POCO-Domänenentitäten verwenden, sind Ihre Domänenmodellklassen gemäß den Grundsätzen der [Persistenzignoranz](https://deviq.com/persistence-ignorance/) und der [Infrastrukturignoranz](https://ayende.com/blog/3137/infrastructure-ignorance) persistenzignorant.

Den DDD-Mustern zufolge sollten Sie das Domänenverhalten und die Domänenregeln in der Entitätsklasse selbst einschließen, damit es beim Zugriff auf eine beliebige Auflistung Invarianten, Validierungen und Regeln steuern kann. Daher ist es in DDD nicht empfehlenswert, einen öffentlichen Zugriff auf Auflistungen untergeordneter Entitäten oder Wertobjekte zu erlauben. Stattdessen sollten Sie Methoden verfügbar machen, die steuern, wie und wann die Felder und Eigenschaftenauflistungen aktualisiert werden können und welches Verhalten und welche Aktionen in diesem Fall erfolgen sollen.

Seit EF Core 1.1 können Sie zur Erfüllung dieser DDD-Anforderungen in Ihren Entitäten normale Felder anstelle von öffentlichen Eigenschaften verwenden. Wenn ein Entitätsfeld nicht extern zugänglich sein soll, können Sie nur das Attribut oder Feld anstelle einer Eigenschaft erstellen. Ferner können Sie private Setter für Eigenschaften verwenden.

Auf ähnliche Weise ist jetzt ein schreibgeschützter Zugriff auf Auflistungen möglich, indem Sie eine als `IReadOnlyCollection<T>` typisierte öffentliche Eigenschaft verwenden, die durch ein privates Feldelement für die Auflistung (wie `List<T>`) in der Entität gestützt wird, das hinsichtlich der Persistenz auf EF vertraut. Frühere Versionen von Entity Framework benötigten Auflistungseigenschaften, um `ICollection<T>` zu unterstützen, was bedeutete, dass jeder Entwickler, der die übergeordnete Entitätsklasse verwendete, Elemente mithilfe ihrer Eigenschaftenauflistung hinzufügen oder entfernen konnte. Diese Möglichkeit würde den empfohlenen Mustern in DDD zuwiderlaufen.

Wie im folgenden Codebeispiel gezeigt wird, können Sie eine private Auflistung beim Verfügbarmachen eines schreibgeschützten `IReadOnlyCollection<T>`-Objekts verwenden:

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

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

        var orderItem = new OrderItem(productId, productName,
                                      unitPrice, discount,
                                      pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

Beachten Sie, dass auf die Eigenschaft `OrderItems` mit `IReadOnlyCollection<OrderItem>` nur schreibgeschützt zugegriffen werden kann. Dieser Typ ist schreibgeschützt, damit er vor regelmäßigen externen Aktualisierungen geschützt ist.

EF Core bietet eine Möglichkeit, das Domänenmodell der physischen Datenbank zuzuordnen, ohne das Domänenmodell zu „verunreinigen“. Dabei handelt es sich um reinen .NET-POCO-Code, da die Zuordnungsaktion in der Persistenzebene implementiert wird. Bei dieser Zuordnungsaktion müssen Sie die Zuordnung zwischen den Feldern und der Datenbank konfigurieren. Im folgenden Beispiel der `OnModelCreating`-Methode von `OrderingContext` und der `OrderEntityTypeConfiguration`Klasse weist der Aufruf von `SetPropertyAccessMode` EF Core an, über ein Feld auf die Eigenschaft `OrderItems` zuzugreifen.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
        // Other configuration

        var navigation =
              orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        //EF access the OrderItem collection property through its backing field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        // Other configuration
    }
}
```

Bei Verwendung von Feldern anstelle von Eigenschaften wird die `OrderItem`-Entität so beibehalten, als weise sie eine `List<OrderItem>`-Eigenschaft auf. Sie hat jedoch einen einzelnen Accessor, die `AddOrderItem`-Methode zum Hinzufügen neuer Elemente zur Bestellung. Daher sind das Verhalten und die Daten miteinander verknüpft und innerhalb eines Anwendungscodes, der das Domänenmodell verwendet, konsistent.

## <a name="implement-custom-repositories-with-entity-framework-core"></a>Implementieren von benutzerdefinierten Repositorys mit Entity Framework Core

Auf der Implementierungsebene ist ein Repository lediglich eine Klasse mit Datenpersistenzcode, die bei Aktualisierungen von einer Arbeitseinheit (DBContext in EF Core) koordiniert wird. Dies wird anhand der folgenden Klasse gezeigt:

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

        public BuyerRepository(OrderingContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        public Buyer Add(Buyer buyer)
        {
            return _context.Buyers.Add(buyer).Entity;
        }

        public async Task<Buyer> FindAsync(string buyerIdentityGuid)
        {
            var buyer = await _context.Buyers
                .Include(b => b.Payments)
                .Where(b => b.FullName == buyerIdentityGuid)
                .SingleOrDefaultAsync();

            return buyer;
        }
    }
}
```

Beachten Sie, dass die IBuyerRepository-Schnittstelle von der Domänenmodellebene als Vertrag übernommen wird. Die Repository-Implementierung erfolgt jedoch auf der Persistenz- und Infrastrukturebene.

Der EF-DbContext stammt mittels Abhängigkeitseinfügung aus dem Konstruktor. Aufgrund seiner Standardlebensdauer (`ServiceLifetime.Scoped`) im IoC-Container (die auch explizit mit `services.AddDbContext<>` festgelegt werden kann) wird er von mehreren Repositorys innerhalb desselben HTTP-Anforderungsbereichs verwendet.

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Methoden für die Implementierung in einem Repository (Aktualisierungen oder Transaktionen vs. Abfragen)

In jeder Repository-Klasse sollten Sie die Persistenzmethoden vorsehen, die den Zustand der Entitäten aktualisieren, die in seinem zugehörigen Aggregat enthalten sind. Denken Sie daran, dass zwischen einem Aggregat und dem zugehörigen Repository eine 1:1-Beziehung besteht. Berücksichtigen Sie, dass ein aggregiertes Stammentitätsobjekt in seinem EF-Graph eingebettete untergeordnete Entitäten aufweisen kann. Ein Käufer könnte beispielsweise mehrere Zahlungsmethoden als verknüpfte untergeordnete Entitäten aufweisen.

Da der Ansatz für den Microservice Bestellung in eShopOnContainers auch auf CQS/CQRS basiert, sind die meisten Abfragen nicht in benutzerdefinierten Repositorys implementiert. Entwickler können die Abfragen und Verknüpfungen, die sie für die Darstellungsschicht benötigen, ohne die Einschränkungen von Aggregaten, benutzerdefinierten Repositorys pro Aggregat und generell DDD erstellen. Die meisten der in diesem Leitfaden vorgeschlagenen benutzerdefinierten Repositorys weisen mehrere Aktualisierungs- oder Transaktionsmethoden, aber nur die für das Abrufen der zu aktualisierenden Daten benötigten Abfragemethoden auf. Das Repository BuyerRepository implementiert beispielsweise eine FindAsync-Methode, da die Anwendung wissen muss, ob ein bestimmter Käufer vorhanden ist, bevor im Zusammenhang mit der Bestellung ein neuer Käufer angelegt wird.

Allerdings werden die tatsächlichen Abfragemethoden für das Abrufen von Daten, die an die Darstellungsschicht oder die Client-Apps gesendet werden, wie erwähnt in den CQRS-Abfragen basierend auf flexiblen Abfragen mit Dapper implementiert.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>Verwenden eines benutzerdefinierten Repositorys im Vergleich zu einer direkten Verwendung von EF-DbContext

Die DbContext-Klasse von Entity Framework basiert auf den Mustern Arbeitseinheit und Repository und kann direkt aus Ihrem Code verwendet werden, beispielsweise aus einem ASP.NET Core MVC-Controller. So können Sie einen möglichst einfachen Code erstellen, wie im Microservice CRUD-Katalog in eShopOnContainers. In Fällen, in denen Sie einen möglichst einfachen Code wünschen, sollten Sie – wie viele andere Entwickler auch – direkt die DbContext-Klasse verwenden.

Das Implementieren benutzerdefinierter Repositorys bietet jedoch mehrere Vorteile, wenn komplexere Microservices oder Anwendungen umgesetzt werden. Die Muster Arbeitseinheit und Repository sollen die Infrastrukturpersistenzebene kapseln, damit sie von den Anwendungs- und Domänenmodellebenen entkoppelt wird. Die Implementierung dieser Muster kann eine Verwendung von Modell-Repositorys ermöglichen, die den Zugriff auf die Datenbank simulieren.

Abbildung 7-18 zeigt die Unterschiede zwischen einer Vorgehensweise ohne Repositorys (d.h. direkte Verwendung von EF-DbContext) im Vergleich zu einer Verwendung von Repositorys, die das Modellieren dieser Repositorys erleichtert.

![Diagramm, das die Komponenten und den Datenfluss in den beiden Repositorys zeigt.](./media/infrastructure-persistence-layer-implemenation-entity-framework-core/custom-repo-versus-db-context.png)

**Abbildung 7-18**. Verwenden von benutzerdefinierten Repositorys im Vergleich zu einfachem DbContext

Abbildung 7–18 zeigt, dass die Verwendung eines benutzerdefinierten Repositorys eine Abstraktionsebene hinzufügt, mit der Tests durch das Modellieren des Repositorys vereinfacht werden können. Es gibt mehrere Alternativen für die Modellierung. Sie können lediglich Repositorys oder eine vollständige Arbeitseinheit modellieren. Üblicherweise reicht es aus, nur die Repositorys zu modellieren. Das komplexe Abstrahieren und Modellieren einer vollständigen Arbeitseinheit ist in der Regel nicht erforderlich.

Wenn wir uns weiter unten mit der Anwendungsebene befassen, werden Sie sehen, wie die Abhängigkeitseinfügung in ASP.NET Core funktioniert und wie sie bei der Verwendung von Repositorys implementiert wird.

Mithilfe benutzerdefinierter Repositorys können Sie also Code leichter mit Komponententests prüfen, auf die der Datenschichtzustand keine Auswirkungen hat. Wenn Sie Tests ausführen, die auch über Entity Framework auf die eigentliche Datenbank zugreifen, handelt es sich hierbei nicht um Komponententests, sondern um Integrationstests, die deutlich langsamer sind.

Wenn Sie DbContext direkt verwenden, können Sie Komponententests nur mithilfe einer In-Memory-Instanz von SQL Server mit vorhersagbaren Daten für Komponententests ausführen. Doch das Modellieren von DbContext oder das Steuern falscher Daten erfordern mehr Arbeit als das Modellieren auf Repositoryebene. Sie könnten natürlich jederzeit die MVC-Controller testen.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>EF-DbContext und IUnitOfWork-Instanzlebensdauer in Ihrem IoC-Container

Das `DbContext`-Objekt (verfügbar als `IUnitOfWork`-Objekt) muss von mehreren Repositorys innerhalb desselben HTTP-Anforderungsbereichs gemeinsam genutzt werden. Dies ist beispielsweise der Fall, wenn von dem ausgeführten Vorgang mehrere Aggregate betroffen sind oder wenn Sie mehrere Repository-Instanzen verwenden. Beachten Sie, dass die `IUnitOfWork`-Schnittstelle Teil Ihrer Domänenebene ist. Es handelt sich dabei nicht um den EF Core-Typ.

Damit mehrere Repositorys im selben HTTP-Anforderungsbereichs das Objekt gemeinsam nutzen können, muss für die Instanz des `DbContext`-Objekts die Dienstlebensdauer auf „ServiceLifetime.Scoped“ festgelegt sein. Dies ist die Standardlebensdauer beim Registrieren eines `DbContext`-Objekts mit `services.AddDbContext` in Ihrem IoC-Container mit der Methode ConfigureServices der `Startup.cs`-Datei in Ihrem ASP.NET Core-Web-API-Projekt. Dies wird im folgenden Code veranschaulicht.

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
                               sqlOptions => sqlOptions.MigrationsAssembly(typeof(Startup).GetTypeInfo().
                                                                                    Assembly.GetName().Name));
      },
      ServiceLifetime.Scoped // Note that Scoped is the default choice
                             // in AddDbContext. It is shown here only for
                             // pedagogic purposes.
      );
}
```

Der Modus der DbContext-Instanziierung sollte nicht als ServiceLifetime.Transient oder ServiceLifetime.Singleton konfiguriert werden.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>Die Lebensdauer der Repository-Instanz in Ihrem IoC-Container

Auf ähnliche Weise sollte die Lebensdauer des Repositorys in der Regel als bereichsbezogen (InstancePerLifetimeScope in Autofac) festgelegt werden. Sie könnte auch vorübergehender Natur sein (InstancePerDependency in Autofac), aber Ihr Service wird speichereffizienter sein, wenn Sie die bereichsbezogene Lebensdauer verwenden.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

Beachten Sie, dass eine Verwendung der Singleton-Lebensdauer für das Repository zu ernsthaften Parallelitätsproblemen führen könnte, wenn Ihr DbContext auf eine bereichsbezogene (InstancePerLifetimeScope) Lebensdauer festgelegt ist (die Standardlebensdauer für einen DbContext).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Implementieren der Muster Repository und Arbeitseinheit in eine ASP.NET MVC-Anwendung** \
  <https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application>

- **Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain (Implementierungsstrategien für das Repositorymuster mit Entity Framework, Dapper und Chain)**  \
  <https://www.infoq.com/articles/repository-implementation-strategies>

- **Cesar de la Torre. Vergleich der Lebensdauer: ASP.NET Core-IoC-Containerdienste vs. Autofac-IoC-Containerinstanzbereiche** \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="table-mapping"></a>Tabellenzuordnung

Bei der Tabellenzuordnung werden die Tabellendaten identifiziert, die aus der Datenbank abgerufen und in dieser gespeichert werden sollen. Sie haben bereits gesehen, wie Domänenentitäten (z.B. eine Produkt- oder Bestellungsdomäne) verwendet werden können, um ein zugehöriges Datenbankschema zu generieren. Bei der Entwicklung von EF spielte das Konzept der *Konventionen* eine wichtige Rolle. Konventionen behandeln Fragen wie „Wie wird der Name der Tabelle lauten?“ oder „Welche Eigenschaft hat der Primärschlüssel?“. Konventionen basieren üblicherweise auf konventionellen Namen. Beim Primärschlüssel handelt es sich z.B. in der Regel um eine auf ID endende Eigenschaft.

Gemäß der Konvention ist jede Entität so eingerichtet, dass sie einer Tabelle mit dem gleichen Namen wie die `DbSet<TEntity>`-Eigenschaft zugeordnet ist, die die Entität für den abgeleiteten Kontext verfügbar macht. Wenn kein `DbSet<TEntity>`-Wert für die betreffende Entität bereitgestellt wird, wird der Klassenname verwendet.

### <a name="data-annotations-versus-fluent-api"></a>Datenanmerkungen im Vergleich zu Fluent-API

Es gibt viele weitere Konventionen von EF Core, und die meisten von ihnen können entweder mithilfe von Datenanmerkungen oder mit der Fluent-API geändert werden, die innerhalb der OnModelCreating-Methode implementiert wird.

Datenanmerkungen müssen für die Entitätsmodellklassen selbst verwendet werden. Aus DDD-Sicht ist diese Methode intrusiver. Dies liegt daran, dass Sie Ihr Modell mit Datenanmerkungen verunreinigen, die mit der Infrastrukturdatenbank verknüpft sind. Andererseits ist die Fluent-API eine praktische Methode, um die meisten Konventionen und Zuordnungen in Ihrer Datenpersistenz-Infrastrukturebene zu ändern, sodass das Entitätsmodell bereinigt und von der Persistenzinfrastruktur abgekoppelt wird.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>Fluent-API und die OnModelCreating-Methode

Wie bereits erwähnt wurde, können Sie die OnModelCreating-Methode in der DbContext-Klasse verwenden, um Konventionen und Zuordnungen zu ändern.

Der Microservice Bestellung in eShopOnContainers implementiert bei Bedarf explizit die Zuordnung und Konfiguration, wie der folgende Code zeigt.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);

        orderConfiguration.HasKey(o => o.Id);

        orderConfiguration.Ignore(b => b.DomainEvents);

        orderConfiguration.Property(o => o.Id)
            .UseHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

        //Address value object persisted as owned entity type supported since EF Core 2.0
        orderConfiguration
            .OwnsOne(o => o.Address, a =>
            {
                a.WithOwner();
            });

        orderConfiguration
            .Property<int?>("_buyerId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("BuyerId")
            .IsRequired(false);

        orderConfiguration
            .Property<DateTime>("_orderDate")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderDate")
            .IsRequired();

        orderConfiguration
            .Property<int>("_orderStatusId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderStatusId")
            .IsRequired();

        orderConfiguration
            .Property<int?>("_paymentMethodId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("PaymentMethodId")
            .IsRequired(false);

        orderConfiguration.Property<string>("Description").IsRequired(false);

        var navigation = orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        // DDD Patterns comment:
        //Set as field (New since EF 1.1) to access the OrderItem collection property through its field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        orderConfiguration.HasOne<PaymentMethod>()
            .WithMany()
            .HasForeignKey("_paymentMethodId")
            .IsRequired(false)
            .OnDelete(DeleteBehavior.Restrict);

        orderConfiguration.HasOne<Buyer>()
            .WithMany()
            .IsRequired(false)
            .HasForeignKey("_buyerId");

        orderConfiguration.HasOne(o => o.OrderStatus)
            .WithMany()
            .HasForeignKey("_orderStatusId");
    }
}
```

Sie könnten alle Fluent-API-Zuordnungen innerhalb derselben `OnModelCreating`-Methode festlegen, es ist jedoch ratsam, diesen Code zu untergliedern und wie im Beispiel gezeigt über mehrere Konfigurationsklassen zu verfügen (eine pro Entität). Vor allem bei besonders großen Modellen ist es empfehlenswert, über separate Konfigurationsklassen für das Konfigurieren unterschiedlicher Entitätstypen zu verfügen.

Der Code im Beispiel zeigt einige explizite Deklarationen und Zuordnungen. EF Core-Konventionen führen viele dieser Zuordnungen jedoch automatisch aus, sodass der von Ihnen tatsächlich benötigte Code einen geringeren Umfang hätte.

### <a name="the-hilo-algorithm-in-ef-core"></a>Der Hi/Lo-Algorithmus in EF Core

Ein interessanter Aspekt des Codes im vorherigen Beispiel ist die Tatsache, dass er den [Hi/Lo-Algorithmus](https://vladmihalcea.com/the-hilo-algorithm/) als Schlüsselgenerierungsstrategie verwendet.

Der Hi/Lo-Algorithmus ist nützlich, wenn Sie eindeutige Schlüssel benötigen, bevor Sie Änderungen committen. Der Hi/Lo-Algorithmus weist im Wesentlichen Tabellenzeilen eindeutige Bezeichner zu, muss die Zeile aber nicht unverzüglich in der Datenbank speichern. Dadurch können Sie die Bezeichner sofort verwenden – wie bei regulären sequenziellen Datenbank-IDs.

Der Hi/Lo-Algorithmus beschreibt einen Mechanismus zum Abrufen eines Batches von eindeutigen IDs aus einer zugehörigen Datenbanksequenz. Die Verwendung dieser IDs gilt als sicher, da die Datenbank die Eindeutigkeit garantiert, sodass keine Konflikte zwischen Benutzern auftreten. Dieser Algorithmus ist aus den folgenden Gründen interessant:

- Das Arbeitseinheitsmuster wird nicht unterbrochen.

- Sequenz-IDs werden batchweise abgerufen, um Roundtrips zur Datenbank zu minimieren.

- Er generiert einen visuell lesbaren Bezeichner (im Gegensatz zu Techniken, die GUIDs zu verwenden).

EF Core unterstützt wie im vorigen Beispiel gezeigt [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) mit der `UseHiLo`-Methode.

### <a name="map-fields-instead-of-properties"></a>Zuordnen von Feldern anstelle von Eigenschaften

Mit diesem seit EF Core 1.1 verfügbaren Features können Sie direkt Spalten zu Feldern zuordnen. Es ist möglich,in der Entitätsklasse keine Eigenschaften zu verwenden und lediglich Spalten einer Tabelle zu Feldern zuzuordnen. Ein typischer Anwendungsfall hierfür wären private Felder für einen internen Zustand, auf die nicht von außerhalb der Entität zugegriffen werden muss.

Hierzu können Sie einzelne Felder oder auch Auflistungen wie z.B. ein `List<>`-Feld verwenden. Dieser Punkt wurde bereits oben in Zusammenhang mit dem Modellieren der Domänenmodellklassen erwähnt, aber hier können Sie sehen, wie die Zuordnung mit der `PropertyAccessMode.Field`-Konfiguration ausgeführt wird, die im vorherigen Code gekennzeichnet ist.

### <a name="use-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a>Verwenden von auf Infrastrukturebene verborgenen Schatteneigenschaften in EF Core

Schatteneigenschaften in EF Core sind Eigenschaften, die nicht in Ihren Entitätsklassenmodell vorhanden sind. Die Werte und Zustände dieser Eigenschaften werden ausschließlich in der [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker)-Klasse auf der Infrastrukturebene verwaltet.

## <a name="implement-the-query-specification-pattern"></a>Implementieren des Abfragespezifikationsmusters

Wie weiter oben bereits erläutert, ist das Abfragespezifikationsmuster ein domänengesteuertes Entwurfsmuster, das als der Ort konzipiert wurde, an dem Sie die Definition einer Abfrage mit optionaler Sortier- und Auslagerungslogik ablegen können.

Das Abfragespezifikationsmuster definiert eine Abfrage in einem Objekt. Um beispielsweise eine ausgelagerte Abfrage, die nach bestimmten Produkten sucht, zu kapseln, können Sie eine PagedProduct-Spezifikation erstellen, die die erforderlichen Eingabeparameter (pageNumber, pageSize, Filter usw.) verwendet. Anschließend würde ein IQuerySpecification-Objekt innerhalb einer Repositorymethode (in der Regel eine List()-Überladung) akzeptiert und die erwartete Abfrage anhand dieser Spezifikation ausgeführt werden.

Ein Beispiel für eine generische Spezifikationsschnittstelle ist der folgende Code aus [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).

```csharp
// GENERIC SPECIFICATION INTERFACE
// https://github.com/dotnet-architecture/eShopOnWeb

public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

Die Implementierung einer generischen Spezifikationsbasisklasse wäre dann die folgende.

```csharp
// GENERIC SPECIFICATION IMPLEMENTATION (BASE CLASS)
// https://github.com/dotnet-architecture/eShopOnWeb

public abstract class BaseSpecification<T> : ISpecification<T>
{
    public BaseSpecification(Expression<Func<T, bool>> criteria)
    {
        Criteria = criteria;
    }
    public Expression<Func<T, bool>> Criteria { get; }

    public List<Expression<Func<T, object>>> Includes { get; } =
                                           new List<Expression<Func<T, object>>>();

    public List<string> IncludeStrings { get; } = new List<string>();

    protected virtual void AddInclude(Expression<Func<T, object>> includeExpression)
    {
        Includes.Add(includeExpression);
    }

    // string-based includes allow for including children of children
    // e.g. Basket.Items.Product
    protected virtual void AddInclude(string includeString)
    {
        IncludeStrings.Add(includeString);
    }
}
```

Die folgende Spezifikation lädt eine einzelne Warenkorb-Entität entweder anhand der ID des Warenkorbs oder der ID des Käufers, zu dem der Warenkorb gehört. Sie wird die Artikelauflistung des Warenkorbs [vorzeitig laden](https://docs.microsoft.com/ef/core/querying/related-data).

```csharp
// SAMPLE QUERY SPECIFICATION IMPLEMENTATION

public class BasketWithItemsSpecification : BaseSpecification<Basket>
{
    public BasketWithItemsSpecification(int basketId)
        : base(b => b.Id == basketId)
    {
        AddInclude(b => b.Items);
    }

    public BasketWithItemsSpecification(string buyerId)
        : base(b => b.BuyerId == buyerId)
    {
        AddInclude(b => b.Items);
    }
}
```

Und schließlich sehen Sie unten, wie ein generisches EF-Repository eine solche Spezifikation verwenden kann, um Daten zu filtern und vorzeitig zu laden, die zu einem bestimmten Entitätstypen T gehören.

```csharp
// GENERIC EF REPOSITORY WITH SPECIFICATION
// https://github.com/dotnet-architecture/eShopOnWeb

public IEnumerable<T> List(ISpecification<T> spec)
{
    // fetch a Queryable that includes all expression-based includes
    var queryableResultWithIncludes = spec.Includes
        .Aggregate(_dbContext.Set<T>().AsQueryable(),
            (current, include) => current.Include(include));

    // modify the IQueryable to include any string-based include statements
    var secondaryResult = spec.IncludeStrings
        .Aggregate(queryableResultWithIncludes,
            (current, include) => current.Include(include));

    // return the result of the query using the specification's criteria expression
    return secondaryResult
                    .Where(spec.Criteria)
                    .AsEnumerable();
}
```

Zusätzlich zum Kapseln der Filterlogik kann die Spezifikation die Form der zurückzugebenden Daten angeben, einschließlich der aufzufüllenden Eigenschaften.

Obwohl davon abgeraten wird, `IQueryable`-Objekte aus einem Repository abzurufen, ist es in Ordnung, sie innerhalb des Repositorys zum Erstellen eines Resultsets zu verwenden. Sie können die Befolgung dieses Ansatzes oben bei der List-Methode sehen, die zwischengeschaltete `IQueryable`-Ausdrücke verwendet, um die Liste der in der Abfrage enthaltenen Elemente zu erstellen, bevor die Abfrage mit den Kriterien der Spezifikation in der letzten Zeile ausgeführt wird.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Tabellenzuordnung** \
  [https://docs.microsoft.com/ef/core/modeling/relational/tables](/ef/core/modeling/relational/tables)

- **Use HiLo to generate keys with Entity Framework Core (Verwenden von Hi/Lo zum Generieren von Schlüsseln mit Entity Framework Core)**  \
  <https://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/>

- **Unterstützungsfelder** \
  [https://docs.microsoft.com/ef/core/modeling/backing-field](/ef/core/modeling/backing-field)

- **Steve Smith. Encapsulated Collections in Entity Framework Core (Gekapselte Auflistungen in Entity Framework Core)**  \
  <https://ardalis.com/encapsulated-collections-in-entity-framework-core>

- **Shadow Properties (Schatteneigenschaften)**  \
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- **The Specification pattern (Spezifikationsmuster)**  \
  <https://deviq.com/specification-pattern/>

> [!div class="step-by-step"]
> [Zurück](infrastructure-persistence-layer-design.md)
> [Weiter](nosql-database-persistence-infrastructure.md)
