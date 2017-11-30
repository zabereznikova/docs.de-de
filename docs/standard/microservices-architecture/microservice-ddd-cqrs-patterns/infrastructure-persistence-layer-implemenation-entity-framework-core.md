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
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="f9a6b-104">Implementieren die Persistenz Infrastrukturebene mit Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="f9a6b-104">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="f9a6b-105">Bei Verwendung von relationalen Datenbanken, z. B. SQL Server, Oracle oder PostgreSQL ist eine empfohlene Vorgehensweise zum Implementieren der Persistenzebene basierend auf Entity Framework (EF).</span><span class="sxs-lookup"><span data-stu-id="f9a6b-105">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="f9a6b-106">EF unterstützt LINQ und stellt stark typisierte Objekte für Ihr Modell als auch vereinfachte Persistenz in die Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-106">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="f9a6b-107">Entity Framework verfügt über eine lange Verlaufsdaten als Teil von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-107">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="f9a6b-108">Wenn Sie .NET Core verwenden, sollten Sie auch Entity Framework Core, verwenden die unter Windows oder Linux ausgeführt, auf die gleiche Weise wie .NET Core wird.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-108">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="f9a6b-109">EF Core handelt es sich um eine vollständig neue Version von Entity Framework, mit einer wesentlich kleineren Platzbedarf und wichtige Verbesserungen der Leistung implementiert.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-109">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="f9a6b-110">Einführung in Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="f9a6b-110">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="f9a6b-111">Entity Framework (EF) Core ist eine einfache, die erweiterbar sind, und plattformübergreifende-Version des beliebten Entity Framework-Daten zugreifen, Technologie.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-111">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="f9a6b-112">Es wurde in der Mitte 2016 mit .NET Core eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-112">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="f9a6b-113">Da eine Einführung in EF Core bereits in der Microsoft-Dokumentation verfügbar ist, bieten wir hier lediglich Links zu diesen Informationen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-113">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="f9a6b-114">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f9a6b-114">Additional resources</span></span>

-   <span data-ttu-id="f9a6b-115">**Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-115">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="f9a6b-116">**Erste Schritte mit ASP.NET Core und Entity Framework Core mithilfe von Visual Studio**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-116">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="f9a6b-117">**DbContext-Klasse**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-117">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="f9a6b-118">**Vergleichen von EF Core & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-118">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="f9a6b-119">Die Infrastruktur in Entity Framework Core im Hinblick auf DDD</span><span class="sxs-lookup"><span data-stu-id="f9a6b-119">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="f9a6b-120">Aus Sicht des eine DDD ist eine wichtige Funktion von EF die Möglichkeit zur Verwendung von POCO-Domain-Entitäten, auch in der EF-Terminologie als POCO bezeichnet *Code First Entitäten*.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-120">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="f9a6b-121">Bei Verwendung von POCO-Domänenentitäten werden Ihren Modellklassen Domäne Dauerhaftigkeit ignorierende, nach der [Persistenz Unkenntnis](http://deviq.com/persistence-ignorance/) und [Infrastruktur Unkenntnis](https://ayende.com/blog/3137/infrastructure-ignorance) Prinzipien.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-121">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="f9a6b-122">Pro DDD-Muster sollten Sie Domänenverhalten und Regeln in die Entitätsklasse, die selbst kapseln, damit es invarianten, Validierungen und Regeln steuern kann, wenn Sie eine beliebige Sammlung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-122">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="f9a6b-123">Aus diesem Grund ist es nicht empfiehlt sich in DDD, öffentlicher Zugriff auf Auflistungen von untergeordneten Entitäten oder rückgabewertobjekte erlauben.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-123">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="f9a6b-124">Sie möchten stattdessen verfügbar machen, Methoden, die steuern, wie und wann die Felder und eigenschaftenauflistungen aktualisiert werden können, und welche Verhalten und Aktionen erfolgen soll, wenn dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-124">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="f9a6b-125">In Version 1.1 EF-Core damit diese DDD-Anforderungen erfüllt werden möglich plain Felder in Ihren Entitäten anstelle von Eigenschaften mit öffentlichen und privaten Setter.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-125">In EF Core 1.1, to satisfy those DDD requirements you can have plain fields in your entities instead of properties with public and private setters.</span></span> <span data-ttu-id="f9a6b-126">Wenn Sie nicht wünschen, dass ein Entitätsfeld extern zugegriffen werden kann, können Sie nur das Attribut oder ein Feld statt einer Objekteigenschaft erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-126">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="f9a6b-127">Es ist nicht erforderlich, private Setter verwenden, falls dieses saubere gewünscht.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-127">There is no need to use private setters if you prefer this cleaner approach.</span></span>

