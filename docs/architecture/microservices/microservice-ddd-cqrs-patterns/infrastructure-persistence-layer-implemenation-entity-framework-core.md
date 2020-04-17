---
title: Implementieren der Infrastrukturpersistenzebene mit Entity Framework Core
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Übersicht über Implementierungsdetails für die Infrastrukturpersistenzebene mit Entity Framework Core
ms.date: 01/30/2020
ms.openlocfilehash: 7ab3be0d6a5affda478f7ec8f6c356571e304759
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805492"
---
# <a name="implement-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="c0812-103">Implementieren der Infrastrukturpersistenzebene mit Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="c0812-103">Implement the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="c0812-104">Bei der Verwendung von relationalen Datenbanken wie SQL Server, Oracle oder PostgreSQL wird empfohlen, die Persistenzebene auf Entity Framework (EF) basierend zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="c0812-104">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="c0812-105">EF unterstützt LINQ und stellt stark typisierte Objekte für Ihr Modell sowie eine vereinfachte Persistenz für Ihre Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="c0812-105">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="c0812-106">Entity Framework ist bereits seit geraumer Zeit Bestandteil von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0812-106">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="c0812-107">Wenn Sie .NET Core verwenden, sollten Sie auch Entity Framework Core verwenden, das unter Windows oder Linux auf die gleiche Weise wie .NET Core ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-107">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="c0812-108">Bei EF Core handelt es sich um eine vollständig neue Version von Entity Framework, die einen wesentlich geringeren Speicherbedarf hat und wichtige Leistungsverbesserungen mit sich bringt.</span><span class="sxs-lookup"><span data-stu-id="c0812-108">EF Core is a complete rewrite of Entity Framework that's implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="c0812-109">Einführung in Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="c0812-109">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="c0812-110">Entity Framework Core (EF Core) ist eine einfache, erweiterbare und plattformübergreifende Version der beliebten Entity Framework-Datenzugriffstechnologie.</span><span class="sxs-lookup"><span data-stu-id="c0812-110">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="c0812-111">Es wurde Mitte 2016 mit .NET Core eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c0812-111">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="c0812-112">Da in der Microsoft-Dokumentation bereits eine Einführung in EF Core verfügbar ist, werden nachfolgend nur die Links zu diesen Informationen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c0812-112">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="c0812-113">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c0812-113">Additional resources</span></span>

