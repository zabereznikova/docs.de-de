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
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a>Verwenden keine NoSQL-Datenbanken als Persistenz Infrastruktur

Wenn Sie keine NoSQL-Datenbanken für Ihre Infrastruktur Datenebene verwenden, verwenden Sie ein ORM wie Entity Framework Core in der Regel nicht. Stattdessen verwenden Sie die API, die vom NoSQL-Modul, wie z. B. Azure-Cosmos-DB, MongoDB, Cassandra, RavenDB, CouchDB oder Azure-Speichertabellen bereitgestellt.

Bei Verwendung eine NoSQL-Datenbank, insbesondere eine dokumentorientiert Datenbank wie Azure-Cosmos-DB, CouchDB oder RavenDB, ist jedoch die Möglichkeit, die Sie das Modell mit DDD Aggregaten entwerfen teilweise ähnelt in EF-Core in Bezug auf die Kennung des Vorgehensweise können Aggregieren Stämme, untergeordneten Entitätsklassen und Wertklassen-Objekt. Aber letztendlich, wirkt sich die Datenbankauswahl im Entwurf.

Wenn Sie eine Datenbank dokumentorientiert verwenden, implementieren Sie ein Aggregat als ein einzelnes Dokument, das in JSON oder ein anderes Format serialisiert. Allerdings ist die Verwendung der Datenbank aus einer Domäne Modell Codeansicht transparent. Wenn Sie eine NoSQL-Datenbank verwenden zu können, Sie weiterhin sind Entitätsklassen und aggregieren Stammklassen, aber mit mehr Flexibilität als bei Verwendung EF Core, da die Persistenz ist nicht relationale.

Der Unterschied besteht darin, wie Sie dieses Modell beibehalten. Wenn Sie Ihre Domänenmodell auf Grundlage von Klassen für POCO-Entitäten implementiert, kann unabhängig von der Infrastruktur Persistenz er anscheinend zu einer anderen Persistenz-Infrastruktur auch aus relationalen Datenquellen zu NoSQL verschoben werden können. Allerdings sollten, die nicht Ziel sein. Es gibt immer Einschränkungen in den verschiedenen Datenbanken werden mithilfe von Push übertragen Sie zurück, sodass Sie nicht das gleiche Modell für haben können relationale oder NoSQL-Datenbanken. Ändern die Persistenz Modelle würde nicht trivial, werden, weil Transaktionen und persistenzvorgänge sehr unterschiedlich.

In einer Datenbank dokumentorientiert ist es beispielsweise angemessen für einen aggregierten Stamm, mehrere untergeordnete Sammlungseigenschaften zu verwenden. In einer relationalen Datenbank wird Abfragen von mehreren untergeordneten Sammlungseigenschaften unsinnig, ist, da Sie eine Vereinigung aller SQL-Anweisung aus EF abzurufen. Mit der gleichen Domänenmodell für relationale Datenbanken oder NoSQL-Datenbanken ist nicht einfach, und Sie sollten nicht versuchen. Sie haben sich tatsächlich so entwerfen Sie Ihr Modell mit einem Überblick darüber, wie die Daten in jeder bestimmte Datenbank verwendet werden soll.

Ein Vorteil bei Verwendung von NoSQL-Datenbanken ist, dass die Entitäten mehr denormalisierten, Sie sollte daher nicht die Zuordnung zu einer Tabelle. Ihre Domänenmodell kann flexibler als bei Verwendung einer relationalen Datenbank sein.

Wenn Sie entwerfen Ihre Domänenmodell basierend auf den Aggregate, um NoSQL verschieben und dokumentorientiert Datenbanken möglicherweise noch einfacher als die Verwendung einer relationalen Datenbank, die Aggregate, die Sie entwerfen ähneln serialisiert Dokumente in einer Datenbank dokumentorientiert. Dann können Sie in diesen "Sammlungen" alle Informationen einschließen, die Sie für das Aggregat eventuell.

Der folgende JSON-Code wird z. B. eine beispielimplementierung eines Aggregats Reihenfolge aus, bei Verwendung einer Datenbank dokumentorientiert. Es ähnelt der aggregierten Reihenfolge, die wir im eShopOnContainers Beispiel, jedoch ohne Verwendung von EF Core unterhalb implementiert.

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

Bei Verwendung von C\# Modell, das Aggregat von etwa wie das Azure Cosmos-DB-SDK, das Aggregat zu verwendende Implementierung ähnelt C\# POCO-Klassen, die mit EF Core verwendet. Der Unterschied besteht darin, die Möglichkeit, ihren Einsatz aus dem die Anwendung und Infrastruktur Ebenen, wie im folgenden Code:

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

Sie können sehen, dass die Möglichkeit, die Arbeit mit Ihrem Domänenmodell ähnlich wie bei Sie es in Ihrer Domäne der Ebene verwenden sein können, wenn die Infrastruktur EF ist. Sie verwenden weiterhin die gleichen aggregieren Stamm-Methoden, um Konsistenz Invarianten und Überprüfungen in das Aggregat sicherzustellen.

Jedoch beibehalten, wenn Sie das Modell in der NoSQL-Datenbank, den Code und API ändern sich im Vergleich zu EF Kerncode oder anderen Code, die im Zusammenhang mit relationalen Datenbanken.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Modellieren von Daten in DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)

-   **Vaughn Vernon. Die ideale Domain Driven Design Aggregat Store? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)

-   **Ein Persistenz agnostisch Ereignisspeicher für .NET.** GitHub-Repository.
    [*https://github.com/NEventStore/NEventStore*](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
[Vorherigen] (Infrastructure-persistence-layer-implemenation-entity-framework-core.md) [weiter] (Microservice-application-layer-web-api-design.md)
