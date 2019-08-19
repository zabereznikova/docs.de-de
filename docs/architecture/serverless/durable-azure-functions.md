---
title: Permanente Azure Functions-Server Lose apps
description: Durable Azure Functions erweitert die Azure Functions Laufzeit, um Zustands behaftete Workflows im Code zu aktivieren.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: f7ee74926d6658042120113b49dc763383881423
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577513"
---
# <a name="durable-azure-functions"></a>Durable Functions (Azure)

Wenn Sie Server lose Anwendungen mit Azure Functions erstellen, werden die Vorgänge in der Regel auf Zustands lose Weise ausgeführt. Der Grund für diese Entwurfs Entscheidung besteht darin, dass bei der Skalierung der Plattform die Server, auf denen der Code ausgeführt wird, schwer zu erkennen ist. Außerdem wird es schwierig zu wissen, wie viele Instanzen zu einem beliebigen Zeitpunkt aktiv sind. Es gibt jedoch Klassen von Anwendungen, für die der aktuelle Zustand eines Prozesses bekannt sein muss. Erwägen Sie den Prozess der Übermittlung eines Auftrags an einen Online Shop. Der Auscheck Vorgang kann ein Workflow sein, der aus mehreren Vorgängen besteht, die den Status des Prozesses kennen müssen. Diese Informationen können die Produkt Inventur enthalten, wenn der Kunde Gutschriften für sein Konto hat, und auch die Ergebnisse der Verarbeitung der Kreditkarte. Bei diesen Vorgängen kann es sich problemlos um eigene interne Workflows oder sogar um Dienste von Drittanbieter Systemen handeln.

Heute gibt es verschiedene Muster, die die Koordination des Anwendungs Zustands zwischen internen und externen Systemen unterstützen. Es ist üblich, Lösungen zu entwickeln, die sich auf zentrale Warteschlangen Systeme, verteilte Schlüssel-Wert-Speicher oder freigegebene Datenbanken stützen, um diesen Status zu verwalten. Dies sind allerdings alle zusätzlichen Ressourcen, die jetzt bereitgestellt und verwaltet werden müssen. In einer Server losen Umgebung könnte Ihr Code mühsam versuchen, sich mit diesen Ressourcen manuell zu koordinieren. Azure Functions bietet eine Alternative zum Erstellen Zustands behafteter Funktionen mit dem Namen Durable Functions.

Durable Functions ist eine Erweiterung der Azure Functions Laufzeit, die die Definition Zustands behafteter Workflows im Code ermöglicht. Durch das Aufteilen von Workflows in Aktivitäten kann die Durable Functions Erweiterung den Status verwalten, Status Prüfpunkte erstellen und die Verteilung von Funktionsaufrufen über mehrere Server hinweg verarbeiten. Im Hintergrund nutzt es ein Azure Storage Konto, um den Ausführungs Verlauf beizubehalten, Aktivitäts Funktionen zu planen und Antworten abzurufen. Der Server lose Code sollte nie mit permanenten Informationen in diesem Speicherkonto interagieren und ist in der Regel nicht mit den Entwicklern zu interagieren, mit denen Entwickler interagieren müssen.

## <a name="triggering-a-stateful-workflow"></a>Auslösen eines Zustands behafteten Workflows

Zustands behaftete Workflows in Durable Functions können in zwei systeminterne Komponenten aufgeteilt werden. Orchestrierungs-und Aktivitäts Trigger. Trigger und Bindungen sind Kernkomponenten, die von Azure Functions verwendet werden, damit Ihre Server losen Funktionen benachrichtigt werden können, wenn Sie beginnen, Eingaben empfangen und Ergebnisse zurückgeben.

### <a name="working-with-the-orchestration-client"></a>Arbeiten mit dem Orchestrierungs Client

Orchestrierungen sind im Vergleich zu anderen Arten von ausgelösten Vorgängen in Azure Functions eindeutig. Durable Functions ermöglicht die Ausführung von Funktionen, die mehrere Stunden oder sogar Tage dauern können. Diese Art von Verhalten besteht darin, dass es möglich ist, den Status einer laufenden Orchestrierung, die präemptiv Beendigung oder das Senden von Benachrichtigungen externer Ereignisse zu überprüfen.

