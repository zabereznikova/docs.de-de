---
title: 'Orchestrierungsmuster: Serverlose Apps'
description: Azure Durable Functions
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522637"
---
# <a name="orchestration-patterns"></a>Orchestrierungsmuster

Durable Functions erleichtert das Erstellen zustandsbehafteter Workflows, die aus diskreten, zeitintensiven Aktivitäten in einer serverlosen Umgebung bestehen. Da Durable Functions den Fortschritt Ihrer Workflows nachverfolgen und den Ausführungsverlauf in regelmäßigen Abständen prüfen kann, ist die Anwendung für die Implementierung einiger interessanter Muster geeignet.

## <a name="function-chaining"></a>Funktionsverkettung

In einem typischen sequenziellen Prozess müssen Aktivitäten nacheinander in einer bestimmten Reihenfolge ausgeführt werden. Optional ist für die bevorstehende Aktivität möglicherweise eine Ausgabe der vorherigen Funktion erforderlich. Diese Abhängigkeit von der Reihenfolge der Aktivitäten erstellt eine Funktionskette der Ausführung.

Der Vorteil der Verwendung von Durable Functions, um dieses Workflowmuster zu implementieren, liegt in der Fähigkeit, Prüfpunkte zu verwenden. Wenn der Server abstürzt, ein Timeout des Netzwerks oder ein anderes Problem auftritt, kann Durable Functions vom letzten bekannten Zustand fortgesetzt werden und den Workflow weiterhin ausführen, selbst auf einem anderen Server.

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

Im vorherigen Codebeispiel ist die `CallActivityAsync`-Funktion für die Ausführung einer bestimmten Aktivität auf einem virtuellen Computer im Rechenzentrum verantwortlich. Nach Rückgabe von await und Abschluss des zugrunde liegenden Tasks wird die Ausführung in der Verlaufstabelle aufgezeichnet. Der Code in der Orchestratorfunktion kann alle vertrauten Konstrukte der Task Parallel Library (TPL) und die Schlüsselwörter async/await nutzen.

Der folgende Code ist ein vereinfachtes Beispiel dafür, wie die `ProcessPayment`-Methode aussehen könnte:

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

In einigen Fällen können Workflows Aktivitäten enthalten, deren Abschluss eine relativ lange Zeit in Anspruch nimmt. Stellen Sie sich einen Prozess vor, bei dem die Sicherung von Mediendateien in Blobspeicher gestartet wird. Abhängig von der Größe und Menge der Mediendateien kann dieser Sicherungsprozess Stunden in Anspruch nehmen.

In diesem Szenario ist die Fähigkeit von `DurableOrchestrationClient` nützlich, den Status eines ausgeführten Workflows zu überprüfen. Wenn Sie einen `HttpTrigger` zum Starten eines Workflows verwenden, kann die `CreateCheckStatusResponse`-Methode verwendet werden, um eine Instanz von `HttpResponseMessage` zurückzugeben. Diese Antwort stellt dem Client in der Nutzlast einen URI zur Verfügung, der zum Überprüfen des Status des aktiven Prozesses verwendet werden kann.

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

Das folgende Beispielergebnis zeigt die Struktur der Antwortnutzlast.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Mithilfe Ihres bevorzugten HTTP-Clients können GET-Anforderungen an den URI in StatusQueryGetUri erfolgen, um den Status des aktiven Workflows zu überprüfen. Die zurückgegebene Statusantwort sollte dem folgenden Code ähneln.

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

Während der Prozess fortgesetzt wird, ändert sich die Statusantwort entweder in **Failed** (Fehler) oder **Completed** (Abgeschlossen). Nach erfolgreichem Abschluss enthält die **output**-Eigenschaft in der Nutzlast alle zurückgegebenen Daten.

## <a name="monitoring"></a>Überwachung

Für einfache periodische Vorgänge stellt Azure Functions den `TimerTrigger` bereit, der basierend auf einem CRON-Ausdruck geplant werden kann. Der Timer eignet sich gut für einfache, kurzlebige Tasks, aber es kann Szenarien geben, in denen eine flexiblere Planung erforderlich ist. Dieses Szenario ist dann der Fall, wenn das Überwachungsmuster und Durable Functions helfen können.

Durable Functions ermöglicht flexible Planungsintervalle, Lebensdauerverwaltung und die Erstellung mehrerer Überwachungsprozesse aus einer einzigen Orchestrierungsfunktion. Ein Anwendungsfall für diese Funktionalität könnte darin bestehen, Beobachter für Aktienkursänderungen zu erstellen, die bei Erreichen eines bestimmten Schwellenwerts abgeschlossen werden.

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

Die `CreateTimer`-Methode von `DurableOrchestrationContext` richtet den Zeitplan für den nächsten Aufruf der Schleife ein, um auf Aktienkursänderungen zu prüfen. `DurableOrchestrationContext` verfügt auch über eine `CurrentUtcDateTime`-Eigenschaft, um den aktuellen DateTime-Wert in UTC abzurufen. Es ist besser, diese Eigenschaft anstelle von `DateTime.UtcNow` zu verwenden, da sie leicht zu Testzwecken simuliert werden kann.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

- [Azure Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Komponententests in .NET Core und .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Zurück](durable-azure-functions.md)
>[Weiter](serverless-business-scenarios.md)
