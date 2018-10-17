---
title: Durable Azure Functions – serverlose apps
description: Permanente Azure-Funktionen erweitern die Azure Functions-Laufzeit, um zustandsbehaftete Workflows in Code zu aktivieren.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 03197ad57813b8132fe592f4e555c6a35edbd9bd
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369955"
---
# <a name="durable-azure-functions"></a>Permanenten Azure-Funktionen

Wenn Sie mit Azure Functions serverlose Anwendungen zu erstellen, werden Ihre Vorgänge in der Regel entworfen werden, in eine statusfreie Weise ausgeführt. Der Grund für diese entwurfsentscheidung liegt als die Skalierung der Plattform, wird es schwierig, Sie wissen, welche Server der Code ausgeführt wird. Es wird auch nur schwer erkennbar, wie viele Instanzen zu einem bestimmten Zeitpunkt aktiv sind. Es gibt jedoch Klassen von Anwendungen, die den aktuellen Status eines Prozesses nicht bekannt sein müssen. Betrachten Sie den Prozess zur Übermittlung einer Bestellung zu einem Onlineshop. Der Auscheckvorgang möglicherweise einen Workflow, der mehrere Vorgänge besteht, die den Zustand des Prozesses kennen müssen. Solche Informationen gehören möglicherweise die Produktbestands, wenn der Kunde Form von Credits auf ihr Konto und die Ergebnisse der Verarbeitung der Kreditkarte verfügt. Diese Vorgänge ist möglicherweise einfach eigene interne Workflows oder sogar Dienste von Drittanbietern.

Heute sind verschiedene Muster, Unterstützung mit der Koordinierung von Anwendungsstatus zwischen internen und externen Systemen. Es ist üblich, stoßen auf Lösungen, die zentralisierte warteschlangensysteme, verteilter Schlüssel-Wert-Speicher oder freigegebene Datenbanken zur Verwaltung dieses Zustands verwenden. Diese sind jedoch alle zusätzlichen Ressourcen, die jetzt bereitgestellt und verwaltet werden müssen. In einer serverlosen Umgebung kann Ihr Code koordinierte mit diesen Ressourcen manuell sehr aufwändig. Azure Functions bietet eine Alternative zum Erstellen von zustandsbehafteter Funktionen, die Durable Functions aufgerufen.

Durable Functions ist eine Erweiterung für Azure Functions-Laufzeit, die die Definition der zustandsbehaftete Workflows in Code ermöglicht. Die Erweiterung Durable Functions können Sie Workflows in Aktivitäten aufteilen, Verwalten des Zustands, Fortschritt Prüfpunkte erstellen und behandeln die Verteilung von Funktionsaufrufen auf Servern. Im Hintergrund ist es, mithilfe von Azure Storage-Konto der Ausführungsverlauf beibehalten, Planen aktivitätsfunktionen und Abrufen von Antworten. Ihrem serverlose Code nie dauerhaft gespeicherten Informationen in diesem Speicherkonto interagieren soll, und ist in der Regel nicht etwas mit dem Entwickler interagieren müssen.

## <a name="triggering-a-stateful-workflow"></a>Auslösen eines zustandsbehafteten Workflows

Zustandsbehaftete Workflows in Durable Functions können in zwei systeminterne Komponenten aufgeteilt werden; Orchestrierung und Aktivität von Triggern. Trigger und Bindungen sind Kernkomponenten, die von Azure Functions verwendet werden, um Ihre serverlosen Funktionen benachrichtigt, wenn die Eingabe starten, erhalten und Ergebnisse zurückgeben zu aktivieren.

### <a name="working-with-the-orchestration-client"></a>Arbeiten mit den orchestrierungsclient

Orchestrierungen sind eindeutig, im Vergleich zu anderen Arten der ausgelösten Vorgänge in Azure Functions. Durable Functions ermöglicht die Ausführung von Funktionen, die Stunden dauern oder sogar Tage ausführen können. Diese Art von Verhalten wird in der Lage sein, um den Status einer ausgeführten Orchestrierung überprüfen müssen, bereits im Vorfeld zu beenden, oder senden Sie Benachrichtigungen über externe Ereignisse.