<span data-ttu-id="f9a6b-128">Auf ähnliche Weise, Sie haben jetzt nur-Lese Zugriff auf Auflistungen mithilfe einer öffentlichen Eigenschaft, die als IEnumerable typisiert&lt;T&gt;, denen von einem Mitglied privates Feld für die Sammlung gesichert ist (z. B. eine Liste&lt;&gt;) in Ihrer Entität, die für den permanenten Speicher EF abhängt.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-128">In a similar way, you can now have read-only access to collections by using a public property typed as IEnumerable&lt;T&gt;, which is backed by a private field member for the collection (like a List&lt;&gt;) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="f9a6b-129">Frühere Versionen von Entity Framework benötigten Sammlungseigenschaften zur Unterstützung von ICollection&lt;T&gt;, die vorgesehen, dass alle Entwickler, die mit der übergeordneten Entität-Klasse konnte hinzufügen oder Entfernen von Elementen aus der eigenschaftenauflistungen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-129">Previous versions of Entity Framework required collection properties to support ICollection&lt;T&gt;, which meant that any developer using the parent entity class could add or remove items from its property collections.</span></span> <span data-ttu-id="f9a6b-130">Diese Möglichkeit wäre für die empfohlene Muster in DDD.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-130">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="f9a6b-131">Sie können eine private Auflistung beim Verfügbarmachen einer nur-Lese IEnumerable-Objekt verwenden, wie im folgenden Codebeispiel wird gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9a6b-131">You can use a private collection while exposing a read-only IEnumerable object, as shown in the following code example:</span></span>

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

<span data-ttu-id="f9a6b-132">Beachten Sie, dass die Eigenschaft OrderItems nur zugegriffen werden kann mithilfe der Liste als schreibgeschützt&lt;&gt;. AsReadOnly().</span><span class="sxs-lookup"><span data-stu-id="f9a6b-132">Note that the OrderItems property can only be accessed as read-only using List&lt;&gt;.AsReadOnly().</span></span> <span data-ttu-id="f9a6b-133">Diese Methode erstellt einen schreibgeschützten Wrapper für private Liste, sodass er gegen externe Updates geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-133">This method creates a read-only wrapper around the private list so that it is protected against external updates.</span></span> <span data-ttu-id="f9a6b-134">Ist wesentlich kostengünstiger als die Verwendung der ToList-Methode, da sie keinen kopieren Sie alle Elemente in einer neuen Auflistung. Stattdessen führt es nur ein Heap Alloc-Vorgang für die Wrapperinstanz.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-134">It is much cheaper than using the ToList method, because it does not have to copy all the items in a new collection; instead, it performs just one heap alloc operation for the wrapper instance.</span></span>

<span data-ttu-id="f9a6b-135">EF Core bietet eine Möglichkeit der physischen Datenbank Domänenmodell zuzuordnen, ohne die Domänenmodell Programme.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-135">EF Core provides a way to map the domain model to the physical database without contaminating the domain model.</span></span> <span data-ttu-id="f9a6b-136">Es ist rein POCO .NET Code, da die Zuordnung Aktion in der Persistenzebene implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-136">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="f9a6b-137">In dieser Zuordnung Aktion müssen Sie die Zuordnung der Felder in Datenbank konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-137">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="f9a6b-138">Im folgenden Beispiel einer OnModelCreating-Methode weist der hervorgehobene Code EF-Kerne und der OrderItems-Eigenschaft über dem Feld zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-138">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

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

