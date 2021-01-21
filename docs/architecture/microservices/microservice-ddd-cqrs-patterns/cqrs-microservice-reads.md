---
title: Implementieren von Lesevorgängen/Abfragen in einem CQRS-Microservice
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Implementierung der Abfrageseite von CQRS im Microservice für Bestellungen in eShopOnContainers mit Dapper
ms.date: 01/13/2021
ms.openlocfilehash: 047fc3893dcaf72a17d29f5560c928879757d024
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188919"
---
# <a name="implement-readsqueries-in-a-cqrs-microservice"></a>Implementieren von Lesevorgängen/Abfragen in einem CQRS-Microservice

Der Microservice für Bestellungen aus der Referenzanwendung eShopOnContainers implementiert für Lesevorgänge/Abfragen die Abfragen unabhängig vom DDD-Modell und Transaktionsbereich. Diese Implementierung wurde in erster Linie durchgeführt, weil sich die Anforderungen an Abfragen und Transaktionen deutlich unterscheiden. Schreibvorgänge führen Transaktionen aus, die mit der Domänenlogik konform sein müssen. Abfragen sind hingegen idempotent und können von den Domänenregeln getrennt werden.

Dieser Ansatz ist einfach, wie in Abbildung 7-3 zu sehen ist. Die API-Schnittstelle wird von den Web-API-Controllern implementiert. Diese nutzen eine beliebige Infrastruktur (z.B. einen Micro-ORM (objektrelationaler Mapper) wie Dapper) und geben je nach Anforderungen der Benutzeroberflächenanwendungen dynamische ViewModels zurück.

![Diagramm, das die allgemeine Abfrageseite in vereinfachter CQRS zeigt.](./media/cqrs-microservice-reads/simple-approach-cqrs-queries.png)

**Abbildung 7-3**. Der einfachste Ansatz für Abfragen in einem CQRS-Microservice

Der einfachste Ansatz für die Abfrageseite in einem vereinfachten CQRS-Ansatz kann durch Abfragen der Datenbank mit einem Micro-ORM wie Dapper und Rückgabe dynamischer ViewModels implementiert werden. Durch Abfragedefinitionen wird die Datenbank abgefragt und ein ViewModel dynamisch für jede Abfrage erstellt. Da Abfragen idempotent sind, ändern sie Daten auch bei mehrmaliger Ausführung nicht. Daher sind keine Einschränkungen durch DDD-Muster (beispielsweise Aggregate und andere Muster) notwendig, die auf der Transaktionsseite verwendet werden. Dies ist auch der Grund, weshalb Abfragen vom Transaktionsbereich getrennt sind. Die von der Benutzeroberfläche benötigten Daten können durch eine Abfrage der Datenbank abgerufen werden. Außerdem wird ein dynamisches ViewModel zurückgegeben, das über keine Klasse verfügt und nur in den SQL-Anweisungen statisch definiert werden muss.