- <span data-ttu-id="c0812-114">**Entity Framework Core** </span><span class="sxs-lookup"><span data-stu-id="c0812-114">**Entity Framework Core** </span></span>\
  [https://docs.microsoft.com/ef/core/](/ef/core/)

- <span data-ttu-id="c0812-115">**Erste Schritte mit ASP.NET Core MVC und Entity Framework Core mithilfe von Visual Studio** </span><span class="sxs-lookup"><span data-stu-id="c0812-115">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio** </span></span>\
  [https://docs.microsoft.com/aspnet/core/data/ef-mvc/](/aspnet/core/data/ef-mvc/)

- <span data-ttu-id="c0812-116">**DbContext-Klasse** </span><span class="sxs-lookup"><span data-stu-id="c0812-116">**DbContext Class** </span></span>\
  [https://docs.microsoft.com/dotnet/api/microsoft.entityframeworkcore.dbcontext](xref:Microsoft.EntityFrameworkCore.DbContext)

- <span data-ttu-id="c0812-117">**Vergleichen von EF Core und EF 6.x** </span><span class="sxs-lookup"><span data-stu-id="c0812-117">**Compare EF Core & EF6.x** </span></span>\
  [https://docs.microsoft.com/ef/efcore-and-ef6/index](/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="c0812-118">Die Infrastruktur in Entity Framework Core aus DDD-Sicht</span><span class="sxs-lookup"><span data-stu-id="c0812-118">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="c0812-119">Aus DDD-Sicht besteht eine wichtige Funktion von EF in der Möglichkeit, POCO-Domänenentitäten zu verwenden. Diese werden in der EF-Terminologie auch als POCO-*Code First-Entitäten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c0812-119">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="c0812-120">Wenn Sie POCO-Domänenentitäten verwenden, sind Ihre Domänenmodellklassen gemäß den Grundsätzen der [Persistenzignoranz](https://deviq.com/persistence-ignorance/) und der [Infrastrukturignoranz](https://ayende.com/blog/3137/infrastructure-ignorance) persistenzignorant.</span><span class="sxs-lookup"><span data-stu-id="c0812-120">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](https://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="c0812-121">Den DDD-Mustern zufolge sollten Sie das Domänenverhalten und die Domänenregeln in der Entitätsklasse selbst einschließen, damit es beim Zugriff auf eine beliebige Auflistung Invarianten, Validierungen und Regeln steuern kann.</span><span class="sxs-lookup"><span data-stu-id="c0812-121">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="c0812-122">Daher ist es in DDD nicht empfehlenswert, einen öffentlichen Zugriff auf Auflistungen untergeordneter Entitäten oder Wertobjekte zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="c0812-122">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="c0812-123">Stattdessen sollten Sie Methoden verfügbar machen, die steuern, wie und wann die Felder und Eigenschaftenauflistungen aktualisiert werden können und welches Verhalten und welche Aktionen in diesem Fall erfolgen sollen.</span><span class="sxs-lookup"><span data-stu-id="c0812-123">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="c0812-124">Seit EF Core 1.1 können Sie zur Erfüllung dieser DDD-Anforderungen in Ihren Entitäten normale Felder anstelle von öffentlichen Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0812-124">Since EF Core 1.1, to satisfy those DDD requirements, you can have plain fields in your entities instead of public properties.</span></span> <span data-ttu-id="c0812-125">Wenn ein Entitätsfeld nicht extern zugänglich sein soll, können Sie nur das Attribut oder Feld anstelle einer Eigenschaft erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0812-125">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="c0812-126">Ferner können Sie private Setter für Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0812-126">You can also use private property setters.</span></span>

<span data-ttu-id="c0812-127">Auf ähnliche Weise ist jetzt ein schreibgeschützter Zugriff auf Auflistungen möglich, indem Sie eine als `IReadOnlyCollection<T>` typisierte öffentliche Eigenschaft verwenden, die durch ein privates Feldelement für die Auflistung (wie `List<T>`) in der Entität gestützt wird, das hinsichtlich der Persistenz auf EF vertraut.</span><span class="sxs-lookup"><span data-stu-id="c0812-127">In a similar way, you can now have read-only access to collections by using a public property typed as  `IReadOnlyCollection<T>`, which is backed by a private field member for the collection (like a `List<T>`) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="c0812-128">Frühere Versionen von Entity Framework benötigten Auflistungseigenschaften, um `ICollection<T>` zu unterstützen, was bedeutete, dass jeder Entwickler, der die übergeordnete Entitätsklasse verwendete, Elemente mithilfe ihrer Eigenschaftenauflistung hinzufügen oder entfernen konnte.</span><span class="sxs-lookup"><span data-stu-id="c0812-128">Previous versions of Entity Framework required collection properties to support `ICollection<T>`, which meant that any developer using the parent entity class could add or remove items through its property collections.</span></span> <span data-ttu-id="c0812-129">Diese Möglichkeit würde den empfohlenen Mustern in DDD zuwiderlaufen.</span><span class="sxs-lookup"><span data-stu-id="c0812-129">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="c0812-130">Wie im folgenden Codebeispiel gezeigt wird, können Sie eine private Auflistung beim Verfügbarmachen eines schreibgeschützten `IReadOnlyCollection<T>`-Objekts verwenden:</span><span class="sxs-lookup"><span data-stu-id="c0812-130">You can use a private collection while exposing a read-only `IReadOnlyCollection<T>` object, as shown in the following code example:</span></span>

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

<span data-ttu-id="c0812-131">Der schreibgeschützte Zugriff auf die Eigenschaft `OrderItems` kann nur über `IReadOnlyCollection<OrderItem>` erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c0812-131">The `OrderItems` property can only be accessed as read-only using `IReadOnlyCollection<OrderItem>`.</span></span> <span data-ttu-id="c0812-132">Dieser Typ ist schreibgeschützt, damit er vor regelmäßigen externen Aktualisierungen geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="c0812-132">This type is read-only so it is protected against regular external updates.</span></span>

<span data-ttu-id="c0812-133">EF Core bietet eine Möglichkeit, das Domänenmodell der physischen Datenbank zuzuordnen, ohne das Domänenmodell zu „verunreinigen“.</span><span class="sxs-lookup"><span data-stu-id="c0812-133">EF Core provides a way to map the domain model to the physical database without "contaminating" the domain model.</span></span> <span data-ttu-id="c0812-134">Dabei handelt es sich um reinen .NET-POCO-Code, da die Zuordnungsaktion in der Persistenzebene implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-134">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="c0812-135">Bei dieser Zuordnungsaktion müssen Sie die Zuordnung zwischen den Feldern und der Datenbank konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c0812-135">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="c0812-136">Im folgenden Beispiel der `OnModelCreating`-Methode von `OrderingContext` und der `OrderEntityTypeConfiguration`Klasse weist der Aufruf von `SetPropertyAccessMode` EF Core an, über ein Feld auf die Eigenschaft `OrderItems` zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c0812-136">In the following example of the `OnModelCreating` method from `OrderingContext` and the `OrderEntityTypeConfiguration` class, the call to `SetPropertyAccessMode` tells EF Core to access the `OrderItems` property through its field.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
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

<span data-ttu-id="c0812-137">Bei Verwendung von Feldern anstelle von Eigenschaften wird die `OrderItem`-Entität so beibehalten, als würde sie eine `List<OrderItem>`-Eigenschaft enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0812-137">When you use fields instead of properties, the `OrderItem` entity is persisted as if it had a `List<OrderItem>` property.</span></span> <span data-ttu-id="c0812-138">Sie hat jedoch einen einzelnen Accessor, die `AddOrderItem`-Methode zum Hinzufügen neuer Elemente zur Bestellung.</span><span class="sxs-lookup"><span data-stu-id="c0812-138">However, it exposes a single accessor, the `AddOrderItem` method, for adding new items to the order.</span></span> <span data-ttu-id="c0812-139">Daher sind das Verhalten und die Daten miteinander verknüpft und innerhalb eines Anwendungscodes, der das Domänenmodell verwendet, konsistent.</span><span class="sxs-lookup"><span data-stu-id="c0812-139">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implement-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="c0812-140">Implementieren von benutzerdefinierten Repositorys mit Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="c0812-140">Implement custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="c0812-141">Auf der Implementierungsebene ist ein Repository lediglich eine Klasse mit Datenpersistenzcode, die bei Aktualisierungen von einer Arbeitseinheit (DBContext in EF Core) koordiniert wird. Dies wird anhand der folgenden Klasse gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c0812-141">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

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

<span data-ttu-id="c0812-142">Die `IBuyerRepository`-Schnittstelle wird von der Domänenmodellebene als Vertrag übernommen.</span><span class="sxs-lookup"><span data-stu-id="c0812-142">The `IBuyerRepository` interface comes from the domain model layer as a contract.</span></span> <span data-ttu-id="c0812-143">Die Repository-Implementierung erfolgt jedoch auf der Persistenz- und Infrastrukturebene.</span><span class="sxs-lookup"><span data-stu-id="c0812-143">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="c0812-144">Der EF-DbContext stammt mittels Abhängigkeitseinfügung aus dem Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="c0812-144">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="c0812-145">Aufgrund seiner Standardlebensdauer (`ServiceLifetime.Scoped`) im IoC-Container (die auch explizit mit `services.AddDbContext<>` festgelegt werden kann) wird er von mehreren Repositorys innerhalb desselben HTTP-Anforderungsbereichs verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0812-145">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (`ServiceLifetime.Scoped`) in the IoC container (which can also be explicitly set with `services.AddDbContext<>`).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="c0812-146">Methoden für die Implementierung in einem Repository (Aktualisierungen oder Transaktionen vs. Abfragen)</span><span class="sxs-lookup"><span data-stu-id="c0812-146">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="c0812-147">In jeder Repository-Klasse sollten Sie die Persistenzmethoden vorsehen, die den Zustand der Entitäten aktualisieren, die in seinem zugehörigen Aggregat enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c0812-147">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="c0812-148">Denken Sie daran, dass zwischen einem Aggregat und dem zugehörigen Repository eine 1:1-Beziehung besteht.</span><span class="sxs-lookup"><span data-stu-id="c0812-148">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="c0812-149">Berücksichtigen Sie, dass ein aggregiertes Stammentitätsobjekt in seinem EF-Graph eingebettete untergeordnete Entitäten aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="c0812-149">Consider that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="c0812-150">Ein Käufer könnte beispielsweise mehrere Zahlungsmethoden als verknüpfte untergeordnete Entitäten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c0812-150">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="c0812-151">Da der Ansatz für den Microservice Bestellung in eShopOnContainers auch auf CQS/CQRS basiert, sind die meisten Abfragen nicht in benutzerdefinierten Repositorys implementiert.</span><span class="sxs-lookup"><span data-stu-id="c0812-151">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="c0812-152">Entwickler können die Abfragen und Verknüpfungen, die sie für die Darstellungsschicht benötigen, ohne die Einschränkungen von Aggregaten, benutzerdefinierten Repositorys pro Aggregat und generell DDD erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0812-152">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="c0812-153">Die meisten der in diesem Leitfaden vorgeschlagenen benutzerdefinierten Repositorys weisen mehrere Aktualisierungs- oder Transaktionsmethoden, aber nur die für das Abrufen der zu aktualisierenden Daten benötigten Abfragemethoden auf.</span><span class="sxs-lookup"><span data-stu-id="c0812-153">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="c0812-154">Das Repository BuyerRepository implementiert beispielsweise eine FindAsync-Methode, da die Anwendung wissen muss, ob ein bestimmter Käufer vorhanden ist, bevor im Zusammenhang mit der Bestellung ein neuer Käufer angelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-154">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="c0812-155">Allerdings werden die tatsächlichen Abfragemethoden für das Abrufen von Daten, die an die Darstellungsschicht oder die Client-Apps gesendet werden, wie erwähnt in den CQRS-Abfragen basierend auf flexiblen Abfragen mit Dapper implementiert.</span><span class="sxs-lookup"><span data-stu-id="c0812-155">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="c0812-156">Verwenden eines benutzerdefinierten Repositorys im Vergleich zu einer direkten Verwendung von EF-DbContext</span><span class="sxs-lookup"><span data-stu-id="c0812-156">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="c0812-157">Die DbContext-Klasse von Entity Framework basiert auf den Mustern „Arbeitseinheit“ und „Repository“ und kann direkt über Ihren Code verwendet werden, beispielsweise über einen ASP.NET Core MVC-Controller.</span><span class="sxs-lookup"><span data-stu-id="c0812-157">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="c0812-158">Die Muster „Arbeitseinheit“ und „Repository“ führen zu sehr einfachem Code wie im CRUD-Katalogmicroservice in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c0812-158">The Unit of Work and Repository patterns result in the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="c0812-159">In Fällen, in denen Sie einen möglichst einfachen Code wünschen, sollten Sie – wie viele andere Entwickler auch – direkt die DbContext-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0812-159">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="c0812-160">Das Implementieren benutzerdefinierter Repositorys bietet jedoch mehrere Vorteile, wenn komplexere Microservices oder Anwendungen umgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c0812-160">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="c0812-161">Die Muster „Arbeitseinheit“ und „Repository“ sollen die Infrastrukturpersistenzebene kapseln, damit sie von den Anwendungs- und Domänenmodellschichten entkoppelt wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-161">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain-model layers.</span></span> <span data-ttu-id="c0812-162">Die Implementierung dieser Muster kann eine Verwendung von Modell-Repositorys ermöglichen, die den Zugriff auf die Datenbank simulieren.</span><span class="sxs-lookup"><span data-stu-id="c0812-162">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="c0812-163">Abbildung 7-18 zeigt die Unterschiede zwischen einer Vorgehensweise ohne Repositorys (d. h. die direkte Verwendung von EF DbContext) im Vergleich zu einer Verwendung von Repositorys, die das Simulieren dieser Repositorys erleichtert.</span><span class="sxs-lookup"><span data-stu-id="c0812-163">In Figure 7-18, you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories, which makes it easier to mock those repositories.</span></span>

![Diagramm, das die Komponenten und den Datenfluss in den beiden Repositorys zeigt.](./media/infrastructure-persistence-layer-implemenation-entity-framework-core/custom-repo-versus-db-context.png)

<span data-ttu-id="c0812-165">**Abbildung 7-18**.</span><span class="sxs-lookup"><span data-stu-id="c0812-165">**Figure 7-18**.</span></span> <span data-ttu-id="c0812-166">Verwenden von benutzerdefinierten Repositorys im Vergleich zu einfachem DbContext</span><span class="sxs-lookup"><span data-stu-id="c0812-166">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="c0812-167">Abbildung 7–18 zeigt, dass die Verwendung eines benutzerdefinierten Repositorys eine Abstraktionsebene hinzufügt, mit der Tests durch das Modellieren des Repositorys vereinfacht werden können.</span><span class="sxs-lookup"><span data-stu-id="c0812-167">Figure 7-18 shows that using a custom repository adds an abstraction layer that can be used to ease testing by mocking the repository.</span></span> <span data-ttu-id="c0812-168">Es gibt mehrere Alternativen für die Modellierung.</span><span class="sxs-lookup"><span data-stu-id="c0812-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="c0812-169">Sie können lediglich Repositorys oder eine vollständige Arbeitseinheit modellieren.</span><span class="sxs-lookup"><span data-stu-id="c0812-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="c0812-170">Üblicherweise reicht es aus, nur die Repositorys zu modellieren. Das komplexe Abstrahieren und Modellieren einer vollständigen Arbeitseinheit ist in der Regel nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c0812-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="c0812-171">Wenn wir uns weiter unten mit der Anwendungsebene befassen, werden Sie sehen, wie die Abhängigkeitseinfügung in ASP.NET Core funktioniert und wie sie bei der Verwendung von Repositorys implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="c0812-172">Mithilfe benutzerdefinierter Repositorys können Sie also Code leichter mit Komponententests prüfen, auf die der Datenschichtzustand keine Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="c0812-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="c0812-173">Wenn Sie Tests ausführen, die auch über Entity Framework auf die eigentliche Datenbank zugreifen, handelt es sich hierbei nicht um Komponententests, sondern um Integrationstests, die deutlich langsamer sind.</span><span class="sxs-lookup"><span data-stu-id="c0812-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="c0812-174">Wenn Sie DbContext direkt verwenden, können Sie Komponententests nur mithilfe einer In-Memory-Instanz von SQL Server mit vorhersagbaren Daten für Komponententests ausführen.</span><span class="sxs-lookup"><span data-stu-id="c0812-174">If you were using DbContext directly, you would have to mock it or to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="c0812-175">Doch das Modellieren von DbContext oder das Steuern falscher Daten erfordern mehr Arbeit als das Modellieren auf Repositoryebene.</span><span class="sxs-lookup"><span data-stu-id="c0812-175">But mocking the DbContext or controlling fake data requires more work than mocking at the repository level.</span></span> <span data-ttu-id="c0812-176">Sie könnten natürlich jederzeit die MVC-Controller testen.</span><span class="sxs-lookup"><span data-stu-id="c0812-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="c0812-177">EF-DbContext und IUnitOfWork-Instanzlebensdauer in Ihrem IoC-Container</span><span class="sxs-lookup"><span data-stu-id="c0812-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="c0812-178">Das `DbContext`-Objekt (verfügbar als `IUnitOfWork`-Objekt) muss von mehreren Repositorys innerhalb desselben HTTP-Anforderungsbereichs gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="c0812-178">The `DbContext` object (exposed as an `IUnitOfWork` object) should be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="c0812-179">Dies ist beispielsweise der Fall, wenn von dem ausgeführten Vorgang mehrere Aggregate betroffen sind oder wenn Sie mehrere Repository-Instanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0812-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="c0812-180">Beachten Sie, dass die `IUnitOfWork`-Schnittstelle Teil Ihrer Domänenebene ist. Es handelt sich dabei nicht um den EF Core-Typ.</span><span class="sxs-lookup"><span data-stu-id="c0812-180">It is also important to mention that the `IUnitOfWork` interface is part of your domain layer, not an EF Core type.</span></span>

<span data-ttu-id="c0812-181">Damit mehrere Repositorys im selben HTTP-Anforderungsbereichs das Objekt gemeinsam nutzen können, muss für die Instanz des `DbContext`-Objekts die Dienstlebensdauer auf „ServiceLifetime.Scoped“ festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="c0812-181">In order to do that, the instance of the `DbContext` object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="c0812-182">Dies ist die Standardlebensdauer beim Registrieren eines `DbContext`-Objekts mit `services.AddDbContext` in Ihrem IoC-Container mit der Methode ConfigureServices der `Startup.cs`-Datei in Ihrem ASP.NET Core-Web-API-Projekt.</span><span class="sxs-lookup"><span data-stu-id="c0812-182">This is the default lifetime when registering a `DbContext` with `services.AddDbContext` in your IoC container from the ConfigureServices method of the `Startup.cs` file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="c0812-183">Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c0812-183">The following code illustrates this.</span></span>

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

<span data-ttu-id="c0812-184">Der Modus der DbContext-Instanziierung sollte nicht als ServiceLifetime.Transient oder ServiceLifetime.Singleton konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c0812-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="c0812-185">Die Lebensdauer der Repository-Instanz in Ihrem IoC-Container</span><span class="sxs-lookup"><span data-stu-id="c0812-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="c0812-186">Auf ähnliche Weise sollte die Lebensdauer des Repositorys in der Regel als bereichsbezogen (InstancePerLifetimeScope in Autofac) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c0812-186">In a similar way, repository's lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="c0812-187">Sie könnte auch vorübergehender Natur sein (InstancePerDependency in Autofac), aber Ihr Service wird speichereffizienter sein, wenn Sie die bereichsbezogene Lebensdauer verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0812-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="c0812-188">Eine Verwendung der Singleton-Lebensdauer für das Repository kann zu ernsthaften Parallelitätsproblemen führen, wenn DbContext auf eine bereichsbezogene (InstancePerLifetimeScope) Lebensdauer festgelegt ist (die Standardlebensdauer für DbContext).</span><span class="sxs-lookup"><span data-stu-id="c0812-188">Using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="c0812-189">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c0812-189">Additional resources</span></span>

- <span data-ttu-id="c0812-190">**Implementieren der Muster Repository und Arbeitseinheit in eine ASP.NET MVC-Anwendung** </span><span class="sxs-lookup"><span data-stu-id="c0812-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application** </span></span>\
  <https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application>

- <span data-ttu-id="c0812-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain (Implementierungsstrategien für das Repositorymuster mit Entity Framework, Dapper und Chain)**  </span><span class="sxs-lookup"><span data-stu-id="c0812-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain** </span></span>\
  <https://www.infoq.com/articles/repository-implementation-strategies>

- <span data-ttu-id="c0812-192">**Cesar de la Torre. Vergleich der Lebensdauer: ASP.NET Core-IoC-Containerdienste vs. Autofac-IoC-Containerinstanzbereiche** </span><span class="sxs-lookup"><span data-stu-id="c0812-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes** </span></span>\
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="table-mapping"></a><span data-ttu-id="c0812-193">Tabellenzuordnung</span><span class="sxs-lookup"><span data-stu-id="c0812-193">Table mapping</span></span>

<span data-ttu-id="c0812-194">Bei der Tabellenzuordnung werden die Tabellendaten identifiziert, die aus der Datenbank abgerufen und in dieser gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c0812-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="c0812-195">Sie haben bereits gesehen, wie Domänenentitäten (z.B. eine Produkt- oder Bestellungsdomäne) verwendet werden können, um ein zugehöriges Datenbankschema zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c0812-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="c0812-196">Bei der Entwicklung von EF spielte das Konzept der *Konventionen* eine wichtige Rolle.</span><span class="sxs-lookup"><span data-stu-id="c0812-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="c0812-197">Konventionen liefern Antworten auf Fragen wie „Wie wird der Name der Tabelle lauten?“</span><span class="sxs-lookup"><span data-stu-id="c0812-197">Conventions address questions like "What will the name of a table be?"</span></span> <span data-ttu-id="c0812-198">oder „Welche Eigenschaft hat der Primärschlüssel?“.</span><span class="sxs-lookup"><span data-stu-id="c0812-198">or "What property is the primary key?"</span></span> <span data-ttu-id="c0812-199">Konventionen basieren in der Regel auf herkömmlichen Namen.</span><span class="sxs-lookup"><span data-stu-id="c0812-199">Conventions are typically based on conventional names.</span></span> <span data-ttu-id="c0812-200">Beispielsweise ist es üblich, dass es sich bei dem Primärschlüssel um eine Eigenschaft handelt, die auf `Id` endet.</span><span class="sxs-lookup"><span data-stu-id="c0812-200">For example, it is typical for the primary key to be a property that ends with `Id`.</span></span>

<span data-ttu-id="c0812-201">Gemäß der Konvention ist jede Entität so eingerichtet, dass sie einer Tabelle mit dem gleichen Namen wie die `DbSet<TEntity>`-Eigenschaft zugeordnet ist, die die Entität für den abgeleiteten Kontext verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c0812-201">By convention, each entity will be set up to map to a table with the same name as the `DbSet<TEntity>` property that exposes the entity on the derived context.</span></span> <span data-ttu-id="c0812-202">Wenn kein `DbSet<TEntity>`-Wert für die betreffende Entität bereitgestellt wird, wird der Klassenname verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0812-202">If no `DbSet<TEntity>` value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="c0812-203">Datenanmerkungen im Vergleich zu Fluent-API</span><span class="sxs-lookup"><span data-stu-id="c0812-203">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="c0812-204">Es gibt viele weitere Konventionen von EF Core, und die meisten von ihnen können entweder mithilfe von Datenanmerkungen oder mit der Fluent-API geändert werden, die innerhalb der OnModelCreating-Methode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-204">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="c0812-205">Datenanmerkungen müssen für die Entitätsmodellklassen selbst verwendet werden. Aus DDD-Sicht ist diese Methode intrusiver.</span><span class="sxs-lookup"><span data-stu-id="c0812-205">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="c0812-206">Dies liegt daran, dass Sie Ihr Modell mit Datenanmerkungen verunreinigen, die mit der Infrastrukturdatenbank verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c0812-206">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="c0812-207">Andererseits ist die Fluent-API eine praktische Methode, um die meisten Konventionen und Zuordnungen in Ihrer Datenpersistenz-Infrastrukturebene zu ändern, sodass das Entitätsmodell bereinigt und von der Persistenzinfrastruktur abgekoppelt wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-207">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="c0812-208">Fluent-API und die OnModelCreating-Methode</span><span class="sxs-lookup"><span data-stu-id="c0812-208">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="c0812-209">Wie bereits erwähnt wurde, können Sie die OnModelCreating-Methode in der DbContext-Klasse verwenden, um Konventionen und Zuordnungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c0812-209">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span>

<span data-ttu-id="c0812-210">Der Microservice Bestellung in eShopOnContainers implementiert bei Bedarf explizit die Zuordnung und Konfiguration, wie der folgende Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="c0812-210">The ordering microservice in eShopOnContainers implements explicit mapping and configuration, when needed, as shown in the following code.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
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

<span data-ttu-id="c0812-211">Sie könnten alle Fluent-API-Zuordnungen innerhalb derselben `OnModelCreating`-Methode festlegen, es ist jedoch ratsam, diesen Code zu untergliedern und wie im Beispiel gezeigt über mehrere Konfigurationsklassen zu verfügen (eine pro Entität).</span><span class="sxs-lookup"><span data-stu-id="c0812-211">You could set all the Fluent API mappings within the same `OnModelCreating` method, but it's advisable to partition that code and have multiple configuration classes, one per entity, as shown in the example.</span></span> <span data-ttu-id="c0812-212">Vor allem bei besonders großen Modellen ist es empfehlenswert, über separate Konfigurationsklassen für das Konfigurieren unterschiedlicher Entitätstypen zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="c0812-212">Especially for large models, it is advisable to have separate configuration classes for configuring different entity types.</span></span>

<span data-ttu-id="c0812-213">Der Code im Beispiel zeigt einige explizite Deklarationen und Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="c0812-213">The code in the example shows a few explicit declarations and mapping.</span></span> <span data-ttu-id="c0812-214">EF Core-Konventionen führen viele dieser Zuordnungen jedoch automatisch aus, sodass der von Ihnen tatsächlich benötigte Code einen geringeren Umfang hätte.</span><span class="sxs-lookup"><span data-stu-id="c0812-214">However, EF Core conventions do many of those mappings automatically, so the actual code you would need in your case might be smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="c0812-215">Der Hi/Lo-Algorithmus in EF Core</span><span class="sxs-lookup"><span data-stu-id="c0812-215">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="c0812-216">Ein interessanter Aspekt des Codes im vorherigen Beispiel ist die Tatsache, dass er den [Hi/Lo-Algorithmus](https://vladmihalcea.com/the-hilo-algorithm/) als Schlüsselgenerierungsstrategie verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0812-216">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="c0812-217">Der Hi/Lo-Algorithmus ist nützlich, wenn Sie eindeutige Schlüssel benötigen, bevor Sie Änderungen committen.</span><span class="sxs-lookup"><span data-stu-id="c0812-217">The Hi/Lo algorithm is useful when you need unique keys before committing changes.</span></span> <span data-ttu-id="c0812-218">Der Hi/Lo-Algorithmus weist im Wesentlichen Tabellenzeilen eindeutige Bezeichner zu, muss die Zeile aber nicht unverzüglich in der Datenbank speichern.</span><span class="sxs-lookup"><span data-stu-id="c0812-218">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="c0812-219">Dadurch können Sie die Bezeichner sofort verwenden – wie bei regulären sequenziellen Datenbank-IDs.</span><span class="sxs-lookup"><span data-stu-id="c0812-219">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="c0812-220">Der Hi/Lo-Algorithmus beschreibt einen Mechanismus zum Abrufen eines Batches von eindeutigen IDs aus einer zugehörigen Datenbanksequenz.</span><span class="sxs-lookup"><span data-stu-id="c0812-220">The Hi/Lo algorithm describes a mechanism for getting a batch of unique IDs from a related database sequence.</span></span> <span data-ttu-id="c0812-221">Die Verwendung dieser IDs gilt als sicher, da die Datenbank die Eindeutigkeit garantiert, sodass keine Konflikte zwischen Benutzern auftreten.</span><span class="sxs-lookup"><span data-stu-id="c0812-221">These IDs are safe to use because the database guarantees the uniqueness, so there will be no collisions between users.</span></span> <span data-ttu-id="c0812-222">Dieser Algorithmus ist aus den folgenden Gründen interessant:</span><span class="sxs-lookup"><span data-stu-id="c0812-222">This algorithm is interesting for these reasons:</span></span>

- <span data-ttu-id="c0812-223">Das Arbeitseinheitsmuster wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="c0812-223">It does not break the Unit of Work pattern.</span></span>

- <span data-ttu-id="c0812-224">Sequenz-IDs werden batchweise abgerufen, um Roundtrips zur Datenbank zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="c0812-224">It gets sequence IDs in batches, to minimize round trips to the database.</span></span>

- <span data-ttu-id="c0812-225">Er generiert einen visuell lesbaren Bezeichner (im Gegensatz zu Techniken, die GUIDs zu verwenden).</span><span class="sxs-lookup"><span data-stu-id="c0812-225">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="c0812-226">EF Core unterstützt wie im vorigen Beispiel gezeigt [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) mit der `UseHiLo`-Methode.</span><span class="sxs-lookup"><span data-stu-id="c0812-226">EF Core supports [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the `UseHiLo` method, as shown in the preceding example.</span></span>

### <a name="map-fields-instead-of-properties"></a><span data-ttu-id="c0812-227">Zuordnen von Feldern anstelle von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c0812-227">Map fields instead of properties</span></span>

<span data-ttu-id="c0812-228">Mit diesem seit EF Core 1.1 verfügbaren Features können Sie direkt Spalten zu Feldern zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c0812-228">With this feature, available since EF Core 1.1, you can directly map columns to fields.</span></span> <span data-ttu-id="c0812-229">Es ist möglich,in der Entitätsklasse keine Eigenschaften zu verwenden und lediglich Spalten einer Tabelle zu Feldern zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c0812-229">It is possible to not use properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="c0812-230">Ein typischer Anwendungsfall hierfür wären private Felder für einen internen Zustand, auf die nicht von außerhalb der Entität zugegriffen werden muss.</span><span class="sxs-lookup"><span data-stu-id="c0812-230">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="c0812-231">Hierzu können Sie einzelne Felder oder auch Auflistungen wie z.B. ein `List<>`-Feld verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0812-231">You can do this with single fields or also with collections, like a `List<>` field.</span></span> <span data-ttu-id="c0812-232">Dieser Punkt wurde bereits oben in Zusammenhang mit dem Modellieren der Domänenmodellklassen erwähnt, aber hier können Sie sehen, wie die Zuordnung mit der `PropertyAccessMode.Field`-Konfiguration ausgeführt wird, die im vorherigen Code gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="c0812-232">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the `PropertyAccessMode.Field` configuration highlighted in the previous code.</span></span>

### <a name="use-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a><span data-ttu-id="c0812-233">Verwenden von auf Infrastrukturebene verborgenen Schatteneigenschaften in EF Core</span><span class="sxs-lookup"><span data-stu-id="c0812-233">Use shadow properties in EF Core, hidden at the infrastructure level</span></span>

<span data-ttu-id="c0812-234">Schatteneigenschaften in EF Core sind Eigenschaften, die nicht in Ihren Entitätsklassenmodell vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c0812-234">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="c0812-235">Die Werte und Zustände dieser Eigenschaften werden ausschließlich in der [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker)-Klasse auf der Infrastrukturebene verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c0812-235">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

## <a name="implement-the-query-specification-pattern"></a><span data-ttu-id="c0812-236">Implementieren des Abfragespezifikationsmusters</span><span class="sxs-lookup"><span data-stu-id="c0812-236">Implement the Query Specification pattern</span></span>

<span data-ttu-id="c0812-237">Wie weiter oben bereits erläutert, ist das Abfragespezifikationsmuster ein domänengesteuertes Entwurfsmuster, das als der Ort konzipiert wurde, an dem Sie die Definition einer Abfrage mit optionaler Sortier- und Auslagerungslogik ablegen können.</span><span class="sxs-lookup"><span data-stu-id="c0812-237">As introduced earlier in the design section, the Query Specification pattern is a Domain-Driven Design pattern designed as the place where you can put the definition of a query with optional sorting and paging logic.</span></span>

<span data-ttu-id="c0812-238">Das Abfragespezifikationsmuster definiert eine Abfrage in einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="c0812-238">The Query Specification pattern defines a query in an object.</span></span> <span data-ttu-id="c0812-239">Um beispielsweise eine ausgelagerte Abfrage, die nach bestimmten Produkten sucht, zu kapseln, können Sie eine PagedProduct-Spezifikation erstellen, die die erforderlichen Eingabeparameter (pageNumber, pageSize, Filter usw.) verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0812-239">For example, in order to encapsulate a paged query that searches for some products you can create a PagedProduct specification that takes the necessary input parameters (pageNumber, pageSize, filter, etc.).</span></span> <span data-ttu-id="c0812-240">Anschließend würde ein IQuerySpecification-Objekt innerhalb einer Repositorymethode (in der Regel eine List()-Überladung) akzeptiert und die erwartete Abfrage anhand dieser Spezifikation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c0812-240">Then, within any Repository method (usually a List() overload) it would accept an IQuerySpecification and run the expected query based on that specification.</span></span>

<span data-ttu-id="c0812-241">Ein Beispiel für eine generische Spezifikationsschnittstelle ist der folgende Code aus [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).</span><span class="sxs-lookup"><span data-stu-id="c0812-241">An example of a generic Specification interface is the following code from [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).</span></span>

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

<span data-ttu-id="c0812-242">Die Implementierung einer generischen Spezifikationsbasisklasse wäre dann die folgende.</span><span class="sxs-lookup"><span data-stu-id="c0812-242">Then, the implementation of a generic specification base class is the following.</span></span>

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

<span data-ttu-id="c0812-243">Die folgende Spezifikation lädt eine einzelne Warenkorbentität entweder anhand der ID des Warenkorbs oder der ID des Käufers, zu dem der Warenkorb gehört.</span><span class="sxs-lookup"><span data-stu-id="c0812-243">The following specification loads a single basket entity given either the basket's ID or the ID of the buyer to whom the basket belongs.</span></span> <span data-ttu-id="c0812-244">Sie lädt die `Items`-Sammlung des Warenkorbs [vorzeitig](/ef/core/querying/related-data).</span><span class="sxs-lookup"><span data-stu-id="c0812-244">It will [eagerly load](/ef/core/querying/related-data) the basket's `Items` collection.</span></span>

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

<span data-ttu-id="c0812-245">Und schließlich sehen Sie unten, wie ein generisches EF-Repository eine solche Spezifikation verwenden kann, um Daten zu filtern und vorzeitig zu laden, die zu einem bestimmten Entitätstypen T gehören.</span><span class="sxs-lookup"><span data-stu-id="c0812-245">And finally, you can see below how a generic EF Repository can use such a specification to filter and eager-load data related to a given entity type T.</span></span>

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

<span data-ttu-id="c0812-246">Zusätzlich zum Kapseln der Filterlogik kann die Spezifikation die Form der zurückzugebenden Daten angeben, einschließlich der aufzufüllenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c0812-246">In addition to encapsulating filtering logic, the specification can specify the shape of the data to be returned, including which properties to populate.</span></span>

<span data-ttu-id="c0812-247">Obwohl davon abgeraten wird, `IQueryable`-Objekte aus einem Repository zurückzugeben, ist es kein Problem, sie innerhalb des Repositorys zum Erstellen eines Resultsets zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0812-247">Although we don't recommend returning `IQueryable` from a repository, it's perfectly fine to use them within the repository to build up a set of results.</span></span> <span data-ttu-id="c0812-248">Sie können die Befolgung dieses Ansatzes oben bei der List-Methode sehen, die zwischengeschaltete `IQueryable`-Ausdrücke verwendet, um die Liste der in der Abfrage enthaltenen Elemente zu erstellen, bevor die Abfrage mit den Kriterien der Spezifikation in der letzten Zeile ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c0812-248">You can see this approach used in the List method above, which uses intermediate `IQueryable` expressions to build up the query's list of includes before executing the query with the specification's criteria on the last line.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="c0812-249">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c0812-249">Additional resources</span></span>

- <span data-ttu-id="c0812-250">**Tabellenzuordnung** </span><span class="sxs-lookup"><span data-stu-id="c0812-250">**Table Mapping** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/relational/tables](/ef/core/modeling/relational/tables)

- <span data-ttu-id="c0812-251">**Use HiLo to generate keys with Entity Framework Core (Verwenden von Hi/Lo zum Generieren von Schlüsseln mit Entity Framework Core)**  </span><span class="sxs-lookup"><span data-stu-id="c0812-251">**Use HiLo to generate keys with Entity Framework Core** </span></span>\
  <https://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/>

- <span data-ttu-id="c0812-252">**Unterstützungsfelder** </span><span class="sxs-lookup"><span data-stu-id="c0812-252">**Backing Fields** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/backing-field](/ef/core/modeling/backing-field)

- <span data-ttu-id="c0812-253">**Steve Smith. Encapsulated Collections in Entity Framework Core (Gekapselte Auflistungen in Entity Framework Core)**  </span><span class="sxs-lookup"><span data-stu-id="c0812-253">**Steve Smith. Encapsulated Collections in Entity Framework Core** </span></span>\
  <https://ardalis.com/encapsulated-collections-in-entity-framework-core>

- <span data-ttu-id="c0812-254">**Shadow Properties (Schatteneigenschaften)**  </span><span class="sxs-lookup"><span data-stu-id="c0812-254">**Shadow Properties** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- <span data-ttu-id="c0812-255">**The Specification pattern (Spezifikationsmuster)**  </span><span class="sxs-lookup"><span data-stu-id="c0812-255">**The Specification pattern** </span></span>\
  <https://deviq.com/specification-pattern/>

> [!div class="step-by-step"]
> <span data-ttu-id="c0812-256">[Zurück](infrastructure-persistence-layer-design.md)
> [Weiter](nosql-database-persistence-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="c0812-256">[Previous](infrastructure-persistence-layer-design.md)
[Next](nosql-database-persistence-infrastructure.md)</span></span>
