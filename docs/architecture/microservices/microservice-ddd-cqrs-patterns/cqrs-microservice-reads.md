---
title: Implementieren von Lesevorgängen/Abfragen in einem CQRS-Microservice
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Implementierung der Abfrageseite von CQRS im Microservice für Bestellungen in eShopOnContainers mit Dapper
ms.date: 10/08/2018
ms.openlocfilehash: 235b0e471a17e2a37a883a111cf499b7837f3ea1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972088"
---
# <a name="implement-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="580a1-103">Implementieren von Lesevorgängen/Abfragen in einem CQRS-Microservice</span><span class="sxs-lookup"><span data-stu-id="580a1-103">Implement reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="580a1-104">Der Microservice für Bestellungen aus der Referenzanwendung eShopOnContainers implementiert für Lesevorgänge/Abfragen die Abfragen unabhängig vom DDD-Modell und Transaktionsbereich.</span><span class="sxs-lookup"><span data-stu-id="580a1-104">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="580a1-105">Dies liegt daran, dass sich die Anforderungen an Abfragen und Transaktionen deutlich unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="580a1-105">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="580a1-106">Schreibvorgänge führen Transaktionen aus, die mit der Domänenlogik konform sein müssen.</span><span class="sxs-lookup"><span data-stu-id="580a1-106">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="580a1-107">Abfragen sind hingegen idempotent und können von den Domänenregeln getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-107">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="580a1-108">Dieser Ansatz ist einfach, wie in Abbildung 7-3 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="580a1-108">The approach is simple, as shown in Figure 7-3.</span></span> <span data-ttu-id="580a1-109">Die API-Schnittstelle wird von den Web-API-Controllern implementiert. Diese nutzen eine beliebige Infrastruktur (z.B. einen Micro-ORM (objektrelationaler Mapper) wie Dapper) und geben je nach Anforderungen der Benutzeroberflächenanwendungen dynamische ViewModels zurück.</span><span class="sxs-lookup"><span data-stu-id="580a1-109">The API interface is implemented by the Web API controllers using any infrastructure, such as a micro Object Relational Mapper (ORM) like Dapper, and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![Diagramm, das die allgemeine Abfrageseite in vereinfachter CQRS zeigt.](./media/cqrs-microservice-reads/simple-approach-cqrs-queries.png)