In solchen Fällen enthält die Erweiterung Durable Functions die `DurableOrchestrationClient` -Klasse, die Ihnen ermöglicht, die Interaktion mit orchestriert Funktionen. Sie erhalten Sie Zugriff auf den orchestrierungsclient mithilfe der `OrchestrationClientAttribute` Bindung. In der Regel ist, schließen Sie dieses Attribut mit einem anderen Triggertyp, z. B. eine `HttpTrigger` oder `ServiceBusTrigger`. Nachdem die Quelle-Funktion ausgelöst wurde, kann der orchestrierungsclient zu einer Orchestrator-Funktion verwendet werden.

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

### <a name="the-orchestrator-function"></a>Der Orchestrator-Funktion

Hinzufügen einer Anmerkung zu einer Funktion mit dem OrchestrationTriggerAttribute in Azure Functions ein diese Funktion als eine orchestratorfunktion. Er ist verantwortlich für die verschiedenen Aktivitäten, aus denen Ihre zustandsbehaftete Workflows verwalten.

Orchestratorfunktionen können keine vorgenommen werden Bindungen die OrchestrationTriggerAttribute verwenden. Dieses Attribut kann nur mit dem Parametertyp DurableOrchestrationContext verwendet werden. Keine anderen Eingaben können verwendet werden, da die Deserialisierung von Eingaben in die Funktionssignatur wird nicht unterstützt. Zum Abrufen von Eingaben von der orchestrierungsclientbindung, die GetInput\<T\> Methode muss verwendet werden.

Darüber hinaus die Rückgabetypen der Orchestrierungsfunktionen muss entweder "void", Task oder einen serialisierbaren JSON-Wert.

> *Code für die Fehlerbehandlung wurde aus Gründen der Übersichtlichkeit ausgelassen wurde*

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

Zur gleichen Zeit können in mehreren Instanzen einer Orchestrierung gestartet und ausgeführt sein. Aufrufen der `StartNewAsync` Methode für die `DurableOrchestrationClient` startet eine neue Instanz der Orchestrierung. Die Methode gibt eine `Task<string>` , die abgeschlossen wird, wenn die Orchestrierung gestartet wurde. Eine Ausnahme vom Typ `TimeoutException` ruft ausgelöst, wenn die Orchestrierung nicht innerhalb von 30 Sekunden gestartet.

Die abgeschlossene `Task<string>` aus `StartNewAsync` sollten enthält die eindeutige ID der Orchestrierungsinstanz. Diese Instanz-ID kann verwendet werden, um Vorgänge für diese bestimmte Orchestrierung aufzurufen. Die Orchestrierung kann abgefragt werden, für den Status oder ereignisbenachrichtigungen gesendet werden.

### <a name="the-activity-functions"></a>Der aktivitätsfunktionen

Aktivitätsfunktionen sind die diskreten Vorgänge, die zusammen in einer Orchestrierungsfunktion zum Erstellen des Workflows erstellt zu erhalten. Hier ist, in denen meisten der eigentlichen Arbeit durchgeführt werden sollen. Sie stellen die Geschäftslogik dar, die lang ausgeführte Prozesse, und die Puzzleteile zu einer größeren Lösung.

Die `ActivityTriggerAttribute` wird verwendet, um einen Funktionsparameter vom Typ mit Anmerkungen versehen `DurableActivityContext`. Mithilfe der-Anmerkung informiert die Laufzeit an, dass die Funktion als eine aktivitätsfunktion verwendet werden soll. Eingabewerte für aktivitätsfunktionen werden abgerufen, mit der `GetInput<T>` Methode der `DurableActivityContext` Parameter.

Ähnlich wie Orchestrierungsfunktionen, die Rückgabetypen der aktivitätsfunktionen muss entweder "void", Task oder einen serialisierbaren JSON-Wert.

Alle nicht behandelten Ausnahmen, die in aktivitätsfunktionen werden gesendet, wird an die aufrufende orchestratorfunktion und als eine `TaskFailedException`. An diesem Punkt wird der Fehler abgefangen und protokolliert Sie in der Orchestrator werden kann, und die Aktivität wiederholt werden kann.

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
[Zurück](event-grid.md)
[Weiter](orchestration-patterns.md)