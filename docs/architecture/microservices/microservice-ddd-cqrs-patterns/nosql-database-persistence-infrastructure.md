---
title: Verwenden von NoSQL-Datenbanken als Persistenzinfrastruktur
description: Übersicht über die Verwendung von NoSql-Datenbanken im Allgemeinen und Azure Cosmos DB im Speziellen als Option zum Implementieren von Persistenz.
ms.date: 01/30/2020
ms.openlocfilehash: 7da4141d9aadc4aaa265ac97d328bc4b7569a0cb
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502397"
---
# <a name="use-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="8b7ed-103">Verwenden von NoSQL-Datenbanken als Persistenzinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="8b7ed-103">Use NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="8b7ed-104">Wenn Sie NoSQL-Datenbanken für die Datenschicht Ihrer Infrastruktur verwenden, verwenden Sie in der Regel keine ORM wie Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-104">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="8b7ed-105">Stattdessen verwenden Sie die API, die von der NoSQL-Engine, wie z.B. Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB oder Azure Table Storage, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-105">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="8b7ed-106">Wenn Sie jedoch eine NoSQL-Datenbank verwenden, insbesondere eine dokumentorientierte Datenbank wie Azure Cosmos DB, CouchDC oder RavenDB, ist die Art und Weise, in der Sie Ihr Modell mit DDD-Aggregaten entwerfen, teilweise mit der Vorgehensweise in EF Core vergleichbar, z.B. in Bezug auf die Identifikation von Aggregatstämmen, untergeordneten Entitätsklassen und Wertobjektklassen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-106">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="8b7ed-107">Letztendlich hat die Datenbankauswahl jedoch Auswirkungen auf Ihren Entwurf.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-107">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="8b7ed-108">Wenn Sie eine dokumentorientierte Datenbank verwenden, implementieren Sie ein Aggregat als einzelnes Dokument, das im JSON-Format oder einem anderen Format serialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-108">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="8b7ed-109">Allerdings ist die Verwendung der Datenbank aus Sicht eines Codeelements des Domänenmodells transparent.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-109">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="8b7ed-110">Durch eine NoSQL-Datenbank verwenden Sie weiterhin Entitätsklassen und Aggregatstammklassen, jedoch mit mehr Flexibilität als bei der Verwendung von EF Core, da die Persistenz nicht relational ist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-110">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="8b7ed-111">Der Unterschied besteht darin, wie Sie dieses Modell speichern.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-111">The difference is in how you persist that model.</span></span> <span data-ttu-id="8b7ed-112">Wenn Sie Ihr Domänenmodell (unabhängig von der Persistenz der Infrastruktur) basierend auf POCO-Entitätsklassen implementiert haben, wirkt es möglicherweise so, als könnten Sie zu einer anderen Persistenz der Infrastruktur wechseln, sogar von einer relationalen zur NoSQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-112">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="8b7ed-113">Das sollte jedoch nicht Ihr Ziel sein.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-113">However, that should not be your goal.</span></span> <span data-ttu-id="8b7ed-114">In den verschiedenen Datenbanktechnologien gibt es immer Einschränkungen und Abwägungen, sodass Sie für relationale oder NoSQL-Datenbanken nicht dasselbe Modell verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-114">There are always constraints and trade-offs in the different database technologies, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="8b7ed-115">Das Ändern von Persistenzmodellen ist nicht leicht, da Transaktionen und Persistenzvorgänge sehr unterschiedlich sein werden.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-115">Changing persistence models is not a trivial task, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="8b7ed-116">So ist es in einer dokumentorientierten Datenbank beispielsweise in Ordnung, wenn ein Aggregatstamm über mehrere untergeordnete Sammlungseigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-116">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="8b7ed-117">In einer relationalen Datenbank lässt sich das Abfragen mehrerer untergeordneter Sammlungseigenschaften nicht einfach optimieren, da EF die SQL-Anweisung UNION ALL zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-117">In a relational database, querying multiple child collection properties is not easily optimized, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="8b7ed-118">Über dasselbe Domänenmodell für relationale Datenbanken oder NoSQL-Datenbanken zu verfügen, ist nicht einfach. Es wird davon abgeraten, es zu probieren.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-118">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try to do it.</span></span> <span data-ttu-id="8b7ed-119">Sie müssen Ihr eigenes Modell entwerfen und dabei verstehen, wie die Daten in den einzelnen Datenbanken verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-119">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="8b7ed-120">Ein Vorteil bei der Verwendung von NoSQL-Datenbanken besteht darin, dass die Entitäten denormalisierter sind und Sie daher keine Tabellenzuordnung festlegen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-120">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="8b7ed-121">Ihr Domänenmodell kann flexibler als bei der Verwendung einer relationalen Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-121">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="8b7ed-122">Wenn Sie Ihr Domänenmodell basierend auf Aggregaten entwerfen, ist der Wechsel zu NoSQL- und dokumentorientierten Datenbanken möglicherweise einfacher als die Verwendung einer relationalen Datenbank, da die von Ihnen entworfenen Aggregate mit serialisierten Dokumenten in einer dokumentorientierten Datenbank vergleichbar sind.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-122">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="8b7ed-123">In diesen Sammlungen können Sie anschließend alle Informationen einschließen, die Sie für dieses Aggregat gebrauchen könnten.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-123">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="8b7ed-124">Bei dem folgenden JSON-Code handelt es sich beispielsweise um die Beispielimplementierung des Aggregats „Order“ bei der Verwendung einer dokumentorientierten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-124">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="8b7ed-125">Er ist mit dem Aggregat „Order“ vergleichbar, das im „eShopOnContainers“-Beispiel implementiert wurde, jedoch ohne die untergeordnete Verwendung von EF Core.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-125">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

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

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a><span data-ttu-id="8b7ed-126">Einführung in Azure Cosmos DB und die native Cosmos DB-API</span><span class="sxs-lookup"><span data-stu-id="8b7ed-126">Introduction to Azure Cosmos DB and the native Cosmos DB API</span></span>

<span data-ttu-id="8b7ed-127">[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) ist der globale verteilte Datenbankdienst von Microsoft für unternehmenskritische Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-127">[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) is Microsoft's globally distributed database service for mission-critical applications.</span></span> <span data-ttu-id="8b7ed-128">Azure Cosmos DB stellt eine [sofort einsatzfähige globale Verteilung](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), weltweit eine [elastische Skalierung von Durchsatz und Speicher](https://docs.microsoft.com/azure/cosmos-db/partition-data), Latenzen im einstelligen Millisekundenbereich im 99. Perzentil, [fünf richtig definierte Konsistenzebenen](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) und garantierte Hochverfügbarkeit bereit. Dies alles wird durch [branchenführende SLAs](https://azure.microsoft.com/support/legal/sla/cosmos-db/) gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-128">Azure Cosmos DB provides [turn-key global distribution](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), [elastic scaling of throughput and storage](https://docs.microsoft.com/azure/cosmos-db/partition-data) worldwide, single-digit millisecond latencies at the 99th percentile, [five well-defined consistency levels](https://docs.microsoft.com/azure/cosmos-db/consistency-levels), and guaranteed high availability, all backed by [industry-leading SLAs](https://azure.microsoft.com/support/legal/sla/cosmos-db/).</span></span> <span data-ttu-id="8b7ed-129">Azure Cosmos DB [indiziert automatisch Daten](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf), ohne dass Sie sich mit der Schema- und Indexverwaltung auseinandersetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-129">Azure Cosmos DB [automatically indexes data](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) without requiring you to deal with schema and index management.</span></span> <span data-ttu-id="8b7ed-130">Die Datenbank umfasst mehrere Modelle und unterstützt Dokument-, Schlüsselwert-, Graph- sowie einspaltige Datenmodelle.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-130">It is multi-model and supports document, key-value, graph, and columnar data models.</span></span>

![Diagramm, das die globale Verteilung von Azure Cosmos DB zeigt.](./media/nosql-database-persistence-infrastructure/azure-cosmos-db-global-distribution.png)

<span data-ttu-id="8b7ed-132">**Abbildung 7-19**.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-132">**Figure 7-19**.</span></span> <span data-ttu-id="8b7ed-133">Globale Verteilung von Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8b7ed-133">Azure Cosmos DB global distribution</span></span>

<span data-ttu-id="8b7ed-134">Bei der Verwendung eines C\#-Modells zur Implementierung des Aggregats, das von der Azure Cosmos DB-API verwendet werden soll, kann das Aggregat mit den in EF Core verwendeten C\#-POCO-Klassen vergleichbar sein.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-134">When you use a C\# model to implement the aggregate to be used by the Azure Cosmos DB API, the aggregate can be similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="8b7ed-135">Der Unterschied besteht darin, wie diese auf der Anwendungs- und der Infrastrukturebene verwendet werden. Dies wird im folgenden Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="8b7ed-135">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH AZURE COSMOS DB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).

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

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
// *** End of Domain Model Code ***

// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, orderAggregate);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

<span data-ttu-id="8b7ed-136">Sie können sehen, dass die Art und Weise, in der Sie mit Ihrem Domänenmodell arbeiten, mit der Verwendungsweise auf der Ebene Ihres Domänenmodells vergleichbar ist, wenn EF die Infrastruktur ist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-136">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="8b7ed-137">Sie verwenden weiterhin die gleichen Aggregatstammmethoden, um Konsistenz, Invarianten und Validierungen innerhalb des Aggregats sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-137">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="8b7ed-138">Wenn Sie Ihr Modell jedoch dauerhaft in der NoSQL-Datenbank speichern, führt dies zu einer wesentlichen Änderung des Codes und der API im Vergleich zu EF Core-Code oder einem beliebigen anderen Code für relationale Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-138">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

## <a name="implement-net-code-targeting-mongodb-and-azure-cosmos-db"></a><span data-ttu-id="8b7ed-139">Implementieren von .NET-Code für MongoDB und Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8b7ed-139">Implement .NET code targeting MongoDB and Azure Cosmos DB</span></span>

### <a name="use-azure-cosmos-db-from-net-containers"></a><span data-ttu-id="8b7ed-140">Verwenden von Azure Cosmos DB über .NET-Container</span><span class="sxs-lookup"><span data-stu-id="8b7ed-140">Use Azure Cosmos DB from .NET containers</span></span>

<span data-ttu-id="8b7ed-141">Sie können über .NET-Code, der in Containern ausgeführt wird, auf Azure Cosmos DB-Datenbanken genau wie über eine beliebige andere .NET-Anwendung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-141">You can access Azure Cosmos DB databases from .NET code running in containers, like from any other .NET application.</span></span> <span data-ttu-id="8b7ed-142">Die Microservices „Locations.API“ und „Marketing.API“ in eShopOnContainers werden beispielsweise implementiert, damit sie Azure Cosmos DB-Datenbanken verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-142">For instance, the Locations.API and Marketing.API microservices in eShopOnContainers are implemented so they can consume Azure Cosmos DB databases.</span></span>

<span data-ttu-id="8b7ed-143">Aus der Sicht einer Docker-Entwicklungsumgebung gibt es in Azure Cosmos DB jedoch eine Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-143">However, there’s a limitation in Azure Cosmos DB from a Docker development environment point of view.</span></span> <span data-ttu-id="8b7ed-144">Es gibt zwar einen lokalen [Azure Cosmos DB-Emulator](https://docs.microsoft.com/azure/cosmos-db/local-emulator), der auf einem lokalen Entwicklungsrechner ausgeführt werden kann, aber nur Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-144">Even though there’s an on-premises [Azure Cosmos DB Emulator](https://docs.microsoft.com/azure/cosmos-db/local-emulator) that can run in a local development machine, it only supports Windows.</span></span> <span data-ttu-id="8b7ed-145">Linux und macOS werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-145">Linux and macOS aren't supported.</span></span>

<span data-ttu-id="8b7ed-146">Dieser Emulator kann auch in Docker ausgeführt werden, allerdings nur in Windows- und nicht in Linux-Containern.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-146">There's also the possibility to run this emulator on Docker, but just on Windows Containers, not with Linux Containers.</span></span> <span data-ttu-id="8b7ed-147">Dies ist ein anfängliches Handicap für die Entwicklungsumgebung, wenn Ihre Anwendung in Linux-Containern bereitgestellt wird, da eine gleichzeitige Bereitstellung von Linux- und Windows-Containern in Docker für Windows derzeit nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-147">That's an initial handicap for the development environment if your application is deployed as Linux containers, since, currently, you can't deploy Linux and Windows Containers on Docker for Windows at the same time.</span></span> <span data-ttu-id="8b7ed-148">Alle bereitgestellten Container müssen entweder für Linux oder für Windows bestimmt sein.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-148">Either all containers being deployed have to be for Linux or for Windows.</span></span>

<span data-ttu-id="8b7ed-149">Der ideale und einfachere Weg zur Bereitstellung für eine Entwicklungs-/Testlösung besteht darin, Ihre Datenbanksysteme zusammen mit Ihren benutzerdefinierten Containern als Container bereitzustellen, damit Ihre Entwicklungs-/Testumgebungen immer konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-149">The ideal and more straightforward deployment for a dev/test solution is to be able to deploy your database systems as containers along with your custom containers so your dev/test environments are always consistent.</span></span>

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a><span data-ttu-id="8b7ed-150">Verwenden der MongoDB-API für lokale Entwicklungs-/Testcontainer unter Linux/Windows plus Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8b7ed-150">Use MongoDB API for local dev/test Linux/Windows containers plus Azure Cosmos DB</span></span>

<span data-ttu-id="8b7ed-151">Cosmos DB-Datenbanken unterstützen die MongoDB-API für .NET sowie das native MongoDB Wire Protocol.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-151">Cosmos DB databases support MongoDB API for .NET as well as the native MongoDB wire protocol.</span></span> <span data-ttu-id="8b7ed-152">Das bedeutet, dass Ihre für MongoDB geschriebene Anwendung unter Verwendung vorhandener Treiber nun mit Cosmos DB kommunizieren und Cosmos DB-Datenbanken anstelle von MongoDB-Datenbanken verwenden kann (s. Abbildung 7-20).</span><span class="sxs-lookup"><span data-stu-id="8b7ed-152">This means that by using existing drivers, your application written for MongoDB can now communicate with Cosmos DB and use Cosmos DB databases instead of MongoDB databases, as shown in Figure 7-20.</span></span>

![Diagramm, das zeigt, dass Cosmos DB das .NET- und MongoDB-Wire Protocol unterstützt.](./media/nosql-database-persistence-infrastructure/mongodb-api-wire-protocol.png)

<span data-ttu-id="8b7ed-154">**Abbildung 7-20**.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-154">**Figure 7-20**.</span></span> <span data-ttu-id="8b7ed-155">Verwenden der API und des Protokolls von MongoDB für den Zugriff auf Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8b7ed-155">Using MongoDB API and protocol to access Azure Cosmos DB</span></span>

<span data-ttu-id="8b7ed-156">Dies ist ein sehr praktischer Ansatz für Proof of Concepts in Docker-Umgebungen mit Linux-Containern, da es sich bei dem [MongoDB-Docker-Image](https://hub.docker.com/r/_/mongo/) um ein Image für mehrere Architekturen handelt, das Linux- und Windows-basierte Docker-Container unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-156">This is a very convenient approach for proof of concepts in Docker environments with Linux containers because the [MongoDB Docker image](https://hub.docker.com/r/_/mongo/) is a multi-arch image that supports Docker Linux containers and Docker Windows containers.</span></span>

<span data-ttu-id="8b7ed-157">Wie die folgende Abbildung zeigt, unterstützt eShopOnContainers unter Verwendung der MongoDB-API MongoDB-Container unter Linux und Windows in der lokalen Entwicklungsumgebung. Anschließend können Sie zu einer skalierbaren PaaS-Cloudlösung wie Azure Cosmos DB wechseln, indem Sie einfach die [MongoDB-Verbindungszeichenfolge so ändern, dass sie auf Azure Cosmos DB verweist](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).</span><span class="sxs-lookup"><span data-stu-id="8b7ed-157">As shown in the following image, by using the MongoDB API, eShopOnContainers supports MongoDB Linux and Windows containers for the local development environment but then, you can move to a scalable, PaaS cloud solution as Azure Cosmos DB by simply [changing the MongoDB connection string to point to Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).</span></span>

![Diagramm, das zeigt, dass der Location-Microservice in eShopOnContainers entweder Cosmos DB oder Mongo DB verwenden kann.](./media/nosql-database-persistence-infrastructure/eshoponcontainers-mongodb-containers.png)

<span data-ttu-id="8b7ed-159">**Abbildung 7-21**.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-159">**Figure 7-21**.</span></span> <span data-ttu-id="8b7ed-160">eShopOnContainers mit MongoDB-Containern für die Entwicklungsumgebung oder Azure Cosmos DB für die Produktion</span><span class="sxs-lookup"><span data-stu-id="8b7ed-160">eShopOnContainers using MongoDB containers for dev-env or Azure Cosmos DB for production</span></span>

<span data-ttu-id="8b7ed-161">Azure Cosmos DB für die Produktion würde in der Azure-Cloud als PaaS und als skalierbarer Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-161">The production Azure Cosmos DB would be running in Azure’s cloud as a PaaS and scalable service.</span></span>

<span data-ttu-id="8b7ed-162">Ihre benutzerdefinierten .NET Core-Container können auf einem lokalen Docker-Entwicklungshost ausgeführt werden (das heißt, Docker für Windows wird auf einem Computer mit Windows 10 verwendet) oder in einer Produktionsumgebung wie Kubernetes in Azure AKS oder Azure Service Fabric bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-162">Your custom .NET Core containers can run on a local development Docker host (that is using Docker for Windows in a Windows 10 machine) or be deployed into a production environment, like Kubernetes in Azure AKS or Azure Service Fabric.</span></span> <span data-ttu-id="8b7ed-163">In dieser zweiten Umgebung würden Sie nur die benutzerdefinierten .NET Core-Container, jedoch nicht die MongoDB-Container bereitstellen, da Sie Azure Cosmos DB in der Cloud für die Verwaltung der Daten in der Produktion verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-163">In this second environment, you would deploy only the .NET Core custom containers but not the MongoDB container since you’d be using Azure Cosmos DB in the cloud for handling the data in production.</span></span>

<span data-ttu-id="8b7ed-164">Ein klarer Vorteil bei der Verwendung der MongoDB-API besteht darin, dass Ihre Lösung in beiden Datenbank-Engines (MongoDB oder Azure Cosmos DB) ausgeführt werden könnte, sodass Migrationen in verschiedenen Umgebungen problemlos durchgeführt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-164">A clear benefit of using the MongoDB API is that your solution could run in both database engines, MongoDB or Azure Cosmos DB, so migrations to different environments should be easy.</span></span> <span data-ttu-id="8b7ed-165">Manchmal ist es jedoch sinnvoll, eine native API (in diesem Fall die native Cosmos DB-API) zu verwenden, um die Funktionen einer bestimmten Datenbank-Engine optimal nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-165">However, sometimes it is worthwhile to use a native API (that is the native Cosmos DB API) in order to take full advantage of the capabilities of a specific database engine.</span></span>

<span data-ttu-id="8b7ed-166">Informationen zum weiteren Vergleich zwischen der einfachen Verwendung von MongoDB im Vergleich zu Cosmos DB in der Cloud finden Sie auf dieser Seite unter [Benefits of using Azure Cosmos DB in this page (Vorteile der Verwendung von Azure Cosmos DB)](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction).</span><span class="sxs-lookup"><span data-stu-id="8b7ed-166">For further comparison between simply using MongoDB versus Cosmos DB in the cloud, see the [Benefits of using Azure Cosmos DB in this page](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction).</span></span>

### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a><span data-ttu-id="8b7ed-167">Analysieren Ihres Ansatzes für Produktionsanwendungen: Vergleich zwischen der MongoDB-API und der Cosmos DB-API</span><span class="sxs-lookup"><span data-stu-id="8b7ed-167">Analyze your approach for production applications: MongoDB API vs. Cosmos DB API</span></span>

<span data-ttu-id="8b7ed-168">In eShopOnContainers wird die MongoDB-API verwendet, da die Priorität im Wesentlichen darauf liegt, über eine konsistente Entwicklungs-/Testumgebung zu verfügen, in der eine NoSQL-Datenbank verwendet wird, die auch in Azure Cosmos DB eingesetzt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-168">In eShopOnContainers, we’re using MongoDB API because our priority was fundamentally to have a consistent dev/test environment using a NoSQL database that could also work with Azure Cosmos DB.</span></span>

<span data-ttu-id="8b7ed-169">Wenn Sie die Verwendung der MongoDB-API für den Zugriff auf Azure Cosmos DB in Azure für Produktionsanwendungen planen, sollten Sie jedoch die Unterschiede in den Funktionen und der Leistung bei der Verwendung der MongoDB-API für den Zugriff auf Azure Cosmos DB-Datenbanken verglichen mit der Verwendung der nativen Azure Cosmos DB-API analysieren.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-169">However, if you planning to use MongoDB API to access Azure Cosmos DB in Azure for production applications, you should analyze the differences in capabilities and performance when using MongoDB API to access Azure Cosmos DB databases compared to using the native Azure Cosmos DB API.</span></span> <span data-ttu-id="8b7ed-170">Wenn die Funktionen und die Leistung vergleichbar sind, können Sie die MongoDB-API verwenden und davon profitieren, dass zwei NoSQL-Datenbank-Engines gleichzeitig unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-170">If it is similar you can use MongoDB API and you get the benefit of supporting two NoSQL database engines at the same time.</span></span>

<span data-ttu-id="8b7ed-171">Alternativ könnten Sie auch MongoDB-Cluster mit dem [MongoDB-Azure-Dienst](https://www.mongodb.com/scale/mongodb-azure-service) als Produktionsdatenbank in der Azure-Cloud verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-171">You could also use MongoDB clusters as the production database in Azure’s cloud, too, with [MongoDB Azure Service](https://www.mongodb.com/scale/mongodb-azure-service).</span></span> <span data-ttu-id="8b7ed-172">Dies ist jedoch kein von Microsoft bereitgestellter PaaS-Dienst.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-172">But that is not a PaaS service provided by Microsoft.</span></span> <span data-ttu-id="8b7ed-173">In diesem Fall hostet Azure lediglich diese Lösung aus MongoDB.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-173">In this case, Azure is just hosting that solution coming from MongoDB.</span></span>

<span data-ttu-id="8b7ed-174">Im Wesentlichen ist dies nur ein Haftungsausschluss, in dem darauf hingewiesen wird, dass Sie die Verwendung der MongoDB-API nicht immer der Verwendung von Azure Cosmos DB vorziehen sollten. In eShopOnContainers wurde dies durchgeführt, weil es sich dabei um eine praktische Wahl für Linux-Container handelt.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-174">Basically, this is just a disclaimer stating that you shouldn’t always use MongoDB API against Azure Cosmos DB, as we did in eShopOnContainers because it was a convenient choice for Linux containers.</span></span> <span data-ttu-id="8b7ed-175">Grundlage der Entscheidung sollten die spezifischen Anforderungen und Tests sein, die Sie für Ihre Produktionsanwendung durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-175">The decision should be based on the specific needs and tests you need to do for your production application.</span></span>

### <a name="the-code-use-mongodb-api-in-net-core-applications"></a><span data-ttu-id="8b7ed-176">Der Code: Verwenden der MongoDB-API in .NET Core-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8b7ed-176">The code: Use MongoDB API in .NET Core applications</span></span>

<span data-ttu-id="8b7ed-177">Die MongoDB-API für .NET basiert auf NuGet-Paketen, die Sie Ihren Projekten hinzufügen müssen, wie das Locations.API-Projekt in der folgenden Abbildung.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-177">MongoDB API for .NET is based on NuGet packages that you need to add to your projects, like in the Locations.API project shown in the following figure.</span></span>

![Screenshot der Abhängigkeiten in den MongoDB-NuGet-Paketen.](./media/nosql-database-persistence-infrastructure/mongodb-api-nuget-packages.png)

<span data-ttu-id="8b7ed-179">**Abbildung 7-22**.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-179">**Figure 7-22**.</span></span> <span data-ttu-id="8b7ed-180">Verweise auf NuGet-Pakete in der MongoDB-API in einem .NET Core-Projekt</span><span class="sxs-lookup"><span data-stu-id="8b7ed-180">MongoDB API NuGet packages references in a .NET Core project</span></span>

<span data-ttu-id="8b7ed-181">In den folgenden Abschnitten wird der Code untersucht.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-181">Let's investigate the code in the following sections.</span></span>

#### <a name="a-model-used-by-mongodb-api"></a><span data-ttu-id="8b7ed-182">Ein von der MongoDB-API verwendetes Modell</span><span class="sxs-lookup"><span data-stu-id="8b7ed-182">A Model used by MongoDB API</span></span>

<span data-ttu-id="8b7ed-183">Zunächst müssen Sie ein Modell definieren, das die Daten enthält, die aus der Datenbank den Speicherplatz Ihrer Anwendung belegen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-183">First, you need to define a model that will hold the data coming from the database in your application’s memory space.</span></span> <span data-ttu-id="8b7ed-184">Im Folgenden sehen Sie ein Beispiel für das Modell, das in eShopOnContainers für „Locations“ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-184">Here’s an example of the model used for Locations at eShopOnContainers.</span></span>

```csharp
using MongoDB.Bson;
using MongoDB.Bson.Serialization.Attributes;
using MongoDB.Driver.GeoJsonObjectModel;
using System.Collections.Generic;

public class Locations
{
    [BsonId]
    [BsonRepresentation(BsonType.ObjectId)]
    public string Id { get; set; }
    public int LocationId { get; set; }
    public string Code { get; set; }
    [BsonRepresentation(BsonType.ObjectId)]
    public string Parent_Id { get; set; }
    public string Description { get; set; }
    public double Latitude { get; set; }
    public double Longitude { get; set; }
    public GeoJsonPoint<GeoJson2DGeographicCoordinates> Location
                                                             { get; private set; }
    public GeoJsonPolygon<GeoJson2DGeographicCoordinates> Polygon
                                                             { get; private set; }
    public void SetLocation(double lon, double lat) => SetPosition(lon, lat);
    public void SetArea(List<GeoJson2DGeographicCoordinates> coordinatesList)
                                                    => SetPolygon(coordinatesList);

    private void SetPosition(double lon, double lat)
    {
        Latitude = lat;
        Longitude = lon;
        Location = new GeoJsonPoint<GeoJson2DGeographicCoordinates>(
            new GeoJson2DGeographicCoordinates(lon, lat));
    }

    private void SetPolygon(List<GeoJson2DGeographicCoordinates> coordinatesList)
    {
        Polygon = new GeoJsonPolygon<GeoJson2DGeographicCoordinates>(
                  new GeoJsonPolygonCoordinates<GeoJson2DGeographicCoordinates>(
                  new GeoJsonLinearRingCoordinates<GeoJson2DGeographicCoordinates>(
                                                                 coordinatesList)));
    }
}
```

<span data-ttu-id="8b7ed-185">Sie können sehen, dass einige Attribute und Typen aus den NuGet-Paketen von MongoDB stammen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-185">You can see there are a few attributes and types coming from the MongoDB NuGet packages.</span></span>

<span data-ttu-id="8b7ed-186">NoSQL-Datenbanken eignen sich in der Regel sehr gut für die Arbeit mit nicht relationalen hierarchischen Daten.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-186">NoSQL databases are usually very well suited for working with non-relational hierarchical data.</span></span> <span data-ttu-id="8b7ed-187">In diesem Beispiel verwenden wir MongoDB-Typen, die speziell für geografische Standorte erstellt wurden, wie z.B. `GeoJson2DGeographicCoordinates`.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-187">In this example, we are using MongoDB types especially made for geo-locations, like `GeoJson2DGeographicCoordinates`.</span></span>

#### <a name="retrieve-the-database-and-the-collection"></a><span data-ttu-id="8b7ed-188">Abrufen von Datenbank und Sammlung</span><span class="sxs-lookup"><span data-stu-id="8b7ed-188">Retrieve the database and the collection</span></span>

<span data-ttu-id="8b7ed-189">In eShopOnContainers wurde ein benutzerdefinierter Datenbankkontext erstellt, in dem der Code implementiert wurde, um die Datenbank und die MongoCollections abzurufen. Dies wird im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-189">In eShopOnContainers, we have created a custom database context where we implement the code to retrieve the database and the MongoCollections, as in the following code.</span></span>

```csharp
public class LocationsContext
{
    private readonly IMongoDatabase _database = null;

    public LocationsContext(IOptions<LocationSettings> settings)
    {
        var client = new MongoClient(settings.Value.ConnectionString);
        if (client != null)
            _database = client.GetDatabase(settings.Value.Database);
    }

    public IMongoCollection<Locations> Locations
    {
        get
        {
            return _database.GetCollection<Locations>("Locations");
        }
    }
}
```

#### <a name="retrieve-the-data"></a><span data-ttu-id="8b7ed-190">Abrufen der Daten</span><span class="sxs-lookup"><span data-stu-id="8b7ed-190">Retrieve the data</span></span>

<span data-ttu-id="8b7ed-191">In C#-Code, wie z.B. Web-API-Controllern oder der Implementierung benutzerdefinierter Repositorys, können Sie bei der Abfrage über die MongoDB-API Code schreiben, der mit dem folgenden Code vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-191">In C# code, like Web API controllers or custom Repositories implementation, you can write similar code to the following when querying through the MongoDB API.</span></span> <span data-ttu-id="8b7ed-192">Beachten Sie, dass das Objekt `_context` eine Instanz der vorherigen Klasse `LocationsContext` ist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-192">Note that the `_context` object is an instance of the previous `LocationsContext` class.</span></span>

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a><span data-ttu-id="8b7ed-193">Verwenden einer Umgebungsvariable in der Datei „docker-compose.override.yml“ für die MongoDB-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b7ed-193">Use an env-var in the docker-compose.override.yml file for the MongoDB connection string</span></span>

<span data-ttu-id="8b7ed-194">Bei der Erstellung eines MongoClient-Objekts ist ein grundlegender Parameter erforderlich, genau genommen der Parameter `ConnectionString`, der auf die korrekte Datenbank verweist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-194">When creating a MongoClient object, it needs a fundamental parameter which is precisely the `ConnectionString` parameter pointing to the right database.</span></span> <span data-ttu-id="8b7ed-195">Bei eShopOnContainers kann die Verbindungszeichenfolge auf einen lokalen MongoDB-Docker-Container oder auf eine „Produktionsdatenbank“ in Azure Cosmos DB verweisen.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-195">In the case of eShopOnContainers, the connection string can point to a local MongoDB Docker container or to a “production” Azure Cosmos DB database.</span></span>  <span data-ttu-id="8b7ed-196">Diese Verbindungszeichenfolge ergibt sich aus den Umgebungsvariablen, die in den Dateien `docker-compose.override.yml` definiert sind. Diese werden bei der Bereitstellung mit „docker-compose“ oder Visual Studio verwendet, wie im folgenden YML-Code zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-196">That connection string comes from the environment variables defined in the `docker-compose.override.yml` files used when deploying with docker-compose or Visual Studio, as in the following yml code.</span></span>

```yml
# docker-compose.override.yml
version: '3.4'
services:
  # Other services
  locations-api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}

```

<span data-ttu-id="8b7ed-197">Die Umgebungsvariable `ConnectionString` wird wie folgt aufgelöst: Wenn die globale Variable `ESHOP_AZURE_COSMOSDB` in der Datei `.env` mit der Azure Cosmos DB-Verbindungszeichenfolge definiert wird, verwendet sie diese für den Zugriff auf die Azure Cosmos DB-Datenbank in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-197">The `ConnectionString` environment variable is resolved this way: If the `ESHOP_AZURE_COSMOSDB` global variable is defined in the `.env` file with the Azure Cosmos DB connection string, it will use it to access the Azure Cosmos DB database in the cloud.</span></span> <span data-ttu-id="8b7ed-198">Wenn sie nicht definiert ist, nimmt sie den Wert `mongodb://nosqldata` an und verwendet den MongoDB-Entwicklungscontainer.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-198">If it’s not defined, it will take the `mongodb://nosqldata` value and use the development MongoDB container.</span></span>

<span data-ttu-id="8b7ed-199">Im folgenden Code wird dargestellt, wie die `.env`-Datei mit der globalen Umgebungsvariable in der Azure Cosmos DB-Verbindungszeichenfolge in eShopOnContainers implementiert wird:</span><span class="sxs-lookup"><span data-stu-id="8b7ed-199">The following code shows the `.env` file with the Azure Cosmos DB connection string global environment variable, as implemented in eShopOnContainers:</span></span>

```yml
# .env file, in eShopOnContainers root folder
# Other Docker environment variables

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost
ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=<YourDockerHostIP>

#ESHOP_AZURE_COSMOSDB=<YourAzureCosmosDBConnData>

#Other environment variables for additional Azure infrastructure assets
#ESHOP_AZURE_REDIS_BASKET_DB=<YourAzureRedisBasketInfo>
#ESHOP_AZURE_STORAGE_CATALOG_URL=<YourAzureStorage_Catalog_BLOB_URL>
#ESHOP_AZURE_SERVICE_BUS=<YourAzureServiceBusInfo>
```

<span data-ttu-id="8b7ed-200">Heben Sie die Auskommentierung in der Zeile ESHOP_AZURE_COSMOSDB auf, und aktualisieren Sie diese mit Ihrer Azure Cosmos DB-Verbindungszeichenfolge, die Sie über das Azure-Portal gemäß den Erläuterungen unter [Verbinden einer MongoDB-Anwendung mit Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account) abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-200">Uncomment the ESHOP_AZURE_COSMOSDB line and update it with your Azure Cosmos DB connection string obtained from the Azure portal as explained in [Connect a MongoDB application to Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).</span></span>

<span data-ttu-id="8b7ed-201">Wenn die globale Variable `ESHOP_AZURE_COSMOSDB` leer ist, was bedeutet, dass Sie in der Datei `.env` auskommentiert ist, verwendet der Container eine standardmäßige MongoDB-Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8b7ed-201">If the `ESHOP_AZURE_COSMOSDB` global variable is empty, meaning it's commented out in the `.env` file, then the container uses a default MongoDB connection string.</span></span> <span data-ttu-id="8b7ed-202">Diese Verbindungszeichenfolge verweist auf den lokalen MongoDB-Container, der in eShopOnContainers unter dem Namen `nosqldata` bereitgestellt und in der Datei „docker-compose“ definiert wurde. Dies wird im folgenden YML-Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8b7ed-202">This connection string points to the local MongoDB container deployed in eShopOnContainers that is named `nosqldata` and was defined at the docker-compose file, as shown in the following .yml code:</span></span>

``` yml
# docker-compose.yml
version: '3.4'
services:
  # ...Other services...
  nosqldata:
    image: mongo
```

#### <a name="additional-resources"></a><span data-ttu-id="8b7ed-203">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8b7ed-203">Additional resources</span></span>

- <span data-ttu-id="8b7ed-204">**Modellieren von Dokumentdaten für NoSQL-Datenbanken** </span><span class="sxs-lookup"><span data-stu-id="8b7ed-204">**Modeling document data for NoSQL databases** </span></span>\
  <https://docs.microsoft.com/azure/cosmos-db/modeling-data>

- <span data-ttu-id="8b7ed-205">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store? (Was ist der ideale DDD-Aggregatspeicher?)**</span><span class="sxs-lookup"><span data-stu-id="8b7ed-205">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**</span></span> \
  <https://kalele.io/blog-posts/the-ideal-domain-driven-design-aggregate-store/>

- <span data-ttu-id="8b7ed-206">**Einführung in die Azure Cosmos DB-API für MongoDB**  </span><span class="sxs-lookup"><span data-stu-id="8b7ed-206">**Introduction to Azure Cosmos DB: API for MongoDB**  </span></span>\
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction>

- <span data-ttu-id="8b7ed-207">**Azure Cosmos DB: Erstellen einer Web-App mit einer MongoDB-API mit .NET und dem Azure-Portal**  </span><span class="sxs-lookup"><span data-stu-id="8b7ed-207">**Azure Cosmos DB: Build a MongoDB API web app with .NET and the Azure portal**  </span></span>\
  <https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet>

- <span data-ttu-id="8b7ed-208">**Verwenden des Azure Cosmos DB-Emulators für lokale Entwicklungs- und Testvorgänge**  </span><span class="sxs-lookup"><span data-stu-id="8b7ed-208">**Use the Azure Cosmos DB Emulator for local development and testing**  </span></span>\
  <https://docs.microsoft.com/azure/cosmos-db/local-emulator>

- <span data-ttu-id="8b7ed-209">**Verbinden einer MongoDB-Anwendung mit Azure Cosmos DB**  </span><span class="sxs-lookup"><span data-stu-id="8b7ed-209">**Connect a MongoDB application to Azure Cosmos DB**  </span></span>\
  <https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account>

- <span data-ttu-id="8b7ed-210">**The Cosmos DB Emulator Docker image (Windows Container) (Das Docker-Image des Cosmos DB-Emulators (Windows-Container))**   </span><span class="sxs-lookup"><span data-stu-id="8b7ed-210">**The Cosmos DB Emulator Docker image (Windows Container)**  </span></span>\
  <https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/>

- <span data-ttu-id="8b7ed-211">**The MongoDB Docker image (Linux and Windows Container) (Das MongoDB-Docker-Image (Linux- und Windows-Container))**   </span><span class="sxs-lookup"><span data-stu-id="8b7ed-211">**The MongoDB Docker image (Linux and Windows Container)**  </span></span>\
  <https://hub.docker.com/_/mongo/>

- <span data-ttu-id="8b7ed-212">**Verwenden von MongoChef (Studio 3T) mit der Azure Cosmos DB-API für MongoDB-Konten**  </span><span class="sxs-lookup"><span data-stu-id="8b7ed-212">**Use MongoChef (Studio 3T) with an Azure Cosmos DB: API for MongoDB account**  </span></span>\
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef>

>[!div class="step-by-step"]
><span data-ttu-id="8b7ed-213">[Zurück](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
>[Weiter](microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="8b7ed-213">[Previous](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
[Next](microservice-application-layer-web-api-design.md)</span></span>