<span data-ttu-id="580a1-111">**Abbildung 7-3**.</span><span class="sxs-lookup"><span data-stu-id="580a1-111">**Figure 7-3**.</span></span> <span data-ttu-id="580a1-112">Der einfachste Ansatz für Abfragen in einem CQRS-Microservice</span><span class="sxs-lookup"><span data-stu-id="580a1-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="580a1-113">Der einfachste Ansatz für die Abfrageseite in einem vereinfachten CQRS-Ansatz kann durch einfaches Abfragen der Datenbank mit einem Micro-ORM wie Dapper und Rückgabe dynamischer ViewModels implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-113">The simplest approach for the queries-side in a simplified CQRS approach can be implemented by just querying the database with a Micro-ORM like Dapper, returning dynamic ViewModels.</span></span> <span data-ttu-id="580a1-114">Durch Abfragedefinitionen wird die Datenbank abgefragt und ein ViewModel dynamisch für jede Abfrage erstellt.</span><span class="sxs-lookup"><span data-stu-id="580a1-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="580a1-115">Da Abfragen idempotent sind, ändern sie Daten auch bei mehrmaliger Ausführung nicht.</span><span class="sxs-lookup"><span data-stu-id="580a1-115">Since the queries are idempotent, they won't change the data no matter how many times you run a query.</span></span> <span data-ttu-id="580a1-116">Daher sind keine Einschränkungen durch DDD-Muster (beispielsweise Aggregate und andere Muster) notwendig, die auf der Transaktionsseite verwendet werden. Dies ist auch der Grund, weshalb Abfragen vom Transaktionsbereich getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="580a1-116">Therefore, you don't need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="580a1-117">Die von der Benutzeroberfläche benötigten Daten können durch eine einfache Abfrage der Datenbank abgerufen werden. Außerdem wird ein dynamisches ViewModel zurückgegeben, das über keine Klasse verfügt und nur in den SQL-Anweisungen statisch definiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="580a1-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="580a1-118">Da dieser Ansatz sehr einfach ist, kann der für die Abfrageseite benötigte Code (beispielsweise Code, der auf Micro-ORMs wie [Dapper](https://github.com/StackExchange/Dapper) zurückgreift) [innerhalb desselben WEB-API-Projekts](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs) implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="580a1-119">Dies ist in Abbildung 7-4 zu sehen.</span><span class="sxs-lookup"><span data-stu-id="580a1-119">Figure 7-4 shows this.</span></span> <span data-ttu-id="580a1-120">Die Abfragen werden im **Ordering.API**-Microserviceprojekt in der Projektmappe „eShopOnContainers“ definiert.</span><span class="sxs-lookup"><span data-stu-id="580a1-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![Screenshot des Ordners „Abfragen“ des Ordering.API-Projekts.](./media/cqrs-microservice-reads/ordering-api-queries-folder.png)

<span data-ttu-id="580a1-122">**Abbildung 7-4**.</span><span class="sxs-lookup"><span data-stu-id="580a1-122">**Figure 7-4**.</span></span> <span data-ttu-id="580a1-123">Abfragen im Microservice für Bestellungen in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="580a1-123">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="use-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="580a1-124">Verwenden von für Client-Apps erstellten und von Domänenmodelleinschränkungen unabhängigen ViewModels</span><span class="sxs-lookup"><span data-stu-id="580a1-124">Use ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="580a1-125">Da durch Abfragen Daten abgerufen werden, die für die Clientanwendungen erforderlich sind, kann der Rückgabetyp auf der Grundlage der zurückgegebenen Daten speziell auf Clients festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-125">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="580a1-126">Diese Modelle bzw. Datentransferobjekte (DTOs) werden als ViewModels bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="580a1-126">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="580a1-127">Die zurückgegebenen Daten (also die ViewModels) können das Ergebnis einer Verknüpfung von Daten aus mehreren Entitäten oder Tabellen in der Datenbank oder einer Verknüpfung mehrerer Aggregate sein, die im Domänenmodell für den Transaktionsbereich definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="580a1-127">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="580a1-128">Da Sie in diesem Fall Abfragen unabhängig vom Domänenmodell erstellen, werden die Aggregatsgrenzen und -einschränkungen vollständig ignoriert, sodass alle erforderlichen Tabellen und Spalten abgefragt werden können.</span><span class="sxs-lookup"><span data-stu-id="580a1-128">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you're free to query any table and column you might need.</span></span> <span data-ttu-id="580a1-129">Dieser Ansatz sorgt dafür, dass Entwickler, die Abfragen erstellen oder aktualisieren, flexibler und produktiver arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="580a1-129">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="580a1-130">Die ViewModels können als statische Typen in Klassen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-130">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="580a1-131">Alternativ lassen sie sich auch auf der Grundlage bereits durchgeführter Abfragen dynamisch erstellen, was im Microservice für Bestellungen implementiert wurde. Hierdurch wird die Entwicklungsagilität gefördert.</span><span class="sxs-lookup"><span data-stu-id="580a1-131">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="use-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="580a1-132">Verwenden von Dapper als Micro-ORM zum Ausführen von Abfragen</span><span class="sxs-lookup"><span data-stu-id="580a1-132">Use Dapper as a micro ORM to perform queries</span></span>

<span data-ttu-id="580a1-133">Für Abfragen kann ein beliebiges Micro-ORM, Entity Framework Core oder sogar einfaches „ADO.NET für Abfragen“ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-133">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="580a1-134">In der Beispielanwendung wurde Dapper für den Microservice für Bestellungen in eShopOnContainers ausgewählt, da dieses Tool ein gutes Beispiel für einen bekannten Micro-ORM ist.</span><span class="sxs-lookup"><span data-stu-id="580a1-134">In the sample application, Dapper was selected for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="580a1-135">Da es sich um ein sehr schlankes Framework handelt, lassen sich mit diesen SQL-Abfragen leistungseffizient ausführen.</span><span class="sxs-lookup"><span data-stu-id="580a1-135">It can run plain SQL queries with great performance, because it's a very light framework.</span></span> <span data-ttu-id="580a1-136">Mit Dapper können Sie eine SQL-Abfrage schreiben, die auf mehrere Tabellen zugreifen und diese verknüpfen kann.</span><span class="sxs-lookup"><span data-stu-id="580a1-136">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="580a1-137">Bei dem Framework handelt es sich um ein Open Source-Projekt, das ursprünglich von Sam Saffron entworfen wurde und nun Teil des Grundgerüsts von [Stack Overflow](https://stackoverflow.com/) ist.</span><span class="sxs-lookup"><span data-stu-id="580a1-137">Dapper is an open-source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="580a1-138">Um Dapper zu verwenden, müssen Sie das Tool mithilfe des [Dapper-NuGet-Pakets](https://www.nuget.org/packages/Dapper) (s. Abbildung unten) installieren:</span><span class="sxs-lookup"><span data-stu-id="580a1-138">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure:</span></span>

![Screenshot des Dapper-Pakets in der NuGet-Paketeansicht.](./media/cqrs-microservice-reads/drapper-package-nuget.png)

<span data-ttu-id="580a1-140">Außerdem ist das Hinzufügen einer using-Anweisung erforderlich, damit der Code auf die Dapper-Erweiterungsmethoden zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="580a1-140">You also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="580a1-141">Wenn Sie Dapper in Ihrem Code verwenden, nutzen Sie direkt die <xref:System.Data.SqlClient.SqlConnection>-Klasse im <xref:System.Data.SqlClient>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="580a1-141">When you use Dapper in your code, you directly use the <xref:System.Data.SqlClient.SqlConnection> class available in the <xref:System.Data.SqlClient> namespace.</span></span> <span data-ttu-id="580a1-142">Über die QueryAsync-Methode und andere Erweiterungsmethoden, die die <xref:System.Data.SqlClient.SqlConnection>-Klasse erweitern, können Sie Abfragen leicht und schnell ausführen.</span><span class="sxs-lookup"><span data-stu-id="580a1-142">Through the QueryAsync method and other extension methods that extend the <xref:System.Data.SqlClient.SqlConnection> class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-versus-static-viewmodels"></a><span data-ttu-id="580a1-143">Dynamische und statische ViewModels im Vergleich</span><span class="sxs-lookup"><span data-stu-id="580a1-143">Dynamic versus static ViewModels</span></span>

<span data-ttu-id="580a1-144">ViewModels, die von serverseitigen Anwendungen an Client-Apps zurückgegeben werden, können als DTOs (Datentransferobjekte) betrachtet werden, die sich möglicherweise von den internen Domänenentitäten des Entitätsmodells unterscheiden, da ViewModels die für die Anwendung benötigten Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="580a1-144">When returning ViewModels from the server-side to client apps, you can think about those ViewModels as DTOs (Data Transfer Objects) that can be different to the internal domain entities of your entity model because the ViewModels hold the data the way the client app needs.</span></span> <span data-ttu-id="580a1-145">In vielen Fällen können Sie daher Daten aus unterschiedlichen Domänenentitäten aggregieren und die ViewModels so erstellen, dass die Datenanforderungen der Clientanwendung erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-145">Therefore, in many cases, you can aggregate data coming from multiple domain entities and compose the ViewModels precisely according to how the client app needs that data.</span></span>

<span data-ttu-id="580a1-146">Die ViewModels bzw. DTOs können explizit als Klassen zur Verwaltung von Daten definiert werden. Ein Beispiel dafür ist die `OrderSummary`-Klasse, die im Codeausschnitt unten gezeigt wird. Alternativ können Sie auch dynamische ViewModels oder DTOs basierend auf den von Ihren Abfragen zurückgegebenen Attributen als dynamischer Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="580a1-146">Those ViewModels or DTOs can be defined explicitly (as data holder classes) like the `OrderSummary` class shown in a later code snippet, or you could just return dynamic ViewModels or dynamic DTOs simply based on the attributes returned by your queries, as a dynamic type.</span></span>

### <a name="viewmodel-as-dynamic-type"></a><span data-ttu-id="580a1-147">ViewModel als dynamischer Typ</span><span class="sxs-lookup"><span data-stu-id="580a1-147">ViewModel as dynamic type</span></span>

<span data-ttu-id="580a1-148">Wie im folgenden Codeausschnitt gezeigt wird, kann ein `ViewModel` direkt von Abfragen zurückgegeben werden, indem ein *dynamischer* Typ zurückgegeben wird, der intern auf den Attributen basiert, die von einer Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-148">As shown in the following code, a `ViewModel` can be directly returned by the queries by just returning a *dynamic* type that internally is based on the attributes returned by a query.</span></span> <span data-ttu-id="580a1-149">Das bedeutet, dass die Teilmenge der Attribute, die zurückgegeben werden soll, auf der Abfrage selbst basiert.</span><span class="sxs-lookup"><span data-stu-id="580a1-149">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="580a1-150">Wenn Sie also der Abfrage oder der Verknüpfung eine neue Spalte hinzufügen, werden diese Daten dynamisch dem zurückgegebenen `ViewModel` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="580a1-150">Therefore, if you add a new column to the query or join, that data is dynamically added to the returned `ViewModel`.</span></span>

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

<span data-ttu-id="580a1-151">Zu beachten ist, dass durch die Verwendung eines dynamischen Typs die zurückgegebene Datensammlung dynamisch als ViewModel zusammengestellt wird. Diese Vorgehensweise bringt sowohl Vor- als auch Nachteile mit sich:</span><span class="sxs-lookup"><span data-stu-id="580a1-151">The important point is that by using a dynamic type, the returned collection of data is dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="580a1-152">**Vorteile:** Bei diesem Ansatz sind weniger Änderungen an statischen ViewModel-Klassen erforderlich, wenn die SQL-Anweisung einer Abfrage aktualisiert wird. Dies trägt zur Agilität und Einfachheit des Entwurfsansatzes bei und führt außerdem dazu, dass er bei zukünftig erforderlichen Änderungen schnell angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="580a1-152">**Pros:** This approach reduces the need to modify static ViewModel classes whenever you update the SQL sentence of a query, making this design approach pretty agile when coding, straightforward, and quick to evolve in regard to future changes.</span></span>

<span data-ttu-id="580a1-153">**Nachteile:** Dynamische Typen können sich langfristig negativ auf die Übersichtlichkeit und die Kompatibilität eines Diensts mit Client-Apps auswirken.</span><span class="sxs-lookup"><span data-stu-id="580a1-153">**Cons:** In the long term, dynamic types can negatively impact the clarity and the compatibility of a service with client apps.</span></span> <span data-ttu-id="580a1-154">Darüber hinaus stellt Middlewaresoftware wie Swashbuckle bei der Verwendung von dynamischen Typen nicht denselben Dokumentationsumfang für Rückgabetypen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="580a1-154">In addition, middleware software like Swashbuckle cannot provide the same level of documentation on returned types if using dynamic types.</span></span>

### <a name="viewmodel-as-predefined-dto-classes"></a><span data-ttu-id="580a1-155">ViewModel als vordefinierte DTO-Klasse</span><span class="sxs-lookup"><span data-stu-id="580a1-155">ViewModel as predefined DTO classes</span></span>

<span data-ttu-id="580a1-156">**Vorteile**: Vordefinierte statische ViewModel-Klassen wie „Verträge“, die auf expliziten DTO-Klassen beruhen, eignen sich insbesondere für öffentliche APIs. Ähnliches gilt auch für langfristige Microservices, und zwar auch dann, wenn diese nur für eine einzelne Anwendung eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-156">**Pros**: Having static predefined ViewModel classes, like “contracts” based on explicit DTO classes, is definitely better for public APIs but also for long term microservices, even if they are only used by the same application.</span></span>

<span data-ttu-id="580a1-157">Wenn Sie Antworttypen für Swagger festlegen möchten, müssen Sie explizite DTO-Klassen als Rückgabetyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="580a1-157">If you want to specify response types for Swagger, you need to use explicit DTO classes as the return type.</span></span> <span data-ttu-id="580a1-158">Mit vordefinierten DTO-Klassen können Sie daher mehr Informationen aus Swagger beziehen und anzeigen lassen.</span><span class="sxs-lookup"><span data-stu-id="580a1-158">Therefore, predefined DTO classes allow you to offer richer information from Swagger.</span></span> <span data-ttu-id="580a1-159">Dadurch werden die API-Dokumentation und die Kompatibilität bei der Nutzung der API verbessert.</span><span class="sxs-lookup"><span data-stu-id="580a1-159">That improves the API documentation and compatibility when consuming an API.</span></span>

<span data-ttu-id="580a1-160">**Nachteile**: Wie bereits erwähnt, sind für die Aktualisierung der DTO-Klassen mehrere Schritte erforderlich, sobald der Code geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="580a1-160">**Cons**: As mentioned earlier, when updating the code, it takes some more steps to update the DTO classes.</span></span>

<span data-ttu-id="580a1-161">*Autorentipp*: Wir haben in den Abfragen, die im Microservice für Bestellungen in eShopOnContainers implementiert wurden, zunächst dynamische ViewModels verwendet, da sich dieses Vorgehen in frühen Entwicklungsphasen als leicht und agil erwiesen hat.</span><span class="sxs-lookup"><span data-stu-id="580a1-161">*Tip based on our experience*: In the queries implemented at the Ordering microservice in eShopOnContainers, we started developing by using dynamic ViewModels as it was very straightforward and agile on the early development stages.</span></span> <span data-ttu-id="580a1-162">Sobald unser Code stabil war, haben wir die APIs umgestaltet und statische oder vordefinierte DTOs für die ViewModels verwendet, da es für die Consumer des Microservices leichter war, mit expliziten DTO-Typen umzugehen, die als Verträge genutzt wurden.</span><span class="sxs-lookup"><span data-stu-id="580a1-162">But, once the development was stabilized, we chose to refactor the APIs and use static or pre-defined DTOs for the ViewModels, because it is clearer for the microservice’s consumers to know explicit DTO types, used as "contracts".</span></span>

<span data-ttu-id="580a1-163">Im folgenden Beispiel wird gezeigt, wie die Abfrage Daten mithilfe der expliziten ViewModel-DTO-Klasse „OrderSummary“ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="580a1-163">In the following example, you can see how the query is returning data by using an explicit ViewModel DTO class: the OrderSummary class.</span></span>

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

#### <a name="describe-response-types-of-web-apis"></a><span data-ttu-id="580a1-164">Beschreiben von Web-API-Antworttypen</span><span class="sxs-lookup"><span data-stu-id="580a1-164">Describe response types of Web APIs</span></span>

<span data-ttu-id="580a1-165">Entwickler, die Web-APIs und Microservices nutzen, interessieren sich v.a. für die zurückgegebenen Antworttypen und Fehlercodes (wenn diese nicht den Standardwerten entsprechen).</span><span class="sxs-lookup"><span data-stu-id="580a1-165">Developers consuming web APIs and microservices are most concerned with what is returned — specifically response types and error codes (if not standard).</span></span> <span data-ttu-id="580a1-166">Diese werden in XML-Kommentaren und Datenanmerkungen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="580a1-166">These are handled in the XML comments and data annotations.</span></span>

<span data-ttu-id="580a1-167">Ohne eine geeignete Dokumentation auf der Swagger-Benutzeroberfläche weiß der Consumer nicht, welche Typen zurückgegeben werden oder welche HTTP-Statuscodes zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="580a1-167">Without proper documentation in the Swagger UI, the consumer lacks knowledge of what types are being returned or what HTTP codes can be returned.</span></span> <span data-ttu-id="580a1-168">Dieses Problem lässt sich durch Hinzufügen von <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType> beheben, wodurch Swashbuckle umfangreichere Informationen über das API-Rückgabemodell und die API-Rückgabewerte generiert. Dies wird im folgenden Codeausschnitt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="580a1-168">That problem is fixed by adding the <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, so Swashbuckle can generate richer information about the API return model and values, as shown in the following code:</span></span>

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

<span data-ttu-id="580a1-169">Das `ProducesResponseType`-Attribut kann allerdings keinen dynamischen Typ nutzen, sondern erfordert wie im folgenden Beispiel explizite Typen wie das `OrderSummary`-ViewModel-DTO:</span><span class="sxs-lookup"><span data-stu-id="580a1-169">However, the `ProducesResponseType` attribute cannot use dynamic as a type but requires to use explicit types, like the `OrderSummary` ViewModel DTO, shown in the following example:</span></span>

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

<span data-ttu-id="580a1-170">Dies ist ein weiterer Grund, weshalb explizite Rückgabetypen langfristig besser als dynamische Typen sind.</span><span class="sxs-lookup"><span data-stu-id="580a1-170">This is another reason why explicit returned types are better than dynamic types, in the long term.</span></span> <span data-ttu-id="580a1-171">Wenn Sie das `ProducesResponseType`-Attribut verwenden, können Sie auch erwartete HTTP-Fehler und Codes (z.B. 200, 400) festlegen.</span><span class="sxs-lookup"><span data-stu-id="580a1-171">When using the `ProducesResponseType` attribute, you can also specify what is the expected outcome in regards possible HTTP errors/codes, like 200, 400, etc.</span></span>

<span data-ttu-id="580a1-172">In der folgenden Abbildung wird gezeigt, wie ResponseType-Informationen auf der Swagger-Benutzeroberfläche dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="580a1-172">In the following image, you can see how Swagger UI shows the ResponseType information.</span></span>

![Screenshot der Swagger-Benutzeroberflächenseite für die Bestell-API.](./media/cqrs-microservice-reads/swagger-ordering-http-api.png)

<span data-ttu-id="580a1-174">**Abbildung 7-5**.</span><span class="sxs-lookup"><span data-stu-id="580a1-174">**Figure 7-5**.</span></span> <span data-ttu-id="580a1-175">Swagger-Benutzeroberfläche mit Antworttypen und möglichen HTTP-Statuscodes von einer Web-API</span><span class="sxs-lookup"><span data-stu-id="580a1-175">Swagger UI showing response types and possible HTTP status codes from a Web API</span></span>

<span data-ttu-id="580a1-176">In der Abbildung werden mehrere Beispielwerte, die auf den ViewModel-Typen basieren, und mögliche HTTP-Statuscodes angezeigt, die zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="580a1-176">You can see in the image above some example values based on the ViewModel types plus the possible HTTP status codes that can be returned.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="580a1-177">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="580a1-177">Additional resources</span></span>

- <span data-ttu-id="580a1-178">**Dapper**</span><span class="sxs-lookup"><span data-stu-id="580a1-178">**Dapper**</span></span>  
 <https://github.com/StackExchange/dapper-dot-net>

- <span data-ttu-id="580a1-179">**Julie Lerman. Datenpunkte – Dapper, Entity Framework und Hybrid-Apps (Artikel im MSDN Magazine)**</span><span class="sxs-lookup"><span data-stu-id="580a1-179">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN magazine article)**</span></span>  
  <https://docs.microsoft.com/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps>

- <span data-ttu-id="580a1-180">**ASP.NET Core-Web-API-Hilfeseiten mit Swagger**</span><span class="sxs-lookup"><span data-stu-id="580a1-180">**ASP.NET Core Web API Help Pages using Swagger**</span></span>  
  <https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio>

>[!div class="step-by-step"]
><span data-ttu-id="580a1-181">[Zurück](eshoponcontainers-cqrs-ddd-microservice.md)
>[Weiter](ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="580a1-181">[Previous](eshoponcontainers-cqrs-ddd-microservice.md)
[Next](ddd-oriented-microservice.md)</span></span>
