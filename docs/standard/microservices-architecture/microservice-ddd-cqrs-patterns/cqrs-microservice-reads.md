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
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a>Implementieren von Lese-/Abfragen in einer CQRS microservice

Für Lesevorgänge/Abfragen implementiert die Sortierung Microservice aus der eShopOnContainers Verweis Anwendung Abfragen unabhängig von der DDD Modell und der transaktionalen Bereich. Dies wurde in erster Linie verwendet werden, da die Anforderungen für Abfragen und Transaktionen erheblich unterscheiden. Schreibvorgänge ausgeführt werden Transaktionen, die mit der Domänenlogik kompatibel sein müssen. Abfragen, andererseits, Idempotent sind und von den Domänenregeln getrennt werden können.

Der Ansatz ist einfach, wie in Abbildung 9 – 3 dargestellt. Die API-Schnittstelle wird von der Web-API-Controller Infrastruktur (z. B. eine Micro-ORM, wie dapper, durch) und Zurückgeben von dynamischen ViewModels je nach den Anforderungen der Benutzeroberflächen-Anwendungen implementiert.

![](./media/image3.png)

**Abbildung 9 – 3**. Der einfachste Ansatz für die Abfragen in einem CQRS microservice

Dies ist die einfachste mögliche Vorgehensweise für Abfragen. Die Abfragedefinitionen die Datenbank abzufragen und eine dynamische ViewModel erstellt bei Bedarf für jede Abfrage zurückzugeben. Da Abfragen Idempotent sind, werden sie die Daten unabhängig davon, wie oft die Ausführung einer Abfrage nicht ändern. Daher müssen Sie nicht durch alle DDD-Muster verwendet wird, in der Transaktions-Seite, wie Aggregaten und anderen Mustern enthalten und eingeschränkt werden, und aus diesem Grund Abfragen voneinander getrennt sind, aus dem Bereich transaktional ist. Klicken Sie einfach Abfragen die Datenbank für die Daten, die die Benutzeroberfläche und zurückzugeben, dass eine dynamische ViewModel, die nicht statisch sein muss anywhere (keine Klassen für die ViewModels) außer in der SQL-Anweisung selbst definiert.

Da dies ein einfacher Ansatz ist, wird der Code für die Seite Abfragen erforderlich (z. B. Code mit einem Micro ORM wie [dapper, durch](https://github.com/StackExchange/Dapper)) implementiert werden können [innerhalb desselben Projekts Web-API](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs). Abbildung 9 – 4 wird angezeigt. Die Abfragen werden definiert, der **Ordering.API** Microservice Projekt innerhalb der Projektmappe eShopOnContainers.

![](./media/image4.png)

**Abbildung 9 – 4**. Abfragen in der Reihenfolge Microservice in eShopOnContainers

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Mithilfe von ViewModels speziell für Client-apps, unabhängig von der Domäne Modell Einschränkungen vorgenommen.

Da die Abfragen, zum Abrufen der Daten, die von den Clientanwendungen erforderlich sind ausgeführt werden, kann der zurückgegebene Typ speziell für die Clients, die basierend auf den von den Abfragen zurückgegebenen Daten vorgenommen werden. Diese Modelle oder Daten-Objekte übertragen (DTOs), werden ViewModels aufgerufen.

Die zurückgegebenen Daten (ViewModel) können das Ergebnis der zu verknüpfenden Daten aus mehreren Entitäten oder Tabellen in der Datenbank oder sogar über mehrere Aggregate im Domänenmodell zum Bereich "transaktional" definiert sein. In diesem Fall werden, da Sie Abfragen unabhängig von der Domänenmodell erstellen, die Aggregate-Grenzen und Einschränkungen werden vollständig ignoriert, und Sie sind frei, um alle Tabellen und Spalten, die Sie möglicherweise Abfragen. Dieser Ansatz bietet maximale Flexibilität beim und Produktivität für den Entwickler erstellen oder aktualisieren die Abfragen.

Die ViewModels können statische Typen in Klassen definiert werden. Oder sie können erstellt werden dynamisch basierend auf den Abfragen ausgeführt (wie in der Reihenfolge Microservice implementiert ist), ist sehr flexible für Entwickler.

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a>Verwenden dapper, durch als eine micro-ORM, zum Ausführen von Abfragen 

Sie können alle micro-ORM, Entity Framework Core oder sogar plain ADO.NET für Abfragen verwenden. In der beispielanwendung wir dapper, durch ausgewählt, für die Sortierung Microservice in eShopOnContainers als ein gutes Beispiel für eine beliebte micro-ORM. Sie können einfache SQL-Abfragen mit hervorragende Leistung, ausführen, da es sich um eine sehr einfache Framework handelt. Dapper, durch verwenden, können Sie eine SQL-Abfrage schreiben, die Zugriff auf und mehrere Tabellen verknüpfen können.

Dapper, durch ist ein open-Source-Projekt (Original erstellt Sam Saffron) und ist Teil der Bausteine in verwendet [Stack Overflow](https://stackoverflow.com/). Um dapper, durch verwenden zu können, müssen Sie nur durch Installieren der [Dapper NuGet-Paket](https://www.nuget.org/packages/Dapper), wie in der folgenden Abbildung dargestellt.

![](./media/image5.png)

Sie müssen auch eine using hinzufügen Anweisung, sodass der Code den Zugriff auf die Dapper Erweiterungsmethoden hat.

Wenn Sie dapper, durch in Ihrem Code verwenden, verwenden Sie direkt die SqlClient-Klasse, die in den System.Data.SqlClient-Namespace verfügbar. Über die QueryAsync-Methode und andere Erweiterungsmethoden, die die SqlClient-Klasse erweitern, können Sie einfach in eine einfache und leistungsstarke Möglichkeit Abfragen ausführen.

## <a name="dynamic-and-static-viewmodels"></a>Dynamische und statische ViewModels

Wie im folgenden Code aus der Sortierung Microservice gezeigt, werden die meisten der von Abfragen zurückgegebene ViewModels als implementiert *dynamische*. Das bedeutet, dass die Teilmenge der Attribute, die zurückgegeben wird, werden auf der Abfrage selbst basiert. Wenn Sie eine neue Spalte an der Abfrage oder der Join hinzufügen, werden diese Daten zurückgegebenen ViewModel dynamisch hinzugefügt. Dieser Ansatz reduziert die Notwendigkeit zum Ändern von Abfragen in Reaktion auf Updates für das zugrunde liegende Datenmodell, wodurch dieser Entwurfsansatz, flexibler und fehlertolerante zukünftige Änderungen.

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

Der wichtige Punkt ist, dass die zurückgegebene Auflistung von Daten mithilfe eines dynamischen Typs dynamisch als ViewModel zusammengestellt werden soll.

Bei den meisten Abfragen müssen keine Klasse DTO oder ViewModel vordefinieren, wodurch das Codieren sie einfacher und produktiver. Sie können jedoch ViewModels (z. B. vordefinierte DTOs) vordefinieren, wenn ViewModels mit einem eingeschränkteren Definition als Verträge sein sollen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)

-   **Julie Lerman. Datenpunkte - Dapper, Entity Framework und Hybrid-Apps (Mag. MSDN-Artikel)**

    *https://msdn.Microsoft.com/en-US/Magazine/mt703432.aspx*


>[!div class="step-by-step"]
[Vorherigen] (Eshoponcontainers-Cqrs-Ddd-microservice.md) [weiter] (Ddd-orientierte-microservice.md)
