---
title: Verwenden keine NoSQL-Datenbanken als Persistenz Infrastruktur
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Verwenden keine NoSQL-Datenbanken als Persistenz Infrastruktur"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e4b63511069b89cc5761ce7ed64f09e9035a56a3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="c7e18-104">Verwenden keine NoSQL-Datenbanken als Persistenz Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="c7e18-104">Using NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="c7e18-105">Wenn Sie keine NoSQL-Datenbanken für Ihre Infrastruktur Datenebene verwenden, verwenden Sie ein ORM wie Entity Framework Core in der Regel nicht.</span><span class="sxs-lookup"><span data-stu-id="c7e18-105">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="c7e18-106">Stattdessen verwenden Sie die API, die vom NoSQL-Modul, wie z. B. Azure-Cosmos-DB, MongoDB, Cassandra, RavenDB, CouchDB oder Azure-Speichertabellen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c7e18-106">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="c7e18-107">Bei Verwendung eine NoSQL-Datenbank, insbesondere eine dokumentorientiert Datenbank wie Azure-Cosmos-DB, CouchDB oder RavenDB, ist jedoch die Möglichkeit, die Sie das Modell mit DDD Aggregaten entwerfen teilweise ähnelt in EF-Core in Bezug auf die Kennung des Vorgehensweise können Aggregieren Stämme, untergeordneten Entitätsklassen und Wertklassen-Objekt.</span><span class="sxs-lookup"><span data-stu-id="c7e18-107">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="c7e18-108">Aber letztendlich, wirkt sich die Datenbankauswahl im Entwurf.</span><span class="sxs-lookup"><span data-stu-id="c7e18-108">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="c7e18-109">Wenn Sie eine Datenbank dokumentorientiert verwenden, implementieren Sie ein Aggregat als ein einzelnes Dokument, das in JSON oder ein anderes Format serialisiert.</span><span class="sxs-lookup"><span data-stu-id="c7e18-109">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="c7e18-110">Allerdings ist die Verwendung der Datenbank aus einer Domäne Modell Codeansicht transparent.</span><span class="sxs-lookup"><span data-stu-id="c7e18-110">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="c7e18-111">Wenn Sie eine NoSQL-Datenbank verwenden zu können, Sie weiterhin sind Entitätsklassen und aggregieren Stammklassen, aber mit mehr Flexibilität als bei Verwendung EF Core, da die Persistenz ist nicht relationale.</span><span class="sxs-lookup"><span data-stu-id="c7e18-111">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="c7e18-112">Der Unterschied besteht darin, wie Sie dieses Modell beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c7e18-112">The difference is in how you persist that model.</span></span> <span data-ttu-id="c7e18-113">Wenn Sie Ihre Domänenmodell auf Grundlage von Klassen für POCO-Entitäten implementiert, kann unabhängig von der Infrastruktur Persistenz er anscheinend zu einer anderen Persistenz-Infrastruktur auch aus relationalen Datenquellen zu NoSQL verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="c7e18-113">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="c7e18-114">Allerdings sollten, die nicht Ziel sein.</span><span class="sxs-lookup"><span data-stu-id="c7e18-114">However, that should not be your goal.</span></span> <span data-ttu-id="c7e18-115">Es gibt immer Einschränkungen in den verschiedenen Datenbanken werden mithilfe von Push übertragen Sie zurück, sodass Sie nicht das gleiche Modell für haben können relationale oder NoSQL-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="c7e18-115">There are always constraints in the different databases will push you back, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="c7e18-116">Ändern die Persistenz Modelle würde nicht trivial, werden, weil Transaktionen und persistenzvorgänge sehr unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="c7e18-116">Changing persistence models would not be trivial, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="c7e18-117">In einer Datenbank dokumentorientiert ist es beispielsweise angemessen für einen aggregierten Stamm, mehrere untergeordnete Sammlungseigenschaften zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7e18-117">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="c7e18-118">In einer relationalen Datenbank wird Abfragen von mehreren untergeordneten Sammlungseigenschaften unsinnig, ist, da Sie eine Vereinigung aller SQL-Anweisung aus EF abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c7e18-118">In a relational database, querying multiple child collection properties is awful, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="c7e18-119">Mit der gleichen Domänenmodell für relationale Datenbanken oder NoSQL-Datenbanken ist nicht einfach, und Sie sollten nicht versuchen.</span><span class="sxs-lookup"><span data-stu-id="c7e18-119">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try it.</span></span> <span data-ttu-id="c7e18-120">Sie haben sich tatsächlich so entwerfen Sie Ihr Modell mit einem Überblick darüber, wie die Daten in jeder bestimmte Datenbank verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7e18-120">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="c7e18-121">Ein Vorteil bei Verwendung von NoSQL-Datenbanken ist, dass die Entitäten mehr denormalisierten, Sie sollte daher nicht die Zuordnung zu einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c7e18-121">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="c7e18-122">Ihre Domänenmodell kann flexibler als bei Verwendung einer relationalen Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="c7e18-122">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="c7e18-123">Wenn Sie entwerfen Ihre Domänenmodell basierend auf den Aggregate, um NoSQL verschieben und dokumentorientiert Datenbanken möglicherweise noch einfacher als die Verwendung einer relationalen Datenbank, die Aggregate, die Sie entwerfen ähneln serialisiert Dokumente in einer Datenbank dokumentorientiert.</span><span class="sxs-lookup"><span data-stu-id="c7e18-123">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="c7e18-124">Dann können Sie in diesen "Sammlungen" alle Informationen einschließen, die Sie für das Aggregat eventuell.</span><span class="sxs-lookup"><span data-stu-id="c7e18-124">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="c7e18-125">Der folgende JSON-Code wird z. B. eine beispielimplementierung eines Aggregats Reihenfolge aus, bei Verwendung einer Datenbank dokumentorientiert.</span><span class="sxs-lookup"><span data-stu-id="c7e18-125">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="c7e18-126">Es ähnelt der aggregierten Reihenfolge, die wir im eShopOnContainers Beispiel, jedoch ohne Verwendung von EF Core unterhalb implementiert.</span><span class="sxs-lookup"><span data-stu-id="c7e18-126">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

