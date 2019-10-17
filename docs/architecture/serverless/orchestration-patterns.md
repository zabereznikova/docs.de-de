---
title: Orchestrierungs Muster-Server Lose apps
description: Azure Durable Functions-PR
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522637"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="ff64e-103">Orchestrierungs Muster</span><span class="sxs-lookup"><span data-stu-id="ff64e-103">Orchestration patterns</span></span>

<span data-ttu-id="ff64e-104">Durable Functions erleichtert das Erstellen Zustands behafteter Workflows, die aus diskreten, lang andauernden Aktivitäten in einer Server losen Umgebung bestehen.</span><span class="sxs-lookup"><span data-stu-id="ff64e-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="ff64e-105">Da Durable Functions den Fortschritt Ihrer Workflows verfolgen und den Ausführungs Verlauf in regelmäßigen Abständen prüfen kann, eignet er sich für die Implementierung einiger interessanter Muster.</span><span class="sxs-lookup"><span data-stu-id="ff64e-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="ff64e-106">Funktions Verkettung</span><span class="sxs-lookup"><span data-stu-id="ff64e-106">Function chaining</span></span>

<span data-ttu-id="ff64e-107">In einem typischen sequenziellen Prozess müssen Aktivitäten nacheinander in einer bestimmten Reihenfolge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ff64e-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="ff64e-108">Optional ist für die bevorstehende Aktivität möglicherweise eine Ausgabe der vorherigen Funktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff64e-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="ff64e-109">Diese Abhängigkeit von der Reihenfolge der Aktivitäten erstellt eine funktionskette der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ff64e-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="ff64e-110">Der Vorteil der Verwendung von Durable Functions, um dieses Workflow Muster zu implementieren, ist von der Fähigkeit, auf Prüfpunkte zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="ff64e-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="ff64e-111">Wenn der Server abstürzt, das Netzwerk ausfällt oder ein anderes Problem auftritt, können Durable Functions vom letzten bekannten Zustand fortgesetzt werden und den Workflow weiterhin ausführen, auch wenn er auf einem anderen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff64e-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="ff64e-112">Im vorangehenden Codebeispiel ist die Funktion "`CallActivityAsync`" für die Ausführung einer bestimmten Aktivität auf einem virtuellen Computer im Rechenzentrum verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="ff64e-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="ff64e-113">Wenn die Erwartung zurückkehrt und die zugrunde liegende Aufgabe abgeschlossen ist, wird die Ausführung in der Verlaufs Tabelle aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ff64e-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="ff64e-114">Der Code in der orchestratorfunktion kann alle vertrauten Konstrukte der Task Parallel Library und der Schlüsselwörter "Async/erwartungsgemäß" nutzen.</span><span class="sxs-lookup"><span data-stu-id="ff64e-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="ff64e-115">Der folgende Code ist ein vereinfachtes Beispiel dafür, wie die `ProcessPayment`-Methode aussehen könnte:</span><span class="sxs-lookup"><span data-stu-id="ff64e-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="ff64e-116">Asynchrone HTTP-APIs</span><span class="sxs-lookup"><span data-stu-id="ff64e-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="ff64e-117">In einigen Fällen können Workflows Aktivitäten enthalten, die eine relativ lange Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ff64e-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="ff64e-118">Stellen Sie sich einen Prozess vor, bei dem die Sicherung von Mediendateien in BLOB Storage gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ff64e-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="ff64e-119">Abhängig von der Größe und Menge der Mediendateien kann dieser Sicherungs Vorgang einige Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ff64e-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="ff64e-120">In diesem Szenario ist die `DurableOrchestrationClient`-Fähigkeit, den Status eines laufenden Workflows zu überprüfen, hilfreich.</span><span class="sxs-lookup"><span data-stu-id="ff64e-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="ff64e-121">Wenn Sie mit einem `HttpTrigger` einen Workflow starten, kann die `CreateCheckStatusResponse`-Methode verwendet werden, um eine Instanz von `HttpResponseMessage` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff64e-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="ff64e-122">Diese Antwort stellt dem Client einen URI in der Nutzlast zur Verfügung, der zum Überprüfen des Status des laufenden Prozesses verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff64e-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="ff64e-123">Das folgende Beispiel Ergebnis zeigt die Struktur der Antwort Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="ff64e-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="ff64e-124">Mithilfe Ihres bevorzugten HTTP-Clients können Get-Anforderungen an den URI in statusquerygeturi erfolgen, um den Status des laufenden Workflows zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ff64e-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="ff64e-125">Die zurückgegebene Status Antwort sollte dem folgenden Code ähneln.</span><span class="sxs-lookup"><span data-stu-id="ff64e-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="ff64e-126">Wenn der Prozess fortgesetzt wird, ändert sich die Status Antwort entweder in " **failed** " oder " **abgeschlossen**".</span><span class="sxs-lookup"><span data-stu-id="ff64e-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="ff64e-127">Nach erfolgreichem Abschluss enthält die **Output** -Eigenschaft in der Nutzlast alle zurückgegebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="ff64e-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="ff64e-128">Überwachung</span><span class="sxs-lookup"><span data-stu-id="ff64e-128">Monitoring</span></span>

<span data-ttu-id="ff64e-129">Für einfache wiederkehrende Aufgaben stellt Azure Functions den `TimerTrigger` bereit, der basierend auf einem Cron-Ausdruck geplant werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff64e-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="ff64e-130">Der Timer eignet sich gut für einfache, kurzlebige Aufgaben, aber es kann Szenarien geben, in denen eine flexiblere Planung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ff64e-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="ff64e-131">Dieses Szenario ist der Fall, wenn das Überwachungs Muster und der Durable Functions helfen können.</span><span class="sxs-lookup"><span data-stu-id="ff64e-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="ff64e-132">Durable Functions ermöglicht flexible Planungs Intervalle, Lebensdauer Verwaltung und die Erstellung mehrerer Monitor Prozesse aus einer einzelnen Orchestrierungs Funktion.</span><span class="sxs-lookup"><span data-stu-id="ff64e-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="ff64e-133">Ein Anwendungsfall für diese Funktionalität ist das Erstellen von Überwachungen für Aktienpreis Änderungen, die durchgeführt werden, sobald ein bestimmter Schwellenwert erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="ff64e-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="ff64e-134">die `CreateTimer`-Methode von `DurableOrchestrationContext` richtet den Zeitplan für den nächsten Aufruf der Schleife ein, um nach Aktienkurs Änderungen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ff64e-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="ff64e-135">`DurableOrchestrationContext` verfügt auch über eine Eigenschaft `CurrentUtcDateTime`, um den aktuellen DateTime-Wert in UTC zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ff64e-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="ff64e-136">Es ist besser, diese Eigenschaft anstelle von "`DateTime.UtcNow`" zu verwenden, da Sie leicht zu Testzwecken verspottet wird.</span><span class="sxs-lookup"><span data-stu-id="ff64e-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="ff64e-137">Empfohlene Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ff64e-137">Recommended resources</span></span>

- [<span data-ttu-id="ff64e-138">Azure-Durable Functions</span><span class="sxs-lookup"><span data-stu-id="ff64e-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="ff64e-139">Komponententests in .NET Core und .NET Standard</span><span class="sxs-lookup"><span data-stu-id="ff64e-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="ff64e-140">[Zurück](durable-azure-functions.md)
>[Weiter](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="ff64e-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