Da dieser Ansatz einfach ist, kann der für die Abfrageseite benötigte Code (beispielsweise Code, der auf Micro-ORMs wie [Dapper](https://github.com/StackExchange/Dapper) zurückgreift) [innerhalb desselben Web-API-Projekts](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs) implementiert werden. Dieser Ansatz wird in Abbildung 7-4 veranschaulicht. Die Abfragen werden im **Ordering.API**-Microserviceprojekt in der Projektmappe „eShopOnContainers“ definiert.

![Screenshot des Ordners „Queries“ des Ordering.API-Projekts.](./media/cqrs-microservice-reads/ordering-api-queries-folder.png)

**Abbildung 7-4**. Abfragen im Microservice für Bestellungen in eShopOnContainers

## <a name="use-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Verwenden von für Client-Apps erstellten und von Domänenmodelleinschränkungen unabhängigen ViewModels

Da durch Abfragen Daten abgerufen werden, die für die Clientanwendungen erforderlich sind, kann der Rückgabetyp auf der Grundlage der zurückgegebenen Daten speziell auf Clients festgelegt werden. Diese Modelle bzw. Datentransferobjekte (DTOs) werden als ViewModels bezeichnet.

Die zurückgegebenen Daten (also die ViewModels) können das Ergebnis einer Verknüpfung von Daten aus mehreren Entitäten oder Tabellen in der Datenbank oder einer Verknüpfung mehrerer Aggregate sein, die im Domänenmodell für den Transaktionsbereich definiert wurden. Da Sie in diesem Fall Abfragen unabhängig vom Domänenmodell erstellen, werden die Aggregatsgrenzen und -einschränkungen ignoriert, sodass alle erforderlichen Tabellen und Spalten abgefragt werden können. Dieser Ansatz sorgt dafür, dass Entwickler, die Abfragen erstellen oder aktualisieren, flexibler und produktiver arbeiten können.

ViewModels können statische Typen sein, die in Klassen definiert sind (wie im Microservice für Bestellungen implementiert). Alternativ können sie auf Grundlage bereits durchgeführter Abfragen dynamisch und flexibel erstellt werden.

## <a name="use-dapper-as-a-micro-orm-to-perform-queries"></a>Verwenden von Dapper als Micro-ORM zum Ausführen von Abfragen

Für Abfragen kann ein beliebiges Micro-ORM, Entity Framework Core oder sogar einfaches „ADO.NET für Abfragen“ verwendet werden. In der Beispielanwendung wurde Dapper für den Microservice für Bestellungen in eShopOnContainers ausgewählt, da dieses Tool ein gutes Beispiel für einen bekannten Micro-ORM ist. Da es sich um ein schlankes Framework handelt, lassen sich damit SQL-Abfragen leistungseffizient ausführen. Mit Dapper können Sie eine SQL-Abfrage schreiben, die auf mehrere Tabellen zugreifen und diese verknüpfen kann.

Bei dem Framework handelt es sich um ein Open Source-Projekt, das ursprünglich von Sam Saffron entworfen wurde und nun Teil des Grundgerüsts von [Stack Overflow](https://stackoverflow.com/) ist. Um Dapper zu verwenden, müssen Sie das Tool mithilfe des [Dapper-NuGet-Pakets](https://www.nuget.org/packages/Dapper) (s. Abbildung unten) installieren:

![Screenshot des Dapper-Pakets in der NuGet-Paketeansicht.](./media/cqrs-microservice-reads/drapper-package-nuget.png)

Außerdem ist das Hinzufügen einer `using`-Anweisung erforderlich, damit der Code auf die Dapper-Erweiterungsmethoden zugreifen kann.

Wenn Sie Dapper in Ihrem Code verwenden, nutzen Sie direkt die <xref:System.Data.SqlClient.SqlConnection>-Klasse im <xref:System.Data.SqlClient>-Namespace. Über die QueryAsync-Methode und andere Erweiterungsmethoden, die die <xref:System.Data.SqlClient.SqlConnection>-Klasse erweitern, können Sie Abfragen schnell ausführen.

## <a name="dynamic-versus-static-viewmodels"></a>Dynamische und statische ViewModels im Vergleich

ViewModels, die von serverseitigen Anwendungen an Client-Apps zurückgegeben werden, können als DTOs (Datentransferobjekte) betrachtet werden, die sich möglicherweise von den internen Domänenentitäten des Entitätsmodells unterscheiden, da ViewModels die für die Anwendung benötigten Daten enthalten. In vielen Fällen können Sie daher Daten aus unterschiedlichen Domänenentitäten aggregieren und die ViewModels so erstellen, dass die Datenanforderungen der Clientanwendung erfüllt werden.

Diese ViewModels oder DTOs können explizit (als Dateninhaberklassen) definiert werden, wie z. B. die `OrderSummary`-Klasse, die in einem späteren Codeausschnitt dargestellt wird. Alternativ können Sie einfach dynamische ViewModels oder dynamische DTOs zurückgeben, die auf den Attributen basieren, die von den Abfragen als dynamischer Typ zurückgegeben werden.

### <a name="viewmodel-as-dynamic-type"></a>ViewModel als dynamischer Typ

Wie im folgenden Codeausschnitt gezeigt wird, kann ein `ViewModel` direkt von Abfragen zurückgegeben werden, indem ein *dynamischer* Typ zurückgegeben wird, der intern auf den Attributen basiert, die von einer Abfrage zurückgegeben werden. Das bedeutet, dass die Teilmenge der Attribute, die zurückgegeben werden soll, auf der Abfrage selbst basiert. Wenn Sie also der Abfrage oder der Verknüpfung eine neue Spalte hinzufügen, werden diese Daten dynamisch dem zurückgegebenen `ViewModel` hinzugefügt.

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
                @"SELECT o.[Id] as ordernumber,
                o.[OrderDate] as [date],os.[Name] as [status],
                SUM(oi.units*oi.unitprice) as total
                FROM [ordering].[Orders] o
                LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
                LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
    }
}
```

Zu beachten ist, dass durch die Verwendung eines dynamischen Typs die zurückgegebene Datensammlung dynamisch als ViewModel zusammengestellt wird. Diese Vorgehensweise bringt sowohl Vor- als auch Nachteile mit sich:

**Vorteile:** Bei diesem Ansatz sind weniger Änderungen an statischen ViewModel-Klassen erforderlich, wenn die SQL-Anweisung einer Abfrage aktualisiert wird. Dies trägt zur Agilität und Einfachheit des Entwurfsansatzes bei und führt außerdem dazu, dass er bei zukünftig erforderlichen Änderungen schnell angepasst werden kann.

**Nachteile:** Dynamische Typen können sich langfristig negativ auf die Übersichtlichkeit und die Kompatibilität eines Diensts mit Client-Apps auswirken. Darüber hinaus stellt Middlewaresoftware wie Swashbuckle bei der Verwendung von dynamischen Typen nicht denselben Dokumentationsumfang für Rückgabetypen zur Verfügung.

### <a name="viewmodel-as-predefined-dto-classes"></a>ViewModel als vordefinierte DTO-Klasse

**Vorteile**: Vordefinierte statische ViewModel-Klassen wie „Verträge“, die auf expliziten DTO-Klassen beruhen, eignen sich insbesondere für öffentliche APIs. Ähnliches gilt auch für langfristige Microservices, selbst wenn diese nur für eine einzelne Anwendung eingesetzt werden.

Wenn Sie Antworttypen für Swagger festlegen möchten, müssen Sie explizite DTO-Klassen als Rückgabetyp verwenden. Mit vordefinierten DTO-Klassen können Sie daher mehr Informationen aus Swagger beziehen und anzeigen lassen. Dadurch werden die API-Dokumentation und die Kompatibilität bei der Nutzung der API verbessert.

**Nachteile**: Wie bereits erwähnt, sind für die Aktualisierung der DTO-Klassen mehrere Schritte erforderlich, sobald der Code geändert werden muss.

*Autorentipp*: Wir haben in den Abfragen, die im Microservice für Bestellungen in eShopOnContainers implementiert wurden, zunächst dynamische ViewModels verwendet, da sich dieses Vorgehen in frühen Entwicklungsphasen als leicht und agil erwiesen hat. Sobald unser Code stabil war, haben wir die APIs umgestaltet und statische oder vordefinierte DTOs für die ViewModels verwendet, da es für die Consumer des Microservices leichter war, mit expliziten DTO-Typen umzugehen, die als Verträge genutzt wurden.

Im folgenden Beispiel wird gezeigt, wie die Abfrage Daten mithilfe der expliziten ViewModel-DTO-Klasse „OrderSummary“ zurückgibt.

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<OrderSummary>(
                  @"SELECT o.[Id] as ordernumber,
                  o.[OrderDate] as [date],os.[Name] as [status],
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    }
}
```

#### <a name="describe-response-types-of-web-apis"></a>Beschreiben von Web-API-Antworttypen

Entwickler, die Web-APIs und Microservices nutzen, interessieren sich vor allem für die zurückgegebenen Antworttypen und Fehlercodes (wenn diese nicht den Standardwerten entsprechen). Diese Antworttypen werden in XML-Kommentaren und Datenanmerkungen verarbeitet.

Ohne eine geeignete Dokumentation auf der Swagger-Benutzeroberfläche weiß der Consumer nicht, welche Typen zurückgegeben werden oder welche HTTP-Statuscodes zurückgegeben werden können. Dieses Problem lässt sich durch Hinzufügen von <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType> beheben, wodurch Swashbuckle umfangreichere Informationen über das API-Rückgabemodell und die API-Rückgabewerte generiert. Dies wird im folgenden Codeausschnitt gezeigt:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
        //Additional code...
        [Route("")]
        [HttpGet]
        [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
            (int)HttpStatusCode.OK)]
        public async Task<IActionResult> GetOrders()
        {
            var userid = _identityService.GetUserIdentity();
            var orders = await _orderQueries
                .GetOrdersFromUserAsync(Guid.Parse(userid));
            return Ok(orders);
        }
    }
}
```

Das `ProducesResponseType`-Attribut kann allerdings keinen dynamischen Typ nutzen, sondern erfordert wie im folgenden Beispiel explizite Typen wie das `OrderSummary`-ViewModel-DTO:

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

Dies ist ein weiterer Grund, weshalb explizite Rückgabetypen langfristig besser als dynamische Typen sind. Wenn Sie das `ProducesResponseType`-Attribut verwenden, können Sie auch erwartete HTTP-Fehler und Codes (z. B. 200 oder 400) festlegen.

In der folgenden Abbildung wird gezeigt, wie ResponseType-Informationen auf der Swagger-Benutzeroberfläche dargestellt werden.

![Screenshot der Swagger-Benutzeroberflächenseite für die Bestell-API.](./media/cqrs-microservice-reads/swagger-ordering-http-api.png)

**Abbildung 7-5**. Swagger-Benutzeroberfläche mit Antworttypen und möglichen HTTP-Statuscodes von einer Web-API

Die Abbildung zeigt mehrere Beispielwerte, die auf den ViewModel-Typen basieren, und mögliche HTTP-Statuscodes, die zurückgegeben werden können.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Dapper**  
 <https://github.com/StackExchange/dapper-dot-net>

- **Julie Lerman. Datenpunkte – Dapper, Entity Framework und Hybrid-Apps (Artikel im MSDN Magazine)**  
  <https://docs.microsoft.com/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps>

- **ASP.NET Core-Web-API-Hilfeseiten mit Swagger**  
  <https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio>

>[!div class="step-by-step"]
>[Zurück](eshoponcontainers-cqrs-ddd-microservice.md)
>[Weiter](ddd-oriented-microservice.md)
