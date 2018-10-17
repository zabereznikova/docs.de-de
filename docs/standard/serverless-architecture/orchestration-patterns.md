---
title: Orchestrierung-Muster – serverlose apps
description: Azure Durable Functions pr
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 241eff4f30e63b2bb34664d6f783f854a000e7fd
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370057"
---
# <a name="orchestration-patterns"></a>Orchestrierung-Muster

Durable Functions erleichtert es, um zustandsbehaftete Workflows zu erstellen, die diskret, lang ausgeführte Aktivitäten in einer serverlosen Umgebung bestehen. Da die Durable Functions den Ausführungsverlauf in dem Status des Workflows und in regelmäßigen Abständen Prüfpunkte nachverfolgen können, gestattet es einige interessante Muster zu implementieren.

## <a name="function-chaining"></a>Funktionsverkettung

In einem typischen sequenziellen Prozess müssen Aktivitäten nacheinander in einer bestimmten Reihenfolge ausführen. Optional kann die nächsten Aktivität eine Ausgabe aus der vorherigen Funktion erfordern. Diese Abhängigkeit für die Reihenfolge der Aktivitäten wird eine Funktion-Kette der Ausführung erstellt.

Der Vorteil der Verwendung von Durable Functions zum Implementieren dieses Musters Workflow liegt in der Fähigkeit zum Setzen von Prüfpunkten zu tun. Wenn der Server abstürzt, können das Netzwerk ein Timeout auftritt oder ein andere Problem tritt auf, und Durable Functions vom letzten bekannten Zustand fortgesetzt weiterhin Ihr Workflow ausgeführt wird, auch wenn sie sich auf einem anderen Server befindet.

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<bool>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

Im vorherigen Codebeispiel das `CallActivityAsync` Funktion ist verantwortlich für die Ausführung einer bestimmten Aktivität auf einem virtuellen Computer im Rechenzentrum. Wenn die "await" zurückgibt und die zugrunde liegende Aufgabe abgeschlossen ist, wird die Ausführung in die Verlaufstabelle aufgezeichnet. Der Code in der orchestratorfunktion kann ist die vertraute Konstrukte der Task Parallel Library und die Schlüsselwörter "Async/await" verwenden.

Der folgende Code ist ein vereinfachtes Beispiel, was die `ProcessPayment` Methode kann wie folgt aussehen:

```csharp
[FunctionName("ProcessPayment")]
public static bool ProcessPayment([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    ApplyCoupons(orderData);
    if(IssuePaymentRequest(orderData)) {
        return true;
    }

    return false;
}
```

## <a name="asynchronous-http-apis"></a>Asynchrone HTTP-APIs

In einigen Fällen können Workflows, Aktivitäten enthalten, die relativ längere Zeit in Anspruch nehmen. Angenommen Sie, einen Prozess, der aus der Sicherung von Medien die Dateien in Blob Storage zum Einsatz kommt. Je nach Größe und Anzahl der Mediendateien kann dieser Sicherungsprozess Stunden dauern.

In diesem Szenario die `DurableOrchestrationClient`die Möglichkeit zum Überprüfen des Status eines ausgeführten Workflows ist nützlich. Bei Verwendung einer `HttpTrigger` zum Starten eines Workflows, die `CreateCheckStatusResponse` Methode kann verwendet werden, um eine Instanz des zurückzugeben `HttpResponseMessage`. Diese Antwort enthält den Client mit einem URI in der Nutzlast, die zum Überprüfen des Status des ausgeführten Prozesses verwendet werden kann.

```csharp
[FunctionName("OrderWorkflow")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient orchestrationClient)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

Das folgende Beispielergebnis zeigt die Struktur der antwortnutzlast an.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Mit Ihrem bevorzugten HTTP-Client, können GET-Anforderungen an den URI in StatusQueryGetUri vorgenommen werden, überprüfen den Status der ausgeführten Workflows. Die Antwort zurückgegebene Status sollte dem folgenden Code ähneln.

```json
{
    "runtimeStatus": "Running",
    "input": {
        "$type": "DurableFunctionsDemos.OrderRequestData, DurableFunctionsDemos"
    },
    "output": null,
    "createdTime": "2018-01-01T00:22:05Z",
    "lastUpdatedTime": "2018-01-01T00:22:09Z"
}
```

Wie der Prozess wird fortgesetzt, ändert sich die Statusantwort entweder **Fehler** oder **abgeschlossen**. Bei erfolgreichem Abschluss der **Ausgabe** Eigenschaft in der Nutzlast enthält alle zurückgegebenen Daten.

## <a name="monitoring"></a>Überwachung

Bei einfachen sich wiederholenden Aufgaben, die Azure Functions bietet die `TimerTrigger` , kann anhand eines CRON-Ausdrucks geplant werden. Der Zeitgeber eignet sich gut für einfache, kurz dauernden Aufgaben, doch in manchen Szenarien, in denen mehr flexible zeitplanung ist erforderlich. Dieses Szenario ist, wenn das Muster für Überwachung und Durable Functions profitieren können.

Durable Functions ermöglicht flexible zeitplanung Intervallen, Verwaltung der Lebensdauer und die Erstellung mehrerer Monitor-Prozesse aus einer einzigen Orchestrierung-Funktion. Ein Anwendungsfall für diese Funktionalität möglicherweise-Watcher für Änderungen der Aktienkurs zu erstellen, die abgeschlossen wird, wenn einen bestimmten Schwellenwert erreicht wurde.

```csharp
[FunctionName("CheckStockPrice")]
public static async Task CheckStockPrice([OrchestrationTrigger] DurableOrchestrationContext context)
{
    StockWatcherInfo stockInfo = context.GetInput<StockWatcherInfo>();
    const int checkIntervalSeconds = 120;
    StockPrice initialStockPrice = null;

    DateTime fireAt;
    DateTime exitTime = context.CurrentUtcDateTime.Add(stockInfo.TimeLimit);

    while (context.CurrentUtcDateTime < exitTime)
    {
        StockPrice currentStockPrice = await context.CallActivityAsync<StockPrice>("GetStockPrice", stockInfo);

        if (initialStockPrice == null)
        {
            initialStockPrice = currentStockPrice;
            fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
            await context.CreateTimer(fireAt, CancellationToken.None);
            continue;
        }

        decimal percentageChange = (initialStockPrice.Price - currentStockPrice.Price) /
                               ((initialStockPrice.Price + currentStockPrice.Price) / 2);

        if (Math.Abs(percentageChange) >= stockInfo.PercentageChange)
        {
            // Change threshold detected
            await context.CallActivityAsync("NotifyStockPercentageChange", currentStockPrice);
            break;
        }

        // Sleep til next polling interval
        fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
        await context.CreateTimer(fireAt, CancellationToken.None);
    }
}
```

`DurableOrchestrationContext`die `CreateTimer` Methode richtet den Zeitplan für den nächsten Aufruf der Schleife, um Aktienkurs Änderungen zu überprüfen. `DurableOrchestrationContext` verfügt auch über eine `CurrentUtcDateTime` Eigenschaft, um den aktuellen DateTime-Wert in UTC, abzurufen. Es ist besser, verwenden Sie diese Eigenschaft anstelle der `DateTime.UtcNow` , da es einfach zu Testzwecken simuliert wird.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [Azure Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Komponententests in .NET Core und .NET Standard](https://docs.microsoft.com/dotnet/core/testing/)

>[!div class="step-by-step"]
[Zurück](durable-azure-functions.md)
[Weiter](serverless-business-scenarios.md)
