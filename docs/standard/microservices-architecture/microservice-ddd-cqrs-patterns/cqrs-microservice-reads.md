---
title: Implementieren von Lese-/Abfragen in einer CQRS microservice
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren von Lese-/Abfragen in einer CQRS microservice"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e017aaaa701d8033110be8d6244d3e1120fc4fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="1a808-104">Implementieren von Lese-/Abfragen in einer CQRS microservice</span><span class="sxs-lookup"><span data-stu-id="1a808-104">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="1a808-105">Für Lesevorgänge/Abfragen implementiert die Sortierung Microservice aus der eShopOnContainers Verweis Anwendung Abfragen unabhängig von der DDD Modell und der transaktionalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="1a808-105">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="1a808-106">Dies wurde in erster Linie verwendet werden, da die Anforderungen für Abfragen und Transaktionen erheblich unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1a808-106">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="1a808-107">Schreibvorgänge ausgeführt werden Transaktionen, die mit der Domänenlogik kompatibel sein müssen.</span><span class="sxs-lookup"><span data-stu-id="1a808-107">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="1a808-108">Abfragen, andererseits, Idempotent sind und von den Domänenregeln getrennt werden können.</span><span class="sxs-lookup"><span data-stu-id="1a808-108">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="1a808-109">Der Ansatz ist einfach, wie in Abbildung 9 – 3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1a808-109">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="1a808-110">Die API-Schnittstelle wird von der Web-API-Controller Infrastruktur (z. B. eine Micro-ORM, wie dapper, durch) und Zurückgeben von dynamischen ViewModels je nach den Anforderungen der Benutzeroberflächen-Anwendungen implementiert.</span><span class="sxs-lookup"><span data-stu-id="1a808-110">The API interface is implemented by the Web API controllers using any infrastructure (such as a micro ORM like Dapper) and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="1a808-111">**Abbildung 9 – 3**.</span><span class="sxs-lookup"><span data-stu-id="1a808-111">**Figure 9-3**.</span></span> <span data-ttu-id="1a808-112">Der einfachste Ansatz für die Abfragen in einem CQRS microservice</span><span class="sxs-lookup"><span data-stu-id="1a808-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="1a808-113">Dies ist die einfachste mögliche Vorgehensweise für Abfragen.</span><span class="sxs-lookup"><span data-stu-id="1a808-113">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="1a808-114">Die Abfragedefinitionen die Datenbank abzufragen und eine dynamische ViewModel erstellt bei Bedarf für jede Abfrage zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1a808-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="1a808-115">Da Abfragen Idempotent sind, werden sie die Daten unabhängig davon, wie oft die Ausführung einer Abfrage nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1a808-115">Since the queries are idempotent, they will not change the data no matter how many times you run a query.</span></span> <span data-ttu-id="1a808-116">Daher müssen Sie nicht durch alle DDD-Muster verwendet wird, in der Transaktions-Seite, wie Aggregaten und anderen Mustern enthalten und eingeschränkt werden, und aus diesem Grund Abfragen voneinander getrennt sind, aus dem Bereich transaktional ist.</span><span class="sxs-lookup"><span data-stu-id="1a808-116">Therefore, you do not need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="1a808-117">Klicken Sie einfach Abfragen die Datenbank für die Daten, die die Benutzeroberfläche und zurückzugeben, dass eine dynamische ViewModel, die nicht statisch sein muss anywhere (keine Klassen für die ViewModels) außer in der SQL-Anweisung selbst definiert.</span><span class="sxs-lookup"><span data-stu-id="1a808-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="1a808-118">Da dies ein einfacher Ansatz ist, wird der Code für die Seite Abfragen erforderlich (z. B. Code mit einem Micro ORM wie [dapper, durch](https://github.com/StackExchange/Dapper)) implementiert werden können [innerhalb desselben Projekts Web-API](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="1a808-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="1a808-119">Abbildung 9 – 4 wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a808-119">Figure 9-4 shows this.</span></span> <span data-ttu-id="1a808-120">Die Abfragen werden definiert, der **Ordering.API** Microservice Projekt innerhalb der Projektmappe eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="1a808-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="1a808-121">**Abbildung 9 – 4**.</span><span class="sxs-lookup"><span data-stu-id="1a808-121">**Figure 9-4**.</span></span> <span data-ttu-id="1a808-122">Abfragen in der Reihenfolge Microservice in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="1a808-122">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="1a808-123">Mithilfe von ViewModels speziell für Client-apps, unabhängig von der Domäne Modell Einschränkungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="1a808-123">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="1a808-124">Da die Abfragen, zum Abrufen der Daten, die von den Clientanwendungen erforderlich sind ausgeführt werden, kann der zurückgegebene Typ speziell für die Clients, die basierend auf den von den Abfragen zurückgegebenen Daten vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="1a808-124">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="1a808-125">Diese Modelle oder Daten-Objekte übertragen (DTOs), werden ViewModels aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1a808-125">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="1a808-126">Die zurückgegebenen Daten (ViewModel) können das Ergebnis der zu verknüpfenden Daten aus mehreren Entitäten oder Tabellen in der Datenbank oder sogar über mehrere Aggregate im Domänenmodell zum Bereich "transaktional" definiert sein.</span><span class="sxs-lookup"><span data-stu-id="1a808-126">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="1a808-127">In diesem Fall werden, da Sie Abfragen unabhängig von der Domänenmodell erstellen, die Aggregate-Grenzen und Einschränkungen werden vollständig ignoriert, und Sie sind frei, um alle Tabellen und Spalten, die Sie möglicherweise Abfragen.</span><span class="sxs-lookup"><span data-stu-id="1a808-127">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you are free to query any table and column you might need.</span></span> <span data-ttu-id="1a808-128">Dieser Ansatz bietet maximale Flexibilität beim und Produktivität für den Entwickler erstellen oder aktualisieren die Abfragen.</span><span class="sxs-lookup"><span data-stu-id="1a808-128">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="1a808-129">Die ViewModels können statische Typen in Klassen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a808-129">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="1a808-130">Oder sie können erstellt werden dynamisch basierend auf den Abfragen ausgeführt (wie in der Reihenfolge Microservice implementiert ist), ist sehr flexible für Entwickler.</span><span class="sxs-lookup"><span data-stu-id="1a808-130">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="1a808-131">Verwenden dapper, durch als eine micro-ORM, zum Ausführen von Abfragen</span><span class="sxs-lookup"><span data-stu-id="1a808-131">Using Dapper as a micro ORM to perform queries</span></span> 

<span data-ttu-id="1a808-132">Sie können alle micro-ORM, Entity Framework Core oder sogar plain ADO.NET für Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a808-132">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="1a808-133">In der beispielanwendung wir dapper, durch ausgewählt, für die Sortierung Microservice in eShopOnContainers als ein gutes Beispiel für eine beliebte micro-ORM.</span><span class="sxs-lookup"><span data-stu-id="1a808-133">In the sample application, we selected Dapper for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="1a808-134">Sie können einfache SQL-Abfragen mit hervorragende Leistung, ausführen, da es sich um eine sehr einfache Framework handelt.</span><span class="sxs-lookup"><span data-stu-id="1a808-134">It can run plain SQL queries with great performance, because it is a very light framework.</span></span> <span data-ttu-id="1a808-135">Dapper, durch verwenden, können Sie eine SQL-Abfrage schreiben, die Zugriff auf und mehrere Tabellen verknüpfen können.</span><span class="sxs-lookup"><span data-stu-id="1a808-135">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="1a808-136">Dapper, durch ist ein open-Source-Projekt (Original erstellt Sam Saffron) und ist Teil der Bausteine in verwendet [Stack Overflow](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="1a808-136">Dapper is an open source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="1a808-137">Um dapper, durch verwenden zu können, müssen Sie nur durch Installieren der [Dapper NuGet-Paket](https://www.nuget.org/packages/Dapper), wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1a808-137">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure.</span></span>

![](./media/image5.png)

<span data-ttu-id="1a808-138">Sie müssen auch eine using hinzufügen Anweisung, sodass der Code den Zugriff auf die Dapper Erweiterungsmethoden hat.</span><span class="sxs-lookup"><span data-stu-id="1a808-138">You will also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="1a808-139">Wenn Sie dapper, durch in Ihrem Code verwenden, verwenden Sie direkt die SqlClient-Klasse, die in den System.Data.SqlClient-Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1a808-139">When you use Dapper in your code, you directly use the SqlClient class available in the System.Data.SqlClient namespace.</span></span> <span data-ttu-id="1a808-140">Über die QueryAsync-Methode und andere Erweiterungsmethoden, die die SqlClient-Klasse erweitern, können Sie einfach in eine einfache und leistungsstarke Möglichkeit Abfragen ausführen.</span><span class="sxs-lookup"><span data-stu-id="1a808-140">Through the QueryAsync method and other extension methods which extend the SqlClient class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-and-static-viewmodels"></a><span data-ttu-id="1a808-141">Dynamische und statische ViewModels</span><span class="sxs-lookup"><span data-stu-id="1a808-141">Dynamic and static ViewModels</span></span>

<span data-ttu-id="1a808-142">Wie im folgenden Code aus der Sortierung Microservice gezeigt, werden die meisten der von Abfragen zurückgegebene ViewModels als implementiert *dynamische*.</span><span class="sxs-lookup"><span data-stu-id="1a808-142">As shown in the following code from the ordering microservice, most of the ViewModels returned by the queries are implemented as *dynamic*.</span></span> <span data-ttu-id="1a808-143">Das bedeutet, dass die Teilmenge der Attribute, die zurückgegeben wird, werden auf der Abfrage selbst basiert.</span><span class="sxs-lookup"><span data-stu-id="1a808-143">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="1a808-144">Wenn Sie eine neue Spalte an der Abfrage oder der Join hinzufügen, werden diese Daten zurückgegebenen ViewModel dynamisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a808-144">If you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span> <span data-ttu-id="1a808-145">Dieser Ansatz reduziert die Notwendigkeit zum Ändern von Abfragen in Reaktion auf Updates für das zugrunde liegende Datenmodell, wodurch dieser Entwurfsansatz, flexibler und fehlertolerante zukünftige Änderungen.</span><span class="sxs-lookup"><span data-stu-id="1a808-145">This approach reduces the need to modify queries in response to updates to the underlying data model, making this design approach more flexible and tolerant of future changes.</span></span>

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

<span data-ttu-id="1a808-146">Der wichtige Punkt ist, dass die zurückgegebene Auflistung von Daten mithilfe eines dynamischen Typs dynamisch als ViewModel zusammengestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a808-146">The important point is that by using a dynamic type, the returned collection of data will be dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="1a808-147">Bei den meisten Abfragen müssen keine Klasse DTO oder ViewModel vordefinieren, wodurch das Codieren sie einfacher und produktiver.</span><span class="sxs-lookup"><span data-stu-id="1a808-147">For most queries, you do not need to predefine a DTO or ViewModel class, which makes coding them straightforward and productive.</span></span> <span data-ttu-id="1a808-148">Sie können jedoch ViewModels (z. B. vordefinierte DTOs) vordefinieren, wenn ViewModels mit einem eingeschränkteren Definition als Verträge sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1a808-148">However, you can predefine ViewModels (like predefined DTOs) if you want to have ViewModels with a more restricted definition as contracts.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="1a808-149">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1a808-149">Additional resources</span></span>

-   <span data-ttu-id="1a808-150">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="1a808-150">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="1a808-151">**Julie Lerman. Datenpunkte - Dapper, Entity Framework und Hybrid-Apps (Mag. MSDN-Artikel)**</span><span class="sxs-lookup"><span data-stu-id="1a808-151">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    <span data-ttu-id="1a808-152">*https://msdn.Microsoft.com/en-US/Magazine/mt703432.aspx*</span><span class="sxs-lookup"><span data-stu-id="1a808-152">*https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="1a808-153">[Vorherigen] (Eshoponcontainers-Cqrs-Ddd-microservice.md) [weiter] (Ddd-orientierte-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="1a808-153">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
