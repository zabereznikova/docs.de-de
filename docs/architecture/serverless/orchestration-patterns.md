---
title: Orchestrierungs Muster-Server Lose apps
description: Azure Durable Functions-PR
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 18e13c5355490ef4a019ceda459114bdb6bfd539
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577403"
---
# <a name="orchestration-patterns"></a>Orchestrierungs Muster

Durable Functions erleichtert das Erstellen Zustands behafteter Workflows, die aus diskreten, lang andauernden Aktivitäten in einer Server losen Umgebung bestehen. Da Durable Functions den Fortschritt Ihrer Workflows verfolgen und den Ausführungs Verlauf in regelmäßigen Abständen prüfen kann, eignet er sich für die Implementierung einiger interessanter Muster.

## <a name="function-chaining"></a>Funktions Verkettung

In einem typischen sequenziellen Prozess müssen Aktivitäten nacheinander in einer bestimmten Reihenfolge ausgeführt werden. Optional ist für die bevorstehende Aktivität möglicherweise eine Ausgabe der vorherigen Funktion erforderlich. Diese Abhängigkeit von der Reihenfolge der Aktivitäten erstellt eine funktionskette der Ausführung.

Der Vorteil der Verwendung von Durable Functions, um dieses Workflow Muster zu implementieren, ist von der Fähigkeit, auf Prüfpunkte zu verweisen. Wenn der Server abstürzt, das Netzwerk ausfällt oder ein anderes Problem auftritt, können Durable Functions vom letzten bekannten Zustand fortgesetzt werden und den Workflow weiterhin ausführen, auch wenn er auf einem anderen Server ausgeführt wird.

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

Im vorangehenden Codebeispiel ist die `CallActivityAsync` Funktion für die Ausführung einer bestimmten Aktivität auf einem virtuellen Computer im Rechenzentrum verantwortlich. Wenn die Erwartung zurückkehrt und die zugrunde liegende Aufgabe abgeschlossen ist, wird die Ausführung in der Verlaufs Tabelle aufgezeichnet. Der Code in der orchestratorfunktion kann alle vertrauten Konstrukte der Task Parallel Library und der Schlüsselwörter "Async/erwartungsgemäß" nutzen.

Der folgende Code ist ein vereinfachtes Beispiel dafür, `ProcessPayment` wie die Methode aussehen könnte:

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

In einigen Fällen können Workflows Aktivitäten enthalten, die eine relativ lange Zeit in Anspruch nehmen. Stellen Sie sich einen Prozess vor, bei dem die Sicherung von Mediendateien in BLOB Storage gestartet wird. Abhängig von der Größe und Menge der Mediendateien kann dieser Sicherungs Vorgang einige Stunden in Anspruch nehmen.

In diesem Szenario ist `DurableOrchestrationClient`es sinnvoll, den Status eines laufenden Workflows zu überprüfen. Wenn Sie einen `HttpTrigger` Workflow mit einem starten, kann `CreateCheckStatusResponse` die-Methode verwendet werden, um eine Instanz `HttpResponseMessage`von zurückzugeben. Diese Antwort stellt dem Client einen URI in der Nutzlast zur Verfügung, der zum Überprüfen des Status des laufenden Prozesses verwendet werden kann.

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

Das folgende Beispiel Ergebnis zeigt die Struktur der Antwort Nutzlast.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Mithilfe Ihres bevorzugten HTTP-Clients können Get-Anforderungen an den URI in statusquerygeturi erfolgen, um den Status des laufenden Workflows zu überprüfen. Die zurückgegebene Status Antwort sollte dem folgenden Code ähneln.

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

Wenn der Prozess fortgesetzt wird, ändert sich die Status Antwort entweder in " **failed** " oder " **abgeschlossen**". Nach erfolgreichem Abschluss enthält die **Output** -Eigenschaft in der Nutzlast alle zurückgegebenen Daten.

## <a name="monitoring"></a>Überwachung

Für einfache wiederkehrende Aufgaben stellt Azure Functions den `TimerTrigger` bereit, der basierend auf einem Cron-Ausdruck geplant werden kann. Der Timer eignet sich gut für einfache, kurzlebige Aufgaben, aber es kann Szenarien geben, in denen eine flexiblere Planung erforderlich ist. Dieses Szenario ist der Fall, wenn das Überwachungs Muster und der Durable Functions helfen können.

Durable Functions ermöglicht flexible Planungs Intervalle, Lebensdauer Verwaltung und die Erstellung mehrerer Monitor Prozesse aus einer einzelnen Orchestrierungs Funktion. Ein Anwendungsfall für diese Funktionalität ist das Erstellen von Überwachungen für Aktienpreis Änderungen, die durchgeführt werden, sobald ein bestimmter Schwellenwert erreicht wird.

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

`DurableOrchestrationContext`die `CreateTimer` -Methode richtet den Zeitplan für den nächsten Aufruf der Schleife ein, um auf Aktienkurs Änderungen zu überprüfen. `DurableOrchestrationContext`verfügt auch über `CurrentUtcDateTime` eine-Eigenschaft, um den aktuellen DateTime-Wert in UTC zu erhalten. Es ist besser, diese Eigenschaft anstelle von `DateTime.UtcNow` zu verwenden, da Sie leicht zu Testzwecken verspottet wird.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [Azure-Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Komponententests in .NET Core und .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Zurück](durable-azure-functions.md)
>[Weiter](serverless-business-scenarios.md)
