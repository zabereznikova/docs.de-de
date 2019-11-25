---
title: 'Durable Functions (Azure): Serverlose Apps'
description: Durable Functions in Azure erweitern die Azure Functions-Laufzeit, um zustandsbehaftete Workflows im Code zu ermöglichen.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522861"
---
# <a name="durable-azure-functions"></a>Durable Functions (Azure)

Wenn Sie serverlose Anwendungen mit Azure Functions erstellen, sind Ihre Vorgänge in der Regel so konzipiert, dass sie zustandslos ausgeführt werden. Der Grund für diese Entwurfsentscheidung besteht darin, dass es bei der Skalierung der Plattform schwierig zu ermitteln ist, auf welchen Servern der Code ausgeführt wird. Außerdem ist schwierig zu ermitteln, wie viele Instanzen zu einem beliebigen Zeitpunkt aktiv sind. Es gibt jedoch Klassen von Anwendungen, für die der aktuelle Zustand eines Prozesses bekannt sein muss. Denken Sie an den Prozess der Übermittlung einer Bestellung an einen Onlineshop. Der Check-Out-Vorgang kann ein Workflow sein, der aus mehreren Vorgängen besteht, die den Status des Prozesses kennen müssen. Zu diesen Informationen können der Produktbestand gehören, ob der Kunde über Guthaben auf seinem Konto verfügt, sowie die Ergebnisse der Verarbeitung der Kreditkarte. Diese Vorgänge könnten leicht eigene interne Workflows oder sogar Dienste von Drittanbietersystemen sein.

Es gibt heute verschiedene Muster, die bei der Koordination des Anwendungszustands zwischen internen und externen Systemen helfen. Es ist üblich, Lösungen zu verwenden, die auf zentralisierte Warteschlangensysteme, verteilte Schlüssel-Wert-Speicher oder gemeinsam verwendete Datenbanken angewiesen sind, um diesen Zustand zu verwalten. Dies sind allerdings alles zusätzliche Ressourcen, die jetzt bereitgestellt und verwaltet werden müssen. In einer serverlosen Umgebung kann Ihr Code umständlich versuchen, die Koordination mit diesen Ressourcen manuell durchzuführen. Azure Functions bietet eine Alternative zum Erstellen zustandsbehafteter Funktionen, die als „Durable Functions“ bezeichnet wird.

Durable Functions ist eine Erweiterung der Azure Functions-Laufzeit, die die Definition zustandsbehafteter Workflows im Code ermöglicht. Durch das Aufteilen von Workflows in Aktivitäten kann die Durable Functions-Erweiterung den Status verwalten, Fortschrittsprüfpunkte erstellen und die Verteilung von Funktionsaufrufen serverübergreifend verarbeiten. Im Hintergrund nutzt Durable Functions ein Azure Storage-Konto, um den Ausführungsverlauf persistent zu speichern, Aktivitätsfunktionen zu planen und Antworten abzurufen. Ihr serverloser Code sollte niemals mit persistent gespeicherten Informationen in diesem Speicherkonto interagieren. Dies sind normalerweise auch keine Informationen, mit denen Entwickler interagieren müssen.

## <a name="triggering-a-stateful-workflow"></a>Auslösen eines zustandsbehafteten Workflows

Zustandsbehaftete Workflows in Durable Functions können in zwei systeminterne Komponenten aufgeteilt werden: Orchestrierung und Aktivitätstrigger. Trigger und Bindungen sind Kernkomponenten, die von Azure Functions verwendet werden, damit Ihre serverlosen Funktionen benachrichtigt werden können, wann sie starten, Eingaben empfangen und Ergebnisse zurückgeben sollen.

### <a name="working-with-the-orchestration-client"></a>Arbeiten mit dem Orchestrierungsclient

Orchestrierungen sind im Vergleich zu anderen Arten von ausgelösten Vorgängen in Azure Functions eindeutig. Durable Functions ermöglicht die Ausführung von Funktionen, die bis zu ihrem Abschluss mehrere Stunden oder sogar Tage dauern können. Diese Art von Verhalten bringt die Notwendigkeit mit sich, den Status einer aktiven Orchestrierung zu überprüfen, sie vorzeitig zu beenden oder Benachrichtigungen zu externen Ereignissen zu senden.

Für solche Fälle stellt die Durable Functions-Erweiterung die `DurableOrchestrationClient`-Klasse bereit, die Ihnen die Interaktion mit orchestrierten Funktionen ermöglicht. Sie erhalten Zugriff auf den Orchestrierungclient, indem Sie die `OrchestrationClientAttribute`-Bindung verwenden. Im Allgemeinen würden Sie dieses Attribut in einen anderen Triggertyp einbinden, z.B. `HttpTrigger` oder `ServiceBusTrigger`. Nachdem die Quellfunktion ausgelöst wurde, kann der Orchestrierungsclient zum Starten einer Orchestratorfunktion verwendet werden.

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

### <a name="the-orchestrator-function"></a>Die Orchestratorfunktion

Wenn Sie eine Funktion mit OrchestrationTriggerAttribute in Azure Functions kommentieren, wird diese Funktion als Orchestratorfunktion markiert. Sie ist für die Verwaltung der verschiedenen Aktivitäten verantwortlich, die Ihren zustandsbehafteten Workflow bilden.

Orchestratorfunktionen können keine anderen Bindungen als OrchestrationTriggerAttribute verwenden. Dieses Attribut kann nur mit dem Parametertyp DurableOrchestrationContext verwendet werden. Es können keine anderen Eingaben verwendet werden, da die Deserialisierung von Eingaben in der Funktionssignatur nicht unterstützt wird. Zum Abrufen von Eingaben, die vom Orchestrierungsclient bereitgestellt werden, muss die Methode GetInput\<T\> verwendet werden.

Außerdem müssen die Rückgabetypen von Orchestrierungsfunktionen entweder void, Task oder ein serialisierbarer JSON-Wert sein.

> *Fehlerbehandlungscode wurde aus Platzgründen ausgelassen*

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

Mehrere Instanzen einer Orchestrierung können gleichzeitig gestartet und ausgeführt werden. Wenn Sie die `StartNewAsync`-Methode für `DurableOrchestrationClient` aufrufen, wird eine neue Instanz der Orchestrierung gestartet. Die Methode gibt ein `Task<string>`-Element zurück, das abgeschlossen wird, wenn die Orchestrierung gestartet wurde. Eine Ausnahme vom Typ `TimeoutException` wird ausgelöst, wenn die Orchestrierung nicht innerhalb von 30 Sekunden gestartet wurde.

Das abgeschlossene `Task<string>`-Element aus `StartNewAsync` sollte die eindeutige ID der Orchestrierungsinstanz enthalten. Diese Instanz-ID kann verwendet werden, um Vorgänge für diese spezifische Orchestrierung aufzurufen. Die Orchestrierung kann mach dem Status abgefragt werden oder Ereignisbenachrichtigungen senden.

### <a name="the-activity-functions"></a>Die Aktivitätsfunktionen

Aktivitätsfunktionen sind die diskreten Vorgänge, die in einer Orchestrierungsfunktion zusammengestellt werden, um den Workflow zu erstellen. And dieser Stelle findet der größte Teil der eigentlichen Arbeit statt. Diese Funktionen stellen die Geschäftslogik, zeitintensive Prozesse und die Puzzleteile für eine größere Lösung dar.

`ActivityTriggerAttribute` wird verwendet, um einen Funktionsparameter vom Typ `DurableActivityContext` zu kommentieren. Mithilfe der Anmerkung wird der Laufzeit mitgeteilt, dass die-Funktion als Aktivitätsfunktion verwendet werden soll. Eingabewerte für Aktivitätsfunktionen werden mit der `GetInput<T>`-Methode des `DurableActivityContext`-Parameters abgerufen.

Ähnlich wie bei Orchestrierungsfunktionen müssen die Rückgabetypen von Aktivitätsfunktionen entweder void, Task oder ein serialisierbarer JSON-Wert sein.

Alle nicht behandelten Ausnahmen, die innerhalb von Aktivitätsfunktionen ausgelöst werden, werden an die aufrufende Orchestratorfunktion gesendet und als `TaskFailedException` ausgegeben. An diesem Punkt kann der Fehler abgefangen und im Orchestrator protokolliert werden, und für die Aktivität kann ein Wiederholungsversuch ausgeführt werden.

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

- [Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Bindungen für Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [Verwalten von Instanzen in Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[Zurück](event-grid.md)
>[Weiter](orchestration-patterns.md)
