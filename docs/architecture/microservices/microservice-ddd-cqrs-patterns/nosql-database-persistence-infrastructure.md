---
title: Verwenden von NoSQL-Datenbanken als Persistenzinfrastruktur
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Verwendung von NoSql-Datenbanken im Allgemeinen – und Azure Cosmos DB im Speziellen – als Option zum Implementieren von Persistenz
ms.date: 10/08/2018
ms.openlocfilehash: 44fc2fa01e2d19efed7314f421a682c0a635a9f6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737403"
---
# <a name="use-nosql-databases-as-a-persistence-infrastructure"></a>Verwenden von NoSQL-Datenbanken als Persistenzinfrastruktur

Wenn Sie NoSQL-Datenbanken für die Datenschicht Ihrer Infrastruktur verwenden, verwenden Sie in der Regel keine ORM wie Entity Framework Core. Stattdessen verwenden Sie die API, die von der NoSQL-Engine, wie z.B. Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB oder Azure Table Storage, bereitgestellt wird.

Wenn Sie jedoch eine NoSQL-Datenbank verwenden, insbesondere eine dokumentorientierte Datenbank wie Azure Cosmos DB, CouchDC oder RavenDB, ist die Art und Weise, in der Sie Ihr Modell mit DDD-Aggregaten entwerfen, teilweise mit der Vorgehensweise in EF Core vergleichbar, z.B. in Bezug auf die Identifikation von Aggregatstämmen, untergeordneten Entitätsklassen und Wertobjektklassen. Letztendlich hat die Datenbankauswahl jedoch Auswirkungen auf Ihren Entwurf.

Wenn Sie eine dokumentorientierte Datenbank verwenden, implementieren Sie ein Aggregat als einzelnes Dokument, das im JSON-Format oder einem anderen Format serialisiert ist. Allerdings ist die Verwendung der Datenbank aus Sicht eines Codeelements des Domänenmodells transparent. Durch eine NoSQL-Datenbank verwenden Sie weiterhin Entitätsklassen und Aggregatstammklassen, jedoch mit mehr Flexibilität als bei der Verwendung von EF Core, da die Persistenz nicht relational ist.

Der Unterschied besteht darin, wie Sie dieses Modell speichern. Wenn Sie Ihr Domänenmodell (unabhängig von der Persistenz der Infrastruktur) basierend auf POCO-Entitätsklassen implementiert haben, wirkt es möglicherweise so, als könnten Sie zu einer anderen Persistenz der Infrastruktur wechseln, sogar von einer relationalen zur NoSQL-Datenbank. Das sollte jedoch nicht Ihr Ziel sein. In den verschiedenen Datenbanktechnologien gibt es immer Einschränkungen und Abwägungen, sodass Sie für relationale oder NoSQL-Datenbanken nicht dasselbe Modell verwenden können. Das Ändern von Persistenzmodellen ist nicht leicht, da Transaktionen und Persistenzvorgänge sehr unterschiedlich sein werden.

So ist es in einer dokumentorientierten Datenbank beispielsweise in Ordnung, wenn ein Aggregatstamm über mehrere untergeordnete Sammlungseigenschaften verfügt. In einer relationalen Datenbank lässt sich das Abfragen mehrerer untergeordneter Sammlungseigenschaften nicht einfach optimieren, da EF die SQL-Anweisung UNION ALL zurückgibt. Über dasselbe Domänenmodell für relationale Datenbanken oder NoSQL-Datenbanken zu verfügen, ist nicht einfach. Es wird davon abgeraten, es zu probieren. Sie müssen Ihr eigenes Modell entwerfen und dabei verstehen, wie die Daten in den einzelnen Datenbanken verwendet werden sollen.

Ein Vorteil bei der Verwendung von NoSQL-Datenbanken besteht darin, dass die Entitäten denormalisierter sind und Sie daher keine Tabellenzuordnung festlegen. Ihr Domänenmodell kann flexibler als bei der Verwendung einer relationalen Datenbank sein.

Wenn Sie Ihr Domänenmodell basierend auf Aggregaten entwerfen, ist der Wechsel zu NoSQL- und dokumentorientierten Datenbanken möglicherweise einfacher als die Verwendung einer relationalen Datenbank, da die von Ihnen entworfenen Aggregate mit serialisierten Dokumenten in einer dokumentorientierten Datenbank vergleichbar sind. In diesen Sammlungen können Sie anschließend alle Informationen einschließen, die Sie für dieses Aggregat gebrauchen könnten.

Bei dem folgenden JSON-Code handelt es sich beispielsweise um die Beispielimplementierung des Aggregats „Order“ bei der Verwendung einer dokumentorientierten Datenbank. Er ist mit dem Aggregat „Order“ vergleichbar, das im „eShopOnContainers“-Beispiel implementiert wurde, jedoch ohne die untergeordnete Verwendung von EF Core.

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

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a>Einführung in Azure Cosmos DB und die native Cosmos DB-API

[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) ist der globale verteilte Datenbankdienst von Microsoft für unternehmenskritische Anwendungen. Azure Cosmos DB stellt eine [sofort einsatzfähige globale Verteilung](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), weltweit eine [elastische Skalierung von Durchsatz und Speicher](https://docs.microsoft.com/azure/cosmos-db/partition-data), Latenzen im einstelligen Millisekundenbereich im 99. Perzentil, [fünf richtig definierte Konsistenzebenen](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) und garantierte Hochverfügbarkeit bereit. Dies alles wird durch [branchenführende SLAs](https://azure.microsoft.com/support/legal/sla/cosmos-db/) gewährleistet. Azure Cosmos DB [indiziert automatisch Daten](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf), ohne dass Sie sich mit der Schema- und Indexverwaltung auseinandersetzen müssen. Die Datenbank umfasst mehrere Modelle und unterstützt Dokument-, Schlüsselwert-, Graph- sowie einspaltige Datenmodelle.

![Diagramm, das die globale Verteilung von Azure Cosmos DB zeigt.](./media/nosql-database-persistence-infrastructure/azure-cosmos-db-global-distribution.png)

**Abbildung 7-19**. Globale Verteilung von Azure Cosmos DB

Bei der Verwendung eines C\#-Modells zur Implementierung des Aggregats, das von der Azure Cosmos DB-API verwendet werden soll, kann das Aggregat mit den in EF Core verwendeten C\#-POCO-Klassen vergleichbar sein. Der Unterschied besteht darin, wie diese auf der Anwendungs- und der Infrastrukturebene verwendet werden. Dies wird im folgenden Code veranschaulicht:

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

Sie können sehen, dass die Art und Weise, in der Sie mit Ihrem Domänenmodell arbeiten, mit der Verwendungsweise auf der Ebene Ihres Domänenmodells vergleichbar ist, wenn EF die Infrastruktur ist. Sie verwenden weiterhin die gleichen Aggregatstammmethoden, um Konsistenz, Invarianten und Validierungen innerhalb des Aggregats sicherzustellen.

Wenn Sie Ihr Modell jedoch dauerhaft in der NoSQL-Datenbank speichern, führt dies zu einer wesentlichen Änderung des Codes und der API im Vergleich zu EF Core-Code oder einem beliebigen anderen Code für relationale Datenbanken.

## <a name="implement-net-code-targeting-mongodb-and-azure-cosmos-db"></a>Implementieren von .NET-Code für MongoDB und Azure Cosmos DB

### <a name="use-azure-cosmos-db-from-net-containers"></a>Verwenden von Azure Cosmos DB über .NET-Container

Sie können über .NET-Code, der in Containern ausgeführt wird, auf Azure Cosmos DB-Datenbanken genau wie über eine beliebige andere .NET-Anwendung zugreifen. Die Microservices „Locations.API“ und „Marketing.API“ in eShopOnContainers werden beispielsweise implementiert, damit sie Azure Cosmos DB-Datenbanken verwenden können.

Aus der Sicht einer Docker-Entwicklungsumgebung gibt es in Azure Cosmos DB jedoch eine Einschränkung. Es ist zwar ein lokaler [Azure Cosmos DB-Emulator](https://docs.microsoft.com/azure/cosmos-db/local-emulator) vorhanden, der auf einem lokalen Entwicklungscomputer (z.B. auf einem PC) ausgeführt werden kann, seit Ende 2017 unterstützt dieser jedoch nur noch Windows, nicht Linux.

Dieser Emulator kann auch in Docker ausgeführt werden, allerdings nur in Windows-Containern, nicht in Linux-Containern. Dies ist ein anfängliches Handicap für die Entwicklungsumgebung, wenn Ihre Anwendung in Linux-Containern bereitgestellt wird, da eine gleichzeitige Bereitstellung von Linux- und Windows-Containern in Docker für Windows derzeit nicht möglich ist. Alle bereitgestellten Container müssen entweder für Linux oder für Windows bestimmt sein.

Der ideale und einfachere Weg zur Bereitstellung für eine Entwicklungs-/Testlösung besteht darin, Ihre Datenbanksysteme zusammen mit Ihren benutzerdefinierten Containern als Container bereitzustellen, damit Ihre Entwicklungs-/Testumgebungen immer konsistent sind.

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a>Verwenden der MongoDB-API für lokale Entwicklungs-/Testcontainer unter Linux/Windows plus Azure Cosmos DB

Cosmos DB-Datenbanken unterstützen die MongoDB-API für .NET sowie das native MongoDB Wire Protocol. Das bedeutet, dass Ihre für MongoDB geschriebene Anwendung unter Verwendung vorhandener Treiber nun mit Cosmos DB kommunizieren und Cosmos DB-Datenbanken anstelle von MongoDB-Datenbanken verwenden kann (s. Abbildung 7-20).

![Diagramm, das zeigt, dass Cosmos DB das .NET- und MongoDB-Wire Protocol unterstützt.](./media/nosql-database-persistence-infrastructure/mongodb-api-wire-protocol.png)

**Abbildung 7-20**. Verwenden der API und des Protokolls von MongoDB für den Zugriff auf Azure Cosmos DB

Dies ist ein sehr praktischer Ansatz für Proof of Concepts in Docker-Umgebungen mit Linux-Containern, da es sich bei dem [MongoDB-Docker-Image](https://hub.docker.com/r/_/mongo/) um ein Image für mehrere Architekturen handelt, das Linux- und Windows-basierte Docker-Container unterstützt.

Wie die folgende Abbildung zeigt, unterstützt eShopOnContainers unter Verwendung der MongoDB-API MongoDB-Container unter Linux und Windows in der lokalen Entwicklungsumgebung. Anschließend können Sie zu einer skalierbaren PaaS-Cloudlösung wie Azure Cosmos DB wechseln, indem Sie einfach die [MongoDB-Verbindungszeichenfolge so ändern, dass sie auf Azure Cosmos DB verweist](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).

![Diagramm, das zeigt, dass der Location-Microservice in eShopOnContainers entweder Cosmos DB oder Mongo DB verwenden kann.](./media/nosql-database-persistence-infrastructure/eshoponcontainers-mongodb-containers.png)

**Abbildung 7-21**. eShopOnContainers mit MongoDB-Containern für die Entwicklungsumgebung oder Azure Cosmos DB für die Produktion

Azure Cosmos DB für die Produktion würde in der Azure-Cloud als PaaS und als skalierbarer Dienst ausgeführt werden.

Ihre benutzerdefinierten .NET Core-Container können auf einem lokalen Docker-Entwicklungshost ausgeführt werden (das heißt, Docker für Windows wird auf einem Computer mit Windows 10 verwendet) oder in einer Produktionsumgebung wie Kubernetes in Azure AKS oder Azure Service Fabric bereitgestellt werden. In dieser zweiten Umgebung würden Sie nur die benutzerdefinierten .NET Core-Container, jedoch nicht die MongoDB-Container bereitstellen, da Sie Azure Cosmos DB in der Cloud für die Verwaltung der Daten in der Produktion verwenden würden.

Ein klarer Vorteil bei der Verwendung der MongoDB-API besteht darin, dass Ihre Lösung in beiden Datenbank-Engines (MongoDB oder Azure Cosmos DB) ausgeführt werden könnte, sodass Migrationen in verschiedenen Umgebungen problemlos durchgeführt werden könnten. Manchmal ist es jedoch sinnvoll, eine native API (in diesem Fall die native Cosmos DB-API) zu verwenden, um die Funktionen einer bestimmten Datenbank-Engine optimal nutzen zu können.

Informationen zum weiteren Vergleich zwischen der einfachen Verwendung von MongoDB im Vergleich zu Cosmos DB in der Cloud finden Sie auf dieser Seite unter [Benefits of using Azure Cosmos DB in this page (Vorteile der Verwendung von Azure Cosmos DB)](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction).

### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a>Analysieren Ihres Ansatzes für Produktionsanwendungen: Vergleich zwischen der MongoDB-API und der Cosmos DB-API

In eShopOnContainers wird die MongoDB-API verwendet, da die Priorität im Wesentlichen darauf liegt, über eine konsistente Entwicklungs-/Testumgebung zu verfügen, in der eine NoSQL-Datenbank verwendet wird, die auch in Azure Cosmos DB eingesetzt werden könnte.

Wenn Sie die Verwendung der MongoDB-API für den Zugriff auf Azure Cosmos DB in Azure für Produktionsanwendungen planen, sollten Sie jedoch die Unterschiede in den Funktionen und der Leistung bei der Verwendung der MongoDB-API für den Zugriff auf Azure Cosmos DB-Datenbanken verglichen mit der Verwendung der nativen Azure Cosmos DB-API analysieren. Wenn die Funktionen und die Leistung vergleichbar sind, können Sie die MongoDB-API verwenden und davon profitieren, dass zwei NoSQL-Datenbank-Engines gleichzeitig unterstützt werden.

Alternativ könnten Sie auch MongoDB-Cluster mit dem [MongoDB-Azure-Dienst](https://www.mongodb.com/scale/mongodb-azure-service) als Produktionsdatenbank in der Azure-Cloud verwenden. Dies ist jedoch kein von Microsoft bereitgestellter PaaS-Dienst. In diesem Fall hostet Azure lediglich diese Lösung aus MongoDB.

Im Wesentlichen ist dies nur ein Haftungsausschluss, in dem darauf hingewiesen wird, dass Sie die Verwendung der MongoDB-API nicht immer der Verwendung von Azure Cosmos DB vorziehen sollten. In eShopOnContainers wurde dies durchgeführt, weil es sich dabei um eine praktische Wahl für Linux-Container handelt. Grundlage der Entscheidung sollten die spezifischen Anforderungen und Tests sein, die Sie für Ihre Produktionsanwendung durchführen müssen.

### <a name="the-code-use-mongodb-api-in-net-core-applications"></a>Der Code: Verwenden der MongoDB-API in .NET Core-Anwendungen

Die MongoDB-API für .NET basiert auf NuGet-Paketen, die Sie Ihren Projekten hinzufügen müssen, wie das Locations.API-Projekt in der folgenden Abbildung.

![Screenshot der Abhängigkeiten in den MongoDB-NuGet-Paketen.](./media/nosql-database-persistence-infrastructure/mongodb-api-nuget-packages.png)

**Abbildung 7-22**. Verweise auf NuGet-Pakete in der MongoDB-API in einem .NET Core-Projekt

In den folgenden Abschnitten wird der Code untersucht.

#### <a name="a-model-used-by-mongodb-api"></a>Ein von der MongoDB-API verwendetes Modell

Zunächst müssen Sie ein Modell definieren, das die Daten enthält, die aus der Datenbank den Speicherplatz Ihrer Anwendung belegen. Im Folgenden sehen Sie ein Beispiel für das Modell, das in eShopOnContainers für „Locations“ verwendet wird.

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

Sie können sehen, dass einige Attribute und Typen aus den NuGet-Paketen von MongoDB stammen.

NoSQL-Datenbanken eignen sich in der Regel sehr gut für die Arbeit mit nicht relationalen hierarchischen Daten. In diesem Beispiel verwenden wir MongoDB-Typen, die speziell für geografische Standorte erstellt wurden, wie z.B. `GeoJson2DGeographicCoordinates`.

#### <a name="retrieve-the-database-and-the-collection"></a>Abrufen von Datenbank und Sammlung

In eShopOnContainers wurde ein benutzerdefinierter Datenbankkontext erstellt, in dem der Code implementiert wurde, um die Datenbank und die MongoCollections abzurufen. Dies wird im folgenden Code dargestellt.

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

#### <a name="retrieve-the-data"></a>Abrufen der Daten

In C#-Code, wie z.B. Web-API-Controllern oder der Implementierung benutzerdefinierter Repositorys, können Sie bei der Abfrage über die MongoDB-API Code schreiben, der mit dem folgenden Code vergleichbar ist. Beachten Sie, dass das Objekt `_context` eine Instanz der vorherigen Klasse `LocationsContext` ist.

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a>Verwenden einer Umgebungsvariable in der Datei „docker-compose.override.yml“ für die MongoDB-Verbindungszeichenfolge

Bei der Erstellung eines MongoClient-Objekts ist ein grundlegender Parameter erforderlich, genau genommen der Parameter `ConnectionString`, der auf die korrekte Datenbank verweist. Bei eShopOnContainers kann die Verbindungszeichenfolge auf einen lokalen MongoDB-Docker-Container oder auf eine „Produktionsdatenbank“ in Azure Cosmos DB verweisen.  Diese Verbindungszeichenfolge ergibt sich aus den Umgebungsvariablen, die in den Dateien `docker-compose.override.yml` definiert sind. Diese werden bei der Bereitstellung mit „docker-compose“ oder Visual Studio verwendet, wie im folgenden YML-Code zu sehen ist.

```yml
# docker-compose.override.yml
version: '3.4'
services:
  # Other services
  locations.api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}

```

Die Umgebungsvariable `ConnectionString` wird wie folgt aufgelöst: Wenn die globale Variable `ESHOP_AZURE_COSMOSDB` in der Datei `.env` mit der Azure Cosmos DB-Verbindungszeichenfolge definiert wird, verwendet sie diese für den Zugriff auf die Azure Cosmos DB-Datenbank in der Cloud. Wenn sie nicht definiert ist, nimmt sie den Wert `mongodb://nosql.data` an und verwendet den MongoDB-Entwicklungscontainer.

Im folgenden Code wird dargestellt, wie die `.env`-Datei mit der globalen Umgebungsvariable in der Azure Cosmos DB-Verbindungszeichenfolge in eShopOnContainers implementiert wird:

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

Sie sollten die Auskommentierung in der Zeile ESHOP_AZURE_COSMOSDB aufheben und diese mit Ihrer Azure Cosmos DB-Verbindungszeichenfolge aktualisieren, die Sie über das Azure-Portal gemäß den Erläuterungen unter [Connect a MongoDB application to Azure Cosmos DB (Verbinden einer MongoDB-Anwendung mit Azure Cosmos DB)](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account) abgerufen haben.

Wenn die globale Variable `ESHOP_AZURE_COSMOSDB` leer ist, d.h. sie in der `.env`-Datei auskommentiert wurde, verwendet der Container eine standardmäßige MongoDB-Verbindungszeichenfolge, die auf den lokalen MongoDB-Container verweist, der in eShopOnContainers unter dem Namen `nosql.data` bereitgestellt und in der Datei „docker-compose“ definiert wurde. Dies wird im folgenden YML-Code dargestellt.

``` yml
# docker-compose.yml
version: '3.4'
services:
  # ...Other services...
  nosql.data:
    image: mongo
```

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Modellieren von Dokumentdaten für NoSQL-Datenbanken** \
  <https://docs.microsoft.com/azure/cosmos-db/modeling-data>

- **Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store? (Was ist der ideale DDD-Aggregatspeicher?)** \
  <https://kalele.io/blog-posts/the-ideal-domain-driven-design-aggregate-store/>

- **Einführung in die Azure Cosmos DB-API für MongoDB**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction>

- **Azure Cosmos DB: Erstellen einer Web-App mit einer MongoDB-API mit .NET und dem Azure-Portal**  \
  <https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet>

- **Verwenden des Azure Cosmos DB-Emulators für lokale Entwicklungs- und Testvorgänge**  \
  <https://docs.microsoft.com/azure/cosmos-db/local-emulator>

- **Verbinden einer MongoDB-Anwendung mit Azure Cosmos DB**  \
  <https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account>

- **The Cosmos DB Emulator Docker image (Windows Container) (Das Docker-Image des Cosmos DB-Emulators (Windows-Container))**   \
  <https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/>

- **The MongoDB Docker image (Linux and Windows Container) (Das MongoDB-Docker-Image (Linux- und Windows-Container))**   \
  <https://hub.docker.com/_/mongo/>

- **Verwenden von MongoChef (Studio 3T) mit der Azure Cosmos DB-API für MongoDB-Konten**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef>

>[!div class="step-by-step"]
>[Zurück](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
>[Weiter](microservice-application-layer-web-api-design.md)