<span data-ttu-id="f9a6b-139">Bei Verwendung von Feldern anstelle von Eigenschaften wird die OrderItem Entität beibehalten, als ob es sich um eine Liste hatte&lt;OrderItem&gt; Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-139">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="f9a6b-140">Allerdings macht einen einzelnen Accessor (AddOrderItem-Methode) für neue Elemente hinzufügen, um die Reihenfolge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-140">However, it exposes a single accessor (the AddOrderItem method) for adding new items to the order.</span></span> <span data-ttu-id="f9a6b-141">Daher Verhalten und die Daten miteinander verbunden sind, und Sie in der gesamten Anwendungscode, der die Domänenmodell verwendet konsistent sein werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-141">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="f9a6b-142">Implementieren von benutzerdefinierten Repositorys mit Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="f9a6b-142">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="f9a6b-143">Der Ebene der Implementierung ist ein Repository einfach eine Klasse mit Persistenz Datencode eine Arbeitseinheit (DBContext in EF Core) koordinierte Weltzeit. die Ausführung der Updates, wie in der folgenden Klasse dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f9a6b-143">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

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

<span data-ttu-id="f9a6b-144">Beachten Sie, dass die IBuyerRepository-Schnittstelle von der Ebene der Domäne stammen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-144">Note that the IBuyerRepository interface comes from the domain model layer.</span></span> <span data-ttu-id="f9a6b-145">Allerdings erfolgt die Repository-Implementierung zur Persistenz und Infrastrukturebene.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-145">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="f9a6b-146">EF DbContext wird über den Konstruktor über Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-146">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="f9a6b-147">Es wird von mehreren Repositorys innerhalb des Bereichs der gleiche HTTP-Anforderung, Dank seiner Standardlebensdauer (ServiceLifetime.Scoped) in der IoC-Container gemeinsam genutzt (die auch explizit mit Diensten festgelegt werden kann. AddDbContext&lt;&gt;).</span><span class="sxs-lookup"><span data-stu-id="f9a6b-147">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="f9a6b-148">Methoden, die in einem Repository (Updates oder Transaktionen im Vergleich zu Abfragen) implementiert.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-148">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="f9a6b-149">Innerhalb jedes Repository-Klasse sollten Sie die persistenzmethoden abgelegt, die den Status der von seiner verwandten Aggregat enthaltenen Entitäten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-149">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="f9a6b-150">Denken Sie daran, dass zwischen ein Aggregat und seine zugehörigen Repository: 1-Beziehung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-150">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="f9a6b-151">Müssen Sie berücksichtigen, dass ein Entitätsobjekt aggregieren Stamm untergeordneten Entitäten innerhalb seines Diagramms EF eingebettet haben kann.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-151">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="f9a6b-152">Z. B. möglicherweise ein Käufer mehrere Zahlungsmethoden als verknüpfte untergeordnete Entitäten.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-152">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="f9a6b-153">Da der Ansatz für die Sortierung Microservice in eShopOnContainers auch CQS/CQRS basiert, sind die meisten Abfragen in benutzerdefinierten Repositorys nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-153">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="f9a6b-154">Entwickler haben die Möglichkeit zum Erstellen der Abfragen und Joins, die ohne den Einschränkungen von Aggregate, benutzerdefinierte Repositorys pro zusammenzufassen und DDD im Allgemeinen für die Darstellungsschicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-154">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="f9a6b-155">Die meisten der benutzerdefinierten Repositorys wird in diesem Handbuch vorgeschlagene haben mehrere Update- oder transaktionale Methoden, aber nur die Abfragemethoden benötigt wird, zum Abrufen von Daten aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-155">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="f9a6b-156">Beispielsweise implementiert BuyerRepository Repository eine FindAsync-Methode, da die Anwendung muss wissen, ob ein bestimmtes kaufen, die vor dem Erstellen eines neuen Käufers im Zusammenhang mit der Reihenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-156">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="f9a6b-157">Allerdings werden die echte Abfragemethoden zum Abrufen von Daten an die Präsentation Ebene oder Client-apps implementiert, wie erwähnt, in den CQRS-Abfragen basierend auf flexible Abfragen, die mit dapper, durch.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-157">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="f9a6b-158">Verwenden einer benutzerdefinierten Repository im Vergleich zum Verwenden von EF DbContext direkt</span><span class="sxs-lookup"><span data-stu-id="f9a6b-158">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="f9a6b-159">Die Entity Framework DbContext-Klasse basiert auf den Mustern Unit of Work und des Repositorys und genutzt werden direkt aus Ihrem Code, z. B. auf einem ASP.NET Core MVC-Controller.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-159">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="f9a6b-160">D. h. die Möglichkeit können Sie den einfachsten Code, wie die CRUD-Katalog Microservice in eShopOnContainers erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-160">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="f9a6b-161">In Fällen den einfachsten Code möglich, sollten Sie die DbContext-Klasse direkt verwenden, wie viele Entwickler.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-161">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="f9a6b-162">Implementieren benutzerdefinierte Repositorys bietet jedoch mehrere Vorteile beim komplexere Microservices oder Anwendungen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-162">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="f9a6b-163">Die Muster Unit of Work und des Repositorys sollen die Persistenz-Infrastrukturebene zu kapseln, damit diese von der Anwendung und die Domäne Modell Ebenen entkoppelt wird.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-163">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="f9a6b-164">Implementieren diese Muster Endprodukts bei der Verwendung von simulierten Repositorys, die Zugriff auf die Datenbank zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-164">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="f9a6b-165">In Abbildung 9 – 18 können Sie die Unterschiede zwischen der Verwendung nicht Repositorys (direkt mit EF DbContext) anzeigen, im Vergleich zum Verwenden des Repositorys, die diese Repositorys modellieren vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-165">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="f9a6b-166">**Abbildung 9 – 18**.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-166">**Figure 9-18**.</span></span> <span data-ttu-id="f9a6b-167">Verwenden von benutzerdefinierten Repositorys im Vergleich zu einer einfachen DbContext</span><span class="sxs-lookup"><span data-stu-id="f9a6b-167">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="f9a6b-168">Es gibt mehrere alternativen imitieren.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="f9a6b-169">Konnten Sie nur Repositorys modellieren, oder Sie können eine gesamte Arbeitseinheit modellieren.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="f9a6b-170">Simulieren einfach den Repositorys in der Regel reicht aus, und die Komplexität zu abstrahieren simulieren Sie eine gesamte Arbeitseinheit ist in der Regel nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="f9a6b-171">Später, wenn wir uns auf die Anwendungsschicht konzentrieren, sehen Sie Abhängigkeitsinjektion in ASP.NET Core wie funktioniert und wie es bei Verwendung des Repositorys implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="f9a6b-172">Kurz gesagt, können mit benutzerdefinierten Repositorys Code leichter mit Komponententests zu testen, die durch den Data-Tier-Zustand nicht beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="f9a6b-173">Wenn Sie Tests, die auch Zugriff auf die aktuelle Datenbank über das Entity Framework ausführen, sind sie nicht Komponententests jedoch Integrationstests, die viel langsamer sind.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="f9a6b-174">Wenn DbContext direkt verwendet haben, wäre die einzige Option, die Sie zum Ausführen von Komponententests mithilfe einer in-Memory-SQL-Server mit vorhersagbaren Daten für Komponententests.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-174">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="f9a6b-175">Steuern von Pseudoobjekten und falschen Daten auf die gleiche Weise auf die Repository-Ebene ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-175">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="f9a6b-176">Natürlich können Sie immer die MVC-Controller testen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="f9a6b-177">EF DbContext und IUnitOfWork Instanz Lebensdauer im IoC-container</span><span class="sxs-lookup"><span data-stu-id="f9a6b-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="f9a6b-178">Die DbContext-Objekt (die als IUnitOfWork Objekt verfügbar gemacht) möglicherweise von mehreren Repositorys innerhalb desselben Gültigkeitsbereichs der HTTP-Anforderung gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-178">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="f9a6b-179">Beispielsweise gilt dies, wenn der Vorgang ausgeführt wird, mehrere Aggregate oder einfach beschäftigen muss, da Sie mehrere Instanzen von Repository verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="f9a6b-180">Es ist auch wichtig zu erwähnen, dass die Schnittstelle IUnitOfWork Teil der Domäne sind, keinen EF-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-180">It is also important to mention that the IUnitOfWork interface is part of the domain, not an EF type.</span></span>

<span data-ttu-id="f9a6b-181">Zu diesem Zweck muss die Instanz des Objekts DbContext seine Lebensdauer von Diensten auf ServiceLifetime.Scoped festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-181">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="f9a6b-182">Dies ist die Standardlebensdauer Wenn services registrieren ein ' DbContext ' mit. AddDbContext im IoC-Container aus der Datei "Startup.cs" in Ihrem Projekt ASP.NET Core Web-API der ConfigureServices-Methode.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-182">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="f9a6b-183">Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-183">The following code illustrates this.</span></span>

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

<span data-ttu-id="f9a6b-184">Der Modus der DbContext-Instanziierung sollte nicht als ServiceLifetime.Transient oder ServiceLifetime.Singleton konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="f9a6b-185">Die Lebensdauer der Repository-Instanz im IoC-container</span><span class="sxs-lookup"><span data-stu-id="f9a6b-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="f9a6b-186">Auf ähnliche Weise sollte die Lebensdauer des Repositorys in der Regel als Bereichsbezogene (InstancePerLifetimeScope in Autofac) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-186">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="f9a6b-187">Unter Umständen liegen auch vorübergehend (InstancePerDependency in Autofac), aber der Dienst wird hinsichtlich Arbeitsspeicher effizienter sein, wenn Sie die Bereichsbezogene Lebensdauer verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="f9a6b-188">Beachten Sie, dass die Singleton-Lebensdauer für das Repository Sie schwerwiegende Probleme verursachen könnte, wenn Ihre ' DbContext ' festgelegt ist, beschränkt (InstancePerLifetimeScope) Lebensdauer (den Standard-Lebensdauer für ein ' DbContext ').</span><span class="sxs-lookup"><span data-stu-id="f9a6b-188">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="f9a6b-189">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f9a6b-189">Additional resources</span></span>

-   <span data-ttu-id="f9a6b-190">**Implementieren das Repository und die Einheit der Arbeit Muster in einer ASP.NET MVC-Anwendung**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="f9a6b-191">**Jonathan Abläufe. Implementierungsstrategien für das Repository mit Entity Framework, Dapper, Muster und verketten**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="f9a6b-192">**Cesar de la Torre. Vergleichen von ASP.NET Core IoC-Container Dienst Lebensdauer mit Autofac IoC-Container Instanz Bereichen**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="f9a6b-193">Zuordnung zu einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="f9a6b-193">Table mapping</span></span>

<span data-ttu-id="f9a6b-194">Tabellenzuordnung identifiziert die Tabellendaten aus abgefragt werden und in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="f9a6b-195">Zuvor haben Sie gesehen, wie Domänenentitäten (z. B. ein Produkt oder eine Bestellung Domäne) generieren eines Schemas für die verbundene Datenbank verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="f9a6b-196">EF dient stark auf dem Konzept von *Konventionen*.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="f9a6b-197">Konventionen Adresse Fragen wie "Welche der Namen einer Tabelle werden?"</span><span class="sxs-lookup"><span data-stu-id="f9a6b-197">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="f9a6b-198">oder "welche Eigenschaft ist der primäre Schlüssel?"</span><span class="sxs-lookup"><span data-stu-id="f9a6b-198">or “What property is the primary key?”</span></span> <span data-ttu-id="f9a6b-199">Konventionen basieren normalerweise auf herkömmliche Namen – z. B. befindet er sich typisch für den primären Schlüssel als eine Eigenschaft, die mit der ID endet</span><span class="sxs-lookup"><span data-stu-id="f9a6b-199">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="f9a6b-200">Gemäß der Konvention jede Entität wird eingerichtet sein, dass eine Tabelle mit dem gleichen Namen wie die DbSet zuordnen&lt;TEntity&gt; Eigenschaft, die die Entität für den abgeleiteten Kontext verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-200">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="f9a6b-201">Wenn keine DbSet&lt;TEntity&gt; Wert ist, sofern für die angegebene Entität, der Name der Klasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-201">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="f9a6b-202">Datenanmerkungen im Vergleich zu Fluent-API</span><span class="sxs-lookup"><span data-stu-id="f9a6b-202">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="f9a6b-203">Es gibt viele weitere EF-Core-Konventionen, und die meisten von ihnen können mithilfe von datenanmerkungen oder der Fluent-API implementiert, innerhalb der OnModelCreating-Methode geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-203">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="f9a6b-204">Datenanmerkungen müssen auf den Entitätsklassen für das Modell selbst verwendet werden, dies ist eine auffallendere Methode aus der Sicht eine DDD.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-204">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="f9a6b-205">Dies liegt daran führen Datenkonsistenz Ihr Modell mit datenanmerkungen im Zusammenhang mit der Infrastruktur-Datenbank beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-205">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="f9a6b-206">Andererseits, ist die Fluent-API eine einfache Möglichkeit, die meisten Konventionen und Zuordnungen in Ihrer Infrastruktur datenpersistenzebene ändern, damit das Entitätsmodell bereinigen und aus der Persistenz-Infrastruktur abgekoppelt werden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-206">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="f9a6b-207">Fluent-API und der OnModelCreating-Methode</span><span class="sxs-lookup"><span data-stu-id="f9a6b-207">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="f9a6b-208">Wie bereits erwähnt, können Sie aus um Konventionen und Zuordnungen, ändern die OnModelCreating-Methode in der DbContext-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-208">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> <span data-ttu-id="f9a6b-209">Das folgende Beispiel zeigt, wie wir dies in der Reihenfolge Microservice in eShopOnContainers durchführen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-209">The following example shows how we do this in the ordering microservice in eShopOnContainers.</span></span>

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

