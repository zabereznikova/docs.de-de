---
title: Orchestrierung-Muster – serverlose apps
description: Azure Durable Functions pr
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: c3b9dbe473ba9272a8c8c07cec86e11fcd9fc12d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129310"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="31bb8-103">Orchestrierung-Muster</span><span class="sxs-lookup"><span data-stu-id="31bb8-103">Orchestration patterns</span></span>

<span data-ttu-id="31bb8-104">Durable Functions erleichtert es, um zustandsbehaftete Workflows zu erstellen, die diskret, lang ausgeführte Aktivitäten in einer serverlosen Umgebung bestehen.</span><span class="sxs-lookup"><span data-stu-id="31bb8-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="31bb8-105">Da die Durable Functions den Ausführungsverlauf in dem Status des Workflows und in regelmäßigen Abständen Prüfpunkte nachverfolgen können, gestattet es einige interessante Muster zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="31bb8-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="31bb8-106">Funktionsverkettung</span><span class="sxs-lookup"><span data-stu-id="31bb8-106">Function chaining</span></span>

<span data-ttu-id="31bb8-107">In einem typischen sequenziellen Prozess müssen Aktivitäten nacheinander in einer bestimmten Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="31bb8-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="31bb8-108">Optional kann die nächsten Aktivität eine Ausgabe aus der vorherigen Funktion erfordern.</span><span class="sxs-lookup"><span data-stu-id="31bb8-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="31bb8-109">Diese Abhängigkeit für die Reihenfolge der Aktivitäten wird eine Funktion-Kette der Ausführung erstellt.</span><span class="sxs-lookup"><span data-stu-id="31bb8-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="31bb8-110">Der Vorteil der Verwendung von Durable Functions zum Implementieren dieses Musters Workflow liegt in der Fähigkeit zum Setzen von Prüfpunkten zu tun.</span><span class="sxs-lookup"><span data-stu-id="31bb8-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="31bb8-111">Wenn der Server abstürzt, können das Netzwerk ein Timeout auftritt oder ein andere Problem tritt auf, und Durable Functions vom letzten bekannten Zustand fortgesetzt weiterhin Ihr Workflow ausgeführt wird, auch wenn sie sich auf einem anderen Server befindet.</span><span class="sxs-lookup"><span data-stu-id="31bb8-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="31bb8-112">Im vorherigen Codebeispiel das `CallActivityAsync` Funktion ist verantwortlich für die Ausführung einer bestimmten Aktivität auf einem virtuellen Computer im Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="31bb8-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="31bb8-113">Wenn die "await" zurückgibt und die zugrunde liegende Aufgabe abgeschlossen ist, wird die Ausführung in die Verlaufstabelle aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="31bb8-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="31bb8-114">Der Code in der orchestratorfunktion kann ist die vertraute Konstrukte der Task Parallel Library und die Schlüsselwörter "Async/await" verwenden.</span><span class="sxs-lookup"><span data-stu-id="31bb8-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="31bb8-115">Der folgende Code ist ein vereinfachtes Beispiel, was die `ProcessPayment` Methode kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="31bb8-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="31bb8-116">Asynchrone HTTP-APIs</span><span class="sxs-lookup"><span data-stu-id="31bb8-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="31bb8-117">In einigen Fällen können Workflows, Aktivitäten enthalten, die relativ längere Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="31bb8-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="31bb8-118">Angenommen Sie, einen Prozess, der aus der Sicherung von Medien die Dateien in Blob Storage zum Einsatz kommt.</span><span class="sxs-lookup"><span data-stu-id="31bb8-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="31bb8-119">Je nach Größe und Anzahl der Mediendateien kann dieser Sicherungsprozess Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="31bb8-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="31bb8-120">In diesem Szenario die `DurableOrchestrationClient`die Möglichkeit zum Überprüfen des Status eines ausgeführten Workflows ist nützlich.</span><span class="sxs-lookup"><span data-stu-id="31bb8-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="31bb8-121">Bei Verwendung einer `HttpTrigger` zum Starten eines Workflows, die `CreateCheckStatusResponse` Methode kann verwendet werden, um eine Instanz des zurückzugeben `HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="31bb8-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="31bb8-122">Diese Antwort enthält den Client mit einem URI in der Nutzlast, die zum Überprüfen des Status des ausgeführten Prozesses verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="31bb8-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="31bb8-123">Das folgende Beispielergebnis zeigt die Struktur der antwortnutzlast an.</span><span class="sxs-lookup"><span data-stu-id="31bb8-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="31bb8-124">Mit Ihrem bevorzugten HTTP-Client, können GET-Anforderungen an den URI in StatusQueryGetUri vorgenommen werden, überprüfen den Status der ausgeführten Workflows.</span><span class="sxs-lookup"><span data-stu-id="31bb8-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="31bb8-125">Die Antwort zurückgegebene Status sollte dem folgenden Code ähneln.</span><span class="sxs-lookup"><span data-stu-id="31bb8-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="31bb8-126">Wie der Prozess wird fortgesetzt, ändert sich die Statusantwort entweder **Fehler** oder **abgeschlossen**.</span><span class="sxs-lookup"><span data-stu-id="31bb8-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="31bb8-127">Bei erfolgreichem Abschluss der **Ausgabe** Eigenschaft in der Nutzlast enthält alle zurückgegebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="31bb8-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="31bb8-128">Überwachung</span><span class="sxs-lookup"><span data-stu-id="31bb8-128">Monitoring</span></span>

<span data-ttu-id="31bb8-129">Bei einfachen sich wiederholenden Aufgaben, die Azure Functions bietet die `TimerTrigger` , kann anhand eines CRON-Ausdrucks geplant werden.</span><span class="sxs-lookup"><span data-stu-id="31bb8-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="31bb8-130">Der Zeitgeber eignet sich gut für einfache, kurz dauernden Aufgaben, doch in manchen Szenarien, in denen mehr flexible zeitplanung ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31bb8-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="31bb8-131">Dieses Szenario ist, wenn das Muster für Überwachung und Durable Functions profitieren können.</span><span class="sxs-lookup"><span data-stu-id="31bb8-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="31bb8-132">Durable Functions ermöglicht flexible zeitplanung Intervallen, Verwaltung der Lebensdauer und die Erstellung mehrerer Monitor-Prozesse aus einer einzigen Orchestrierung-Funktion.</span><span class="sxs-lookup"><span data-stu-id="31bb8-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="31bb8-133">Ein Anwendungsfall für diese Funktionalität möglicherweise-Watcher für Änderungen der Aktienkurs zu erstellen, die abgeschlossen wird, wenn einen bestimmten Schwellenwert erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="31bb8-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="31bb8-134">`DurableOrchestrationContext`die `CreateTimer` Methode richtet den Zeitplan für den nächsten Aufruf der Schleife, um Aktienkurs Änderungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="31bb8-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="31bb8-135">`DurableOrchestrationContext` verfügt auch über eine `CurrentUtcDateTime` Eigenschaft, um den aktuellen DateTime-Wert in UTC, abzurufen.</span><span class="sxs-lookup"><span data-stu-id="31bb8-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="31bb8-136">Es ist besser, verwenden Sie diese Eigenschaft anstelle der `DateTime.UtcNow` , da es einfach zu Testzwecken simuliert wird.</span><span class="sxs-lookup"><span data-stu-id="31bb8-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="31bb8-137">Empfohlene Ressourcen</span><span class="sxs-lookup"><span data-stu-id="31bb8-137">Recommended resources</span></span>

* [<span data-ttu-id="31bb8-138">Azure Durable Functions</span><span class="sxs-lookup"><span data-stu-id="31bb8-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="31bb8-139">Komponententests in .NET Core und .NET Standard</span><span class="sxs-lookup"><span data-stu-id="31bb8-139">Unit Testing in .NET Core and .NET Standard</span></span>](https://docs.microsoft.com/dotnet/core/testing/)

>[!div class="step-by-step"]
><span data-ttu-id="31bb8-140">[Zurück](durable-azure-functions.md)
>[Weiter](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="31bb8-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>