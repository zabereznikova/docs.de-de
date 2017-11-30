---
title: "Ein Microservice Domänenmodell mit .NET Core implementieren"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Ein Microservice Domänenmodell mit .NET Core implementieren"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a><span data-ttu-id="d0e5f-104">Ein Microservice Domänenmodell mit .NET Core implementieren</span><span class="sxs-lookup"><span data-stu-id="d0e5f-104">Implementing a microservice domain model with .NET Core</span></span> 

<span data-ttu-id="d0e5f-105">Im vorherigen Abschnitt wurden die grundlegenden Entwurfsprinzipien und das Muster für das Entwerfen ein Domänenmodell erläutert.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-105">In the previous section, the fundamental design principles and patterns for designing a domain model were explained.</span></span> <span data-ttu-id="d0e5f-106">Jetzt es Zeit zum Untersuchen von Möglichkeiten, implementieren Sie die Domänenmodell mit .NET Core ist (plain C\# Code) und EF Core.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-106">Now it is time to explore possible ways to implement the domain model by using .NET Core (plain C\# code) and EF Core.</span></span> <span data-ttu-id="d0e5f-107">Beachten Sie, dass Ihre Domänenmodell einfach Code besteht.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-107">Note that your domain model will be composed simply of your code.</span></span> <span data-ttu-id="d0e5f-108">Es wird nur das Modell im EF kernanforderungen, jedoch keine echten Abhängigkeiten für EF verfügen.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-108">It will have just the EF Core model requirements, but not real dependencies on EF.</span></span> <span data-ttu-id="d0e5f-109">Sie sollten kein harte Abhängigkeiten oder Verweise auf EF-Core-Installationen oder anderen ORM-in Ihrem Domänenmodell aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-109">You should not have hard dependencies or references to EF Core or any other ORM in your domain model.</span></span>

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a><span data-ttu-id="d0e5f-110">Modell Domänenstruktur in einer benutzerdefinierten .NET Standard-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="d0e5f-110">Domain model structure in a custom .NET Standard library</span></span>

<span data-ttu-id="d0e5f-111">Ordnerorganisation, die für die Anwendung der eShopOnContainers Verweis verwendet veranschaulicht das DDD-Modell für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-111">The folder organization used for the eShopOnContainers reference application demonstrates the DDD model for the application.</span></span> <span data-ttu-id="d0e5f-112">Möglicherweise eine anderen Ordnerorganisation deutlicher Entwurf gewählten Optionen für Ihre Anwendung kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-112">You might find that a different folder organization more clearly communicates the design choices made for your application.</span></span> <span data-ttu-id="d0e5f-113">Wie Sie in Abbildung 9 – 10 sehen können, in der Reihenfolge Domänenmodell sind zwei Aggregate, das Aggregat Reihenfolge und den Käufer-Aggregat.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-113">As you can see in Figure 9-10, in the ordering domain model there are two aggregates, the order aggregate and the buyer aggregate.</span></span> <span data-ttu-id="d0e5f-114">Jedes Aggregat ist eine Gruppe von Domänenentitäten und Value-Objekte, obwohl Sie ein Aggregat besteht aus einer Einzeldomäne Entität (aggregieren Stamm oder Stammentität) sowie möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-114">Each aggregate is a group of domain entities and value objects, although you could have an aggregate composed of a single domain entity (the aggregate root or root entity) as well.</span></span>

![](./media/image11.png)

<span data-ttu-id="d0e5f-115">**Abbildung 9 – 10**.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-115">**Figure 9-10**.</span></span> <span data-ttu-id="d0e5f-116">Modell Domänenstruktur für die Sortierung Microservice in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="d0e5f-116">Domain model structure for the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="d0e5f-117">Darüber hinaus umfasst der Domäne der Ebene der Repository-Verträge (Schnittstellen), die die Anforderungen an die Infrastruktur des Modells Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-117">Additionally, the domain model layer includes the repository contracts (interfaces) that are the infrastructure requirements of your domain model.</span></span> <span data-ttu-id="d0e5f-118">Das heißt, diese Schnittstellen express welche Repositorys, die die Infrastrukturebene implementieren muss und wie.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-118">In other words, these interfaces express what repositories the infrastructure layer must implement and how.</span></span> <span data-ttu-id="d0e5f-119">Es ist wichtig, dass die Implementierung der Repositorys außerhalb der Modellebene Domäne in der Bibliothek der formularinfrastruktur Ebene platziert werden, damit die Domäne der Ebene nicht "durch-API oder Klassen von Technologien, wie Entity Framework-Infrastruktur verunreinigt ist".</span><span class="sxs-lookup"><span data-stu-id="d0e5f-119">It is critical that the implementation of the repositories be placed outside of the domain model layer, in the infrastructure layer library, so the domain model layer is not “contaminated” by API or classes from infrastructure technologies, like Entity Framework.</span></span>

<span data-ttu-id="d0e5f-120">Sie sehen auch eine [SeedWork](https://martinfowler.com/bliki/Seedwork.html) Ordner mit benutzerdefinierten Basisklassen, die Sie als Basis für Ihre Domänenentitäten und Wert verwenden können Objekte, müssen Sie nicht redundanten Code in jeder Domäne Objektklasse.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-120">You can also see a [SeedWork](https://martinfowler.com/bliki/Seedwork.html) folder that contains custom base classes that you can use as a base for your domain entities and value objects, so you do not have redundant code in each domain’s object class.</span></span>

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a><span data-ttu-id="d0e5f-121">Strukturieren von Aggregaten in einer benutzerdefinierten .NET Standard-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="d0e5f-121">Structuring aggregates in a custom .NET Standard library</span></span>

<span data-ttu-id="d0e5f-122">Ein Aggregat bezieht sich auf einem Cluster mit Domänenobjekte Transaktionskonsistenz entsprechend gruppiert.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-122">An aggregate refers to a cluster of domain objects grouped together to match transactional consistency.</span></span> <span data-ttu-id="d0e5f-123">Diese Objekte möglicherweise Entitäteninstanzen (von denen die aggregierten Stamm- oder Stammentität ist) sowie alle zusätzlichen Wert Objekte.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-123">Those objects could be instances of entities (one of which is the aggregate root or root entity) plus any additional value objects.</span></span>

<span data-ttu-id="d0e5f-124">Transaktionskonsistenz bedeutet, dass ein Aggregat unbedingt konsistent und am Ende einer Business-Aktion auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-124">Transactional consistency means that an aggregate is guaranteed to be consistent and up to date at the end of a business action.</span></span> <span data-ttu-id="d0e5f-125">Das Order-Aggregat aus der Sortierung Microservice Domänenmodell eShopOnContainers besteht z. B. wie in Abbildung 9 – 11 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-125">For example, the order aggregate from the eShopOnContainers ordering microservice domain model is composed as shown in Figure 9-11.</span></span>

![](./media/image12.png)

<span data-ttu-id="d0e5f-126">**Abbildung 9 – 11**.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-126">**Figure 9-11**.</span></span> <span data-ttu-id="d0e5f-127">Die Reihenfolge, die in Visual Studio-Projektmappe aggregieren</span><span class="sxs-lookup"><span data-stu-id="d0e5f-127">The order aggregate in Visual Studio solution</span></span>

<span data-ttu-id="d0e5f-128">Wenn Sie eine der Dateien im Ordner "aggregate" öffnen, sehen Sie wie sie markiert ist, als benutzerdefinierte Basisklasse oder Schnittstelle, wie die Entität oder Wert-Objekt, wie im implementiert die [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) Ordner.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-128">If you open any of the files in an aggregate folder, you can see how it is marked as either a custom base class or interface, like entity or value object, as implemented in the [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) folder.</span></span>

## <a name="implementing-domain-entities-as-poco-classes"></a><span data-ttu-id="d0e5f-129">Implementieren von Domänenentitäten als POCO-Klassen</span><span class="sxs-lookup"><span data-stu-id="d0e5f-129">Implementing domain entities as POCO classes</span></span>

<span data-ttu-id="d0e5f-130">Sie implementieren ein Domänenmodell in .NET durch das Erstellen von POCO-Klassen, die die Domänenentitäten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-130">You implement a domain model in .NET by creating POCO classes that implement your domain entities.</span></span> <span data-ttu-id="d0e5f-131">Im folgenden Beispiel wird die Order-Klasse als Entität und auch als aggregate Stammzertifizierungsstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-131">In the following example, the Order class is defined as an entity and also as an aggregate root.</span></span> <span data-ttu-id="d0e5f-132">Da die Order-Klasse von der Entität Basisklasse abgeleitet ist, können sie allgemeine Code in Bezug auf Entitäten wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-132">Because the Order class derives from the Entity base class, it can reuse common code related to entities.</span></span> <span data-ttu-id="d0e5f-133">Beachten Sie, dass diese Basis-Klassen und Schnittstellen von Ihnen in der Domäne Modellprojekt, definiert sind daher ist es Ihr Code, der nicht über ein ORM wie EF Infrastrukturcode der Diagnosefunktion berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-133">Bear in mind that these base classes and interfaces are defined by you in the domain model project, so it is your code, not infrastructure code from an ORM like EF.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

<span data-ttu-id="d0e5f-134">Es ist wichtig zu beachten, dass dies eine Entität "Domain" als POCO-Klasse implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-134">It is important to note that this is a domain entity implemented as a POCO class.</span></span> <span data-ttu-id="d0e5f-135">Es ist keine direkte Abhängigkeit von Entity Framework Core oder andere Infrastruktur-Framework kein.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-135">It does not have any direct dependency on Entity Framework Core or any other infrastructure framework.</span></span> <span data-ttu-id="d0e5f-136">Diese Implementierung ist, sollte es sein, nur C#\# Code ein Domänenmodell implementieren.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-136">This implementation is as it should be, just C\# code implementing a domain model.</span></span>

<span data-ttu-id="d0e5f-137">Darüber hinaus wird die Klasse mit einer Schnittstelle, die mit dem Namen IAggregateRoot ergänzt.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-137">In addition, the class is decorated with an interface named IAggregateRoot.</span></span> <span data-ttu-id="d0e5f-138">Diese Schnittstelle ist eine leere Schnittstelle, bezeichnet einen *markerschnittstelle*, d. h. nur, um anzugeben, dass dieser Entitätsklasse auch einen aggregierten Stamm wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-138">That interface is an empty interface, sometimes called a *marker interface*, that is used just to indicate that this entity class is also an aggregate root.</span></span>

<span data-ttu-id="d0e5f-139">Eine markerschnittstelle wird manchmal als ein Antimuster betrachtet. Es ist jedoch auch eine fehlerfreie Möglichkeit, eine Klasse zu markieren, insbesondere, wenn diese Schnittstelle möglicherweise weiterentwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-139">A marker interface is sometimes considered as an anti-pattern; however, it is also a clean way to mark a class, especially when that interface might be evolving.</span></span> <span data-ttu-id="d0e5f-140">Ein Attribut ist möglicherweise die andere Auswahl für den Marker allerdings handelt es sich schneller die Basisklasse (Entität) neben der IAggregate-Schnittstelle, über die Klasse ein Aggregatattribut-Marker Probieren Sie anstelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-140">An attribute could be the other choice for the marker, but it is quicker to see the base class (Entity) next to the IAggregate interface instead of putting an Aggregate attribute marker above the class.</span></span> <span data-ttu-id="d0e5f-141">Es ist ein Metter Voreinstellungen, in jedem Fall.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-141">It is a metter of preferences, in any case.</span></span>

<span data-ttu-id="d0e5f-142">Müssen Sie ein Verfahren zum Aggregieren Stamm, der Großteil des Codes im Zusammenhang mit der Konsistenz und Geschäftsregeln für das Aggregat Entitäten als Methoden in der Reihenfolge-aggregate Stammklasse (z. B. AddOrderItem beim Hinzufügen eines OrderItem-Objekts, das Aggregat) implementiert werden sollte. .</span><span class="sxs-lookup"><span data-stu-id="d0e5f-142">Having an aggregate root means that most of the code related to consistency and business rules of the aggregate’s entities should be implemented as methods in the Order aggregate root class (for example, AddOrderItem when adding an OrderItem object to the aggregate).</span></span> <span data-ttu-id="d0e5f-143">Sie sollten nicht erstellen oder OrderItems Objekten unabhängig voneinander oder direkt aktualisieren; die Klasse AggregateRoot muss Steuerelement und Konsistenz von jeder Updatevorgang für seine untergeordneten Entitäten beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-143">You should not create or update OrderItems objects independently or directly; the AggregateRoot class must keep control and consistency of any update operation against its child entities.</span></span>

<span data-ttu-id="d0e5f-144">Beispielsweise sollten Sie *nicht* gehen beliebiger Befehl Handler-Methode oder einer Anwendung Ebene Klassen:</span><span class="sxs-lookup"><span data-stu-id="d0e5f-144">For example, you should *not* do the following from any command handler method or application layer class:</span></span>

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

<span data-ttu-id="d0e5f-145">In diesem Fall wird die Add-Methode rein eines Vorgangs zum Hinzufügen von Daten, mit direktem Zugriff auf die Auflistung OrderItems.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-145">In this case, the Add method is purely an operation to add data, with direct access to the OrderItems collection.</span></span> <span data-ttu-id="d0e5f-146">Aus diesem Grund beziehen sich die meisten Domänenlogik, Regeln oder Überprüfungen auf, dass der Vorgang mit den untergeordneten Entitäten auf der Anwendungsebene (Befehlshandler und Web-API-Controller) verteilt.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-146">Therefore, most of the domain logic, rules, or validations related to that operation with the child entities will be spread across the application layer (command handlers and Web API controllers).</span></span>

<span data-ttu-id="d0e5f-147">Wenn Sie um die aggregierten Stamm wechseln, kann nicht der aggregierte Stamm die Invarianten seine Gültigkeit bzw. ihre Konsistenz garantieren.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-147">If you go around the aggregate root, the aggregate root cannot guarantee its invariants, its validity, or its consistency.</span></span> <span data-ttu-id="d0e5f-148">Schließlich müssen Sie Spaghetti oder Transaktionsskripts Code.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-148">Eventually you will have spaghetti code or transactional script code.</span></span>

<span data-ttu-id="d0e5f-149">Um DDD Muster folgen zu können, benötigen Entitäten nicht öffentlichen Setter in jeder Entitätseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-149">To follow DDD patterns, entities must not have public setters in any entity property.</span></span> <span data-ttu-id="d0e5f-150">Änderungen in einer Entität sollte von expliziten Methoden mit expliziten ubiquitäre Sprache über die Änderung gesteuert, die sie in der Entität ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-150">Changes in an entity should be driven by explicit methods with explicit ubiquitous language about the change they are performing in the entity.</span></span>

<span data-ttu-id="d0e5f-151">Darüber hinaus muss Sammlungen innerhalb der Entität (z. B. die Bestellartikel) schreibgeschützte Eigenschaften (die AsReadOnly Methode weiter unten erläutert).</span><span class="sxs-lookup"><span data-stu-id="d0e5f-151">Furthermore, collections within the entity (like the order items) should be read-only properties (the AsReadOnly method explained later).</span></span> <span data-ttu-id="d0e5f-152">Sie sollten nur von innerhalb der aggregierten Stamm-Klasse, Methoden oder die Methoden der untergeordneten Entität aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-152">You should be able to update it only from within the aggregate root class methods or the child entity methods.</span></span>

<span data-ttu-id="d0e5f-153">Wie Sie im Code für den Auftrag aggregieren Stamm sehen können, sollten alle Setter private oder mindestens schreibgeschützt sind und extern sein, damit alle Vorgang für die Entität Daten oder seinen untergeordneten Elementen verfügt über Methoden in die Entitätsklasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-153">As you can see in the code for the Order aggregate root, all setters should be private or at least read-only externally, so that any operation against the entity’s data or its child entities has to be performed through methods in the entity class.</span></span> <span data-ttu-id="d0e5f-154">Damit wird die Konsistenz auf eine gesteuerte und objektorientierte Weise anstelle von Transaktionsskripts Code implementieren.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-154">This maintains consistency in a controlled and object-oriented way instead of implementing transactional script code.</span></span>

<span data-ttu-id="d0e5f-155">Der folgende Codeausschnitt zeigt die richtige Methode zum Hinzufügen eines Objekts OrderItem des Aggregats Reihenfolge von code.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-155">The following code snippet shows the proper way to code the task of adding an OrderItem object to the Order aggregate.</span></span>

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

<span data-ttu-id="d0e5f-156">In diesem Codeausschnitt werden die meisten Überprüfungen oder Logik, die im Zusammenhang mit der Erstellung eines Objekts OrderItem unter der Kontrolle des Stamms aggregieren Reihenfolge werden – in der Methode AddOrderItem – insbesondere Überprüfungen und Logik im Zusammenhang mit anderen Elementen im aggregatfunktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-156">In this snippet, most of the validations or logic related to the creation of an OrderItem object will be under the control of the Order aggregate root—in the AddOrderItem method—especially validations and logic related to other elements in the aggregate.</span></span> <span data-ttu-id="d0e5f-157">Beispielsweise erhalten Sie möglicherweise das gleiche Produkt-Element als das Ergebnis von mehreren Aufrufen an AddOrderItem.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-157">For instance, you might get the same product item as the result of multiple calls to AddOrderItem.</span></span> <span data-ttu-id="d0e5f-158">In dieser Methode konnte Sie untersuchen die Produktelemente und dieselben Produktelemente zu einem einzigen OrderItem-Objekt mit mehreren Einheiten zu konsolidieren.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-158">In that method, you could examine the product items and consolidate the same product items into a single OrderItem object with several units.</span></span> <span data-ttu-id="d0e5f-159">Darüber hinaus würde, wenn es gibt verschiedene Rabatte die Produkt-ID ist jedoch gleich, Sie wahrscheinlich höheren Rabatt gelten.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-159">Additionally, if there are different discount amounts but the product ID is the same, you would likely apply the higher discount.</span></span> <span data-ttu-id="d0e5f-160">Dieses Prinzip gilt für alle anderen Domänenlogik für das Objekt OrderItem.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-160">This principle applies to any other domain logic for the OrderItem object.</span></span>

<span data-ttu-id="d0e5f-161">Darüber hinaus die neue OrderItem(params) Vorgang ebenfalls gesteuert und die von der Methode AddOrderItem vom Stamm aggregieren Reihenfolge ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-161">In addition, the new OrderItem(params) operation will also be controlled and performed by the AddOrderItem method from the Order aggregate root.</span></span> <span data-ttu-id="d0e5f-162">Daher im Zusammenhang Großteil der Logik oder Überprüfungen mit, dass Vorgang (besonders alles, was die Konsistenz zwischen anderen Entitäten untergeordneten wirkt sich auf) in einer einzelnen Stelle innerhalb des Stamms aggregieren kann.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-162">Therefore, most of the logic or validations related to that operation (especially anything that impacts the consistency between other child entities) will be in a single place within the aggregate root.</span></span> <span data-ttu-id="d0e5f-163">Also der ultimate Zweck des Musters aggregieren Stamm.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-163">That is the ultimate purpose of the aggregate root pattern.</span></span>

<span data-ttu-id="d0e5f-164">Bei Verwendung von Entity Framework 1.1 eine Entität DDD kann ausgedrückt werden, da einer der neuen Funktionen von Entity Framework Core 1.1 ist, dass es ermöglicht [zuordnen zu Feldern](https://docs.microsoft.com/ef/core/modeling/backing-field) zusätzlich zu den Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-164">When you use Entity Framework 1.1, a DDD entity can be better expressed because one of the new features of Entity Framework Core 1.1 is that it allows [mapping to fields](https://docs.microsoft.com/ef/core/modeling/backing-field) in addition to properties.</span></span> <span data-ttu-id="d0e5f-165">Dies ist hilfreich, wenn Sie eine Sammlung von untergeordneten Entitäten oder rückgabewertobjekte zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-165">This is useful when protecting collections of child entities or value objects.</span></span> <span data-ttu-id="d0e5f-166">Mit dieser Erweiterung können Sie einfache private Felder anstelle von Eigenschaften, und Sie jede Aktualisierung an die feldauflistung in öffentlichen Methoden implementieren und Bereitstellen von nur-Lese-Zugriff über die AsReadOnly-Methode.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-166">With this enhancement, you can use simple private fields instead of properties and you can implement any update to the field collection in public methods and provide read-only access through the AsReadOnly method.</span></span>

<span data-ttu-id="d0e5f-167">Eigenschaften werden daher in DDD, aktualisieren die Entität nur über Methoden in der Entität (oder der Konstruktor), um alle invariante und die Konsistenz der Daten zu steuern möchten, nur mit einem Get-Accessor definiert.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-167">In DDD you want to update the entity only through methods in the entity (or the constructor) in order to control any invariant and the consistency of the data, so properties are defined only with a get accessor.</span></span> <span data-ttu-id="d0e5f-168">Die Eigenschaften werden durch private Felder unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-168">The properties are backed by private fields.</span></span> <span data-ttu-id="d0e5f-169">Private Member kann nur von innerhalb der Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-169">Private members can only be accessed from within the class.</span></span> <span data-ttu-id="d0e5f-170">Allerdings dort eine Ausnahme: EF Core muss diese Felder ebenfalls festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-170">However, there one exception: EF Core needs to set these fields as well.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a><span data-ttu-id="d0e5f-171">Zuordnen von Eigenschaften nur mit get-Eigenschaftenaccessoren auf die Felder in der Datenbanktabelle</span><span class="sxs-lookup"><span data-stu-id="d0e5f-171">Mapping properties with only get accessors to the fields in the database table</span></span>

<span data-ttu-id="d0e5f-172">Zuordnen von Eigenschaften zu den Spalten der Datenbanktabelle ist kein Domäne Zuständigkeit, sondern Teil der Infrastruktur und Persistenz-Ebene.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-172">Mapping properties to the database table columns is not a domain responsibility, but part of the infrastructure and persistence layer.</span></span> <span data-ttu-id="d0e5f-173">Wir erwähnt diese hier nur, damit die neuen Funktionen in der EF 1.1 im Zusammenhang mit, wie Sie Entitäten modellieren können bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-173">We mention this here just so you are aware of the new capabilities in EF 1.1 related to how you can model entities.</span></span> <span data-ttu-id="d0e5f-174">Weitere Informationen zu diesem Thema werden im Abschnitt-Infrastruktur und Persistenz erläutert.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-174">Additional details on this topic are explained in the infrastructure and persistence section.</span></span>

<span data-ttu-id="d0e5f-175">Bei Verwendung von EF 1.0 müssen innerhalb der DbContext Sie ordnen Sie die Eigenschaften, die nur mit Getter auf die tatsächlichen Felder in der Datenbanktabelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-175">When you use EF 1.0, within the DbContext you need to map the properties that are defined only with getters to the actual fields in the database table.</span></span> <span data-ttu-id="d0e5f-176">Dies erfolgt mit der HasField-Methode der PropertyBuilder-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-176">This is done with the HasField method of the PropertyBuilder class.</span></span>

### <a name="mapping-fields-without-properties"></a><span data-ttu-id="d0e5f-177">Zuordnen von Feldern ohne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0e5f-177">Mapping fields without properties</span></span>

<span data-ttu-id="d0e5f-178">Mit dem neuen Feature in EF Core 1.1 Spalten Felder zuordnen ist es auch möglich, verwenden die Eigenschaften nicht.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-178">With the new feature in EF Core 1.1 to map columns to fields, it is also possible to not use properties.</span></span> <span data-ttu-id="d0e5f-179">Stattdessen können Sie nur Spalten aus einer Tabelle Felder zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-179">Instead, you can just map columns from a table to fields.</span></span> <span data-ttu-id="d0e5f-180">Ein allgemeiner Verwendungsfall dafür wird die private Felder für einen internen Status, der nicht von außerhalb der Entität zugegriffen werden muss.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-180">A common use case for this is private fields for an internal state that does not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="d0e5f-181">Angenommen, in der im vorangehenden Codebeispiel wird die \_SomeOrderInternalState Feld verfügt über keine verknüpften Eigenschaft für eine Setter oder Getter-Methode.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-181">For example, in the preceding code example, the \_someOrderInternalState field has no related property for either a setter or getter.</span></span> <span data-ttu-id="d0e5f-182">Dieses Feld wird auch innerhalb der Reihenfolge von Geschäftslogik berechnet und aus der Order-Methoden verwendet werden, es muss jedoch in der Datenbank ebenfalls beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-182">That field will also be calculated within the order’s business logic and used from the order’s methods, but it needs to be persisted in the database as well.</span></span> <span data-ttu-id="d0e5f-183">In der EF 1.1 ist daher eine Möglichkeit, ein Feld ohne eine zugehörige Eigenschaft einer Spalte in der Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-183">So, in EF 1.1 there is a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="d0e5f-184">Dies wird auch erläutert, der [Infrastrukturebene](#the-infrastructure-layer) Abschnitt dieses Handbuchs.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-184">This is also explained in the [Infrastructure layer](#the-infrastructure-layer) section of this guide.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d0e5f-185">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d0e5f-185">Additional resources</span></span>

-   <span data-ttu-id="d0e5f-186">**Vaughn Vernon. Modellieren von Aggregate mit DDD und Entity Framework.**</span><span class="sxs-lookup"><span data-stu-id="d0e5f-186">**Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework.**</span></span> <span data-ttu-id="d0e5f-187">Beachten Sie, dass dies *nicht* Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="d0e5f-187">Note that this is *not* Entity Framework Core.</span></span>
    [<span data-ttu-id="d0e5f-188">*https://vaughnvernon.Co/?p=879*</span><span class="sxs-lookup"><span data-stu-id="d0e5f-188">*https://vaughnvernon.co/?p=879*</span></span>](https://vaughnvernon.co/?p=879)

-   <span data-ttu-id="d0e5f-189">**Julie Lerman. Codierung für Domain Driven Design: Tipps für Entwickler Daten Developers**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span><span class="sxs-lookup"><span data-stu-id="d0e5f-189">**Julie Lerman. Coding for Domain-Driven Design: Tips for Data-Focused Devs**
[*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span></span>

-   <span data-ttu-id="d0e5f-190">**Udi Dahan. Vorgehensweise: Erstellen Sie vollständig gekapselt Domänenmodelle**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="d0e5f-190">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d0e5f-191">[Vorherigen] (Microservice-Domain-model.md) [weiter] (Seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="d0e5f-191">[Previous] (microservice-domain-model.md) [Next] (seedwork-domain-model-base-classes-interfaces.md)</span></span>