<span data-ttu-id="f9a6b-210">Konnten Sie die Fluent-API-Zuordnungen innerhalb der gleichen OnModelCreating-Methode festgelegt, aber es ist ratsam, Partitionieren diesen Code und mehrere Submethods, eine pro Entität haben, wie im Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-210">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple submethods, one per entity, as shown in the example.</span></span> <span data-ttu-id="f9a6b-211">Bei besonders großen Modellen kann es auch ratsam, separate Quelldateien (statische Klassen) zur Konfiguration der anderen Entitätstypen sein.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-211">For particularly large models, it can even be advisable to have separate source files (static classes) for configuring different entity types.</span></span>

<span data-ttu-id="f9a6b-212">Der Code im Beispiel ist explizit.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-212">The code in the example is explicit.</span></span> <span data-ttu-id="f9a6b-213">EF Core Konventionen führen die meisten dieser jedoch automatisch, deshalb ist der tatsächliche Code, den Sie dasselbe Ziel erreichen schreiben müssen wesentlich kleiner.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-213">However, EF Core conventions do most of this automatically, so the actual code you would need to write to achieve the same thing would be much smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="f9a6b-214">Der Algorithmus Hi/Lo in EF Core</span><span class="sxs-lookup"><span data-stu-id="f9a6b-214">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="f9a6b-215">Ein interessanter Aspekt der Code im vorherigen Beispiel ist, verwendet der [Hi/Lo Algorithmus](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) als die Generierung von Zertifizierungsstellenschlüsseln-Strategie.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-215">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="f9a6b-216">Der Algorithmus Hi/Lo ist nützlich, wenn Sie eindeutige Schlüssel benötigen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-216">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="f9a6b-217">Als eine Zusammenfassung weist der Hi-Lo Algorithmus eindeutige Bezeichner zu Tabellenzeilen aus, während nicht je nach der Zeile sofort in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-217">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="f9a6b-218">Dadurch können Sie den Einstieg in die Bezeichner sofort, wie bei regulären sequenzielle Datenbank-IDs geschieht.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-218">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="f9a6b-219">Der Algorithmus Hi/Lo beschreibt einen Mechanismus zum Generieren von safe-IDs auf der Clientseite und nicht in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-219">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="f9a6b-220">*Sichere* bedeutet, dass in diesem Kontext ohne Konflikte.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-220">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="f9a6b-221">Bei diesem Algorithmus handelt es sich um interessante aus diesen Gründen:</span><span class="sxs-lookup"><span data-stu-id="f9a6b-221">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="f9a6b-222">Das Muster Unit of Work wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-222">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="f9a6b-223">Sie erfordert keine Roundtrips Weise Sequenz-Generatoren in andere DBMS-Systeme zu tun.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-223">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="f9a6b-224">Er generiert einen Menschen lesbaren Bezeichner, im Gegensatz zu Techniken, die GUIDs zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-224">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="f9a6b-225">EF Core unterstützt [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) mit ForSqlServerUseSequenceHiLo-Methode, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-225">EF Core supports [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="f9a6b-226">Zuordnen von Feldern anstelle von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f9a6b-226">Mapping fields instead of properties</span></span>

<span data-ttu-id="f9a6b-227">Mit der Funktion von EF Core 1.1, die Spalten zu Feldern zugeordnet werden soll, ist es möglich, die keine Eigenschaften in die Entitätsklasse verwendet werden, und nur Spalten aus einer Tabelle Felder zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-227">With the feature of EF Core 1.1 that maps columns to fields, it is possible to not use any properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="f9a6b-228">Eine übliche Verwendung für diese wäre private Felder für alle internen Status, die nicht von außerhalb der Entität zugegriffen werden muss.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-228">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="f9a6b-229">EF 1.1 unterstützt eine Möglichkeit, ein Feld ohne eine zugehörige Eigenschaft einer Spalte in der Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-229">EF 1.1 supports a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="f9a6b-230">Hierzu können Sie einzelne Felder oder auch mit Auflistungen, wie eine Liste&lt; &gt; Feld.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-230">You can do this with single fields or also with collections, like a List&lt;&gt; field.</span></span> <span data-ttu-id="f9a6b-231">Bisher wurde weiter oben erwähnt, werden beim Modellieren der Domäne Modellklassen besprochen, jedoch hier Sie sehen können, wie die Zuordnung ausgeführt wird, mit der PropertyAccessMode.Field-Konfiguration, die im vorherigen Code hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-231">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the PropertyAccessMode.Field configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a><span data-ttu-id="f9a6b-232">Verwenden von Shadowing von Eigenschaften in rückgabewertobjekte für ausgeblendete-IDs auf der Infrastrukturebene</span><span class="sxs-lookup"><span data-stu-id="f9a6b-232">Using shadow properties in value objects for hidden IDs at the infrastructure level</span></span>

<span data-ttu-id="f9a6b-233">Shadowing von Eigenschaften in EF Core sind Eigenschaften, die nicht in Ihrer Klasse Entitätsmodell vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-233">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="f9a6b-234">Die Werte und den Status dieser Eigenschaften werden ausschließlich in verwaltet die [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) Klasse auf Infrastrukturebene.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-234">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

<span data-ttu-id="f9a6b-235">Aus Sicht des eine DDD sind Shadowing von Eigenschaften für eine einfache Möglichkeit, den Wert-Objekte implementieren, indem Sie die ID als primären Schlüssel für eine Schattenkopie ausblenden.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-235">From a DDD point of view, shadow properties are a convenient way to implement value objects by hiding the ID as a shadow property primary key.</span></span> <span data-ttu-id="f9a6b-236">Dies ist wichtig, da ein Wertobjekt Identität keinen sollten (über mindestens Sie müssen nicht die ID in der Domäne der Ebene beim Strukturieren der Value-Objekte).</span><span class="sxs-lookup"><span data-stu-id="f9a6b-236">This is important, because a value object should not have identity (at least, you should not have the ID in the domain model layer when shaping value objects).</span></span> <span data-ttu-id="f9a6b-237">Das Hierbei ist, dass zum Zeitpunkt der aktuellen Version von EF Core, EF Core eine Möglichkeit zum Implementieren des Value-Objekte als keinen [komplexe Typen](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), wie möglich in EF 6.x.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-237">The point here is that as of the current version of EF Core, EF Core does not have a way to implement value objects as [complex types](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), as is possible in EF 6.x.</span></span> <span data-ttu-id="f9a6b-238">Aus diesem Grund müssen Sie zurzeit implementieren ein Wertobjekt als eine Entität mit einer ausgeblendeten-ID (Primärschlüssel) als ein Schatten-Eigenschaft festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-238">That is why you currently need to implement a value object as an entity with a hidden ID (primary key) set as a shadow property.</span></span>

<span data-ttu-id="f9a6b-239">Wie in der Sie sehen die [Wert Adressobjekt](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, im Modell Adresse nicht angezeigt. ID:</span><span class="sxs-lookup"><span data-stu-id="f9a6b-239">As you can see in the [Address value object](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, in the Address model you do not see an ID:</span></span>

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

<span data-ttu-id="f9a6b-240">Aber im Hintergrund müssen wir eine ID bereitstellen, sodass EF Core diese Daten in Tabellen der Datenbank beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-240">But under the covers, we need to provide an ID so that EF Core is able to persist this data in the database tables.</span></span> <span data-ttu-id="f9a6b-241">Wir machen, die in der Methode ConfigureAddress der [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) Klasse auf der Infrastrukturebene, damit wir das Domänenmodell mit EF Infrastrukturcode nicht beschädigt sind.</span><span class="sxs-lookup"><span data-stu-id="f9a6b-241">We do that in the ConfigureAddress method of the [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) class at the infrastructure level, so we do not pollute the domain model with EF infrastructure code.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="f9a6b-242">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f9a6b-242">Additional resources</span></span>

-   <span data-ttu-id="f9a6b-243">**Tabelle der Zuordnung**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-243">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="f9a6b-244">**Verwenden Sie zum Generieren von Schlüsseln mit Entity Framework Core HiLo**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-244">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="f9a6b-245">**Sichern die Felder**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-245">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="f9a6b-246">**Steve Smith. Sammlungen in Entity Framework Core gekapselt**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-246">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="f9a6b-247">**Shadowing von Eigenschaften**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-247">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f9a6b-248">[Vorherigen] (Infrastruktur-Persistenz-Ebene – design.md) [weiter] (Nosql-Datenbank-Persistenz-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="f9a6b-248">[Previous] (infrastructure-persistence-layer-design.md) [Next] (nosql-database-persistence-infrastructure.md)</span></span>