In solchen Fällen stellt die Durable Functions-Erweiterung die `DurableOrchestrationClient` Klasse bereit, die Ihnen die Interaktion mit orchestrierten Funktionen ermöglicht. Sie erhalten Zugriff auf den Orchestrierungs Client, indem Sie `OrchestrationClientAttribute` die-Bindung verwenden. Im allgemeinen würden Sie dieses Attribut mit einem anderen auslösertyp einschließen, `HttpTrigger` z `ServiceBusTrigger`. b. oder. Nachdem die Quell Funktion ausgelöst wurde, kann der Orchestrierungs Client zum Starten einer orchestratorfunktion verwendet werden.

```csharp
[FunctionName("KickOff")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient<orchestrationClient>)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

### <a name="the-orchestrator-function"></a>Die orchestratorfunktion

Hinzufügen einer Anmerkung zu einer Funktion mit dem orchestrationtriggerattribute in Azure Functions Markierungen, die als orchestratorfunktion fungieren. Er ist für die Verwaltung der verschiedenen Aktivitäten verantwortlich, die ihren Zustands behafteten Workflow bilden.

Orchestratorfunktionen können keine anderen Bindungen als das orchestrationtriggerattribute verwenden. Dieses Attribut kann nur mit dem Parametertyp durableorchestrationcontext verwendet werden. Es können keine weiteren Eingaben verwendet werden, da die Deserialisierung von Eingaben in der Funktions Signatur nicht unterstützt wird. Zum Aufrufen von Eingaben, die vom Orchestrierungs Client bereitgestellt werden,\<muss\> die GetInput T-Methode verwendet werden.

Außerdem müssen die Rückgabe Typen von Orchestrierungs Funktionen entweder "void", "Task" oder ein serialisierbarer JSON-Wert sein.

> *Der Fehler Behandlungs Code wurde aus Gründen der Übersichtlichkeit ausgelassen.*

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<string>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

Mehrere Instanzen einer Orchestrierung können gleichzeitig gestartet und ausgeführt werden. Wenn Sie `StartNewAsync` die-Methode `DurableOrchestrationClient` für den aufrufen, wird eine neue Instanz der Orchestrierung gestartet. Die-Methode gibt `Task<string>` einen zurück, der abgeschlossen wird, wenn die Orchestrierung gestartet wurde. Eine Ausnahme vom Typ `TimeoutException` wird ausgelöst, wenn die Orchestrierung nicht innerhalb von 30 Sekunden gestartet wurde.

Der abgeschlossene `Task<string>` aus `StartNewAsync` sollte die eindeutige ID der Orchestrierungs Instanz enthalten. Diese Instanz-ID kann verwendet werden, um Vorgänge für diese bestimmte Orchestrierung aufzurufen. Die Orchestrierung kann für den Status oder die gesendeten Ereignis Benachrichtigungen abgefragt werden.

### <a name="the-activity-functions"></a>Die Aktivitäts Funktionen

Aktivitäts Funktionen sind die diskreten Vorgänge, die in einer Orchestrierungs Funktion zusammengesetzt werden, um den Workflow zu erstellen. Hier finden Sie den größten Teil der eigentlichen Arbeit. Sie stellen die Geschäftslogik, Prozesse mit langer Ausführungszeit und die Rätsel Teile für eine größere Lösung dar.

Wird verwendet, um einen Funktionsparameter vom Typ `DurableActivityContext`zu kommentieren. `ActivityTriggerAttribute` Mithilfe der-Anmerkung wird der Laufzeit mitgeteilt, dass die-Funktion als Aktivitäts Funktion verwendet werden soll. Eingabewerte für Aktivitäts Funktionen werden mithilfe der `GetInput<T>` -Methode `DurableActivityContext` des-Parameters abgerufen.

Ähnlich wie bei Orchestrierungs Funktionen müssen die Rückgabe Typen von Aktivitäts Funktionen entweder "void", "Task" oder ein serialisierbarer JSON-Wert sein.

Alle nicht behandelten Ausnahmen, die innerhalb von Aktivitäts Funktionen ausgelöst werden, werden an die aufrufende orchestratorfunktion gesendet und als `TaskFailedException`dargestellt. An diesem Punkt kann der Fehler abgefangen und in Orchestrator protokolliert werden, und die Aktivität kann wiederholt werden.

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Bindungen für Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
* [Verwalten von Instanzen in Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[Zurück](event-grid.md)
>[Weiter](orchestration-patterns.md)