```json
{
    "id": "2017001",
    "orderDate": "2/25/2017",
    "buyerId": "1234567",
    "address": [
        {
        "street": "100 One Microsoft Way",
        "city": "Redmond",
        "state": "WA",
        "zip": "98052",
        "country": "U.S."
        }
    ],
    "orderItems": [
        {"id": 20170011, "productId": "123456", "productName": ".NET T-Shirt",
        "unitPrice": 25, "units": 2, "discount": 0},
        {"id": 20170012, "productId": "123457", "productName": ".NET Mug",
        "unitPrice": 15, "units": 1, "discount": 0}
    ]
}
```

<span data-ttu-id="c7e18-127">Bei Verwendung von C\# Modell, das Aggregat von etwa wie das Azure Cosmos-DB-SDK, das Aggregat zu verwendende Implementierung ähnelt C\# POCO-Klassen, die mit EF Core verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7e18-127">When you use a C\# model to implement the aggregate to be used by something like the Azure Cosmos DB SDK, the aggregate is similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="c7e18-128">Der Unterschied besteht darin, die Möglichkeit, ihren Einsatz aus dem die Anwendung und Infrastruktur Ebenen, wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="c7e18-128">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH DOCUMENTDB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).
// This can be saved as JSON as is without converting into rows/columns.
Order orderAggregate = new Order
{
    Id = "2017001",
    OrderDate = new DateTime(2005, 7, 1),
    BuyerId = "1234567",
    PurchaseOrderNumber = "PO18009186470"
}

Address address = new Address
{
    Street = "100 One Microsoft Way",
    City = "Redmond",
    State = "WA",
    Zip = "98052",
    Country = "U.S."
}

orderAggregate.UpdateAddress(address);
OrderItem orderItem1 = new OrderItem
{
    Id = 20170011,
    ProductId = "123456",
    ProductName = ".NET T-Shirt",
    UnitPrice = 25,
    Units = 2,
    Discount = 0;
};

OrderItem orderItem2 = new OrderItem
{
    Id = 20170012,
    ProductId = "123457",
    ProductName = ".NET Mug",
    UnitPrice = 15,
    Units = 1,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);

// *** End of Domain Model Code ***
//...
// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, order);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

<span data-ttu-id="c7e18-129">Sie können sehen, dass die Möglichkeit, die Arbeit mit Ihrem Domänenmodell ähnlich wie bei Sie es in Ihrer Domäne der Ebene verwenden sein können, wenn die Infrastruktur EF ist.</span><span class="sxs-lookup"><span data-stu-id="c7e18-129">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="c7e18-130">Sie verwenden weiterhin die gleichen aggregieren Stamm-Methoden, um Konsistenz Invarianten und Überprüfungen in das Aggregat sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="c7e18-130">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="c7e18-131">Jedoch beibehalten, wenn Sie das Modell in der NoSQL-Datenbank, den Code und API ändern sich im Vergleich zu EF Kerncode oder anderen Code, die im Zusammenhang mit relationalen Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="c7e18-131">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="c7e18-132">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c7e18-132">Additional resources</span></span>

-   <span data-ttu-id="c7e18-133">**Modellieren von Daten in DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span><span class="sxs-lookup"><span data-stu-id="c7e18-133">**Modeling data in DocumentDB**
[*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span></span>

-   <span data-ttu-id="c7e18-134">**Vaughn Vernon. Die ideale Domain Driven Design Aggregat Store? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span><span class="sxs-lookup"><span data-stu-id="c7e18-134">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**
[*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span></span>

-   <span data-ttu-id="c7e18-135">**Ein Persistenz agnostisch Ereignisspeicher für .NET.**</span><span class="sxs-lookup"><span data-stu-id="c7e18-135">**A persistence agnostic Event Store for .NET.**</span></span> <span data-ttu-id="c7e18-136">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="c7e18-136">GitHub repo.</span></span>
    [<span data-ttu-id="c7e18-137">*https://github.com/NEventStore/NEventStore*</span><span class="sxs-lookup"><span data-stu-id="c7e18-137">*https://github.com/NEventStore/NEventStore*</span></span>](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
<span data-ttu-id="c7e18-138">[Vorherigen] (Infrastructure-persistence-layer-implemenation-entity-framework-core.md) [weiter] (Microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="c7e18-138">[Previous] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Next] (microservice-application-layer-web-api-design.md)</span></span>
