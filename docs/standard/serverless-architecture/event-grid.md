---
title: Azure Event Grid – serverlose apps
description: Azure Event Grid ist ein serverlosen Lösung für die zuverlässige Ereignisübermittlung und routing in großem Umfang auf ein Modell für die Zahlung pro Ereignis.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 240542014a34235aea9fd0f8162748749f23eacf
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143661"
---
# <a name="event-grid"></a>Event Grid

[Azure Event Grid](/azure-event-grid/overview) bietet serverlose-Infrastruktur für Ereignis-basierte Anwendungen. Sie können aus beliebigen Quellen Event Grid veröffentlichen und nutzen Nachrichten von einer beliebigen Plattform. Event Grid bietet auch integrierten Unterstützung für die Ereignisse aus Azure-Ressourcen für die Integration in Ihre Anwendungen zu optimieren. Beispielsweise können Sie abonnieren, um Blob-Storage-Ereignissen an Ihre app zu benachrichtigen, wenn eine Datei hochgeladen wird. Ihre Anwendung können Sie eine Meldung eines benutzerdefinierten Raster veröffentlichen, das von anderen Cloud verwendet oder lokale Anwendungen. Event Grid wurde erstellt, um zuverlässig sehr großem Umfang zu verarbeiten. Sie erhalten die Vorteile von veröffentlichen und Abonnieren von Nachrichten ohne den Aufwand für die notwendige Infrastruktur einrichten.

![Event Grid-logo](./media/event-grid-logo.png)

Die wichtigsten Features von Event Grid gehören:

* Vollständig verwaltetem Ereignisrouting.
* Nahezu in Echtzeit-Übermittlung nach Maß.
* Umfassende Abdeckung innerhalb und außerhalb von Azure.

## <a name="scenarios"></a>Szenarien

Event Grid werden die verschiedene Szenarien behandelt. Dieser Abschnitt enthält drei der am häufigsten verwendeten Seiten.

### <a name="ops-automation"></a>Betriebsautomatisierung

![Betriebsautomatisierung](./media/ops-automation.png)

Event Grid kann Hilfe von Automatisierung für Geschwindigkeit und die richtlinienerzwingung vereinfachen, indem benachrichtigt [Azure Automation](https://docs.microsoft.com/azure/automation) Wenn Infrastruktur bereitgestellt wird.

### <a name="application-integration"></a>Anwendungsintegration

![Anwendungsintegration](./media/app-integration.png)

Event Grid können Ihre app mit anderen Diensten zu verbinden. Mithilfe von HTTP-Protokollen, können auch legacy-apps ganz einfach geändert werden zum Veröffentlichen von Nachrichten von Event Grid. Web-Hooks stehen für andere Dienste und Plattformen, um Event Grid-Nachrichten zu verarbeiten.

### <a name="serverless-apps"></a>Serverlose apps

![Serverlose apps](./media/serverless-apps.png)

Event Grid kann Azure Functions, Logic Apps oder Ihren eigenen benutzerdefinierten Code auslösen. Ein großer Vorteil der Verwendung von Event Grid ist, jedoch verwendet eine *Push* Mechanismus zum Senden von Nachrichten, wenn Ereignisse auftreten. Die Push-Architektur weniger Ressourcen belegt, und eine bessere Skalierbarkeit als *abrufen* Mechanismen. Abruf muss Updates in regelmäßigen Abständen überprüfen.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Event Grid im Vergleich zu anderen Azure-Messagingdiensten

Azure bietet mehrere messaging-Dienste, einschließlich [Event Hubs](https://docs.microsoft.com/azure/event-hubs) und [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging). Jede ist speziell auf eine bestimmte Gruppe von Anwendungsfällen. Das folgende Diagramm bietet einen allgemeinen Überblick über die Unterschiede zwischen den Diensten.

![Azure messaging-Vergleich](./media/azure-messaging-services.png)

Einen ausführlicheren Vergleich finden Sie unter [Vergleich von Messagingdiensten](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Leistungsziele

Garantiert mit Event Grid, die Sie die folgenden Leistung nutzen können:

* Subsecond End-to-End-Wartezeit im 99. Perzentil.
* Verfügbarkeit von 99,99 %.
* 10 Millionen Ereignisse pro Sekunde pro Region.
* 100 Millionen von Abonnements pro Region.
* Verleger-Latenz 50 ms.
* 24-Stunden-Wiederholung mit exponentiellem Backoff für garantierte Zustellung im Fenster 1 Tag.
* Transparentes regionales Failover.

## <a name="event-grid-schema"></a>Event Grid-schema

Event Grid verwendet ein Standardschema, um benutzerdefinierte Ereignisse zu umschließen. Das Schema ist wie ein Umschlag, der das benutzerdefinierte Element umschließt. Hier ist ein Beispiel für Event Grid-Meldung aus:

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

Alles über die Meldung ist standard, mit Ausnahme der `data` Eigenschaft. Sie können die Nachricht zu überprüfen und die `eventType` und `dataVersion` deserialisiert den benutzerdefinierte Teil der Nutzlast.

## <a name="azure-resources"></a>Azure-Ressourcen

Ein großer Vorteil der Verwendung von Event Grid ist die automatische Nachrichten, die von Azure erstellt. In Azure Ressourcen automatisch veröffentlichen in einer *Thema* , mit der Sie für verschiedene Ereignisse zu abonnieren. Die folgende Tabelle enthält die Ressourcentypen, Nachrichtentypen und Ereignisse, die automatisch verfügbar sind.

| Azure-Ressourcen | Ereignistyp | Beschreibung |
| -------------- | ---------- | ----------- |
| Azure-Abonnement | Microsoft.Resources.ResourceWriteSuccess | Wird ausgelöst, wenn erstellungs- oder Aktualisierungsvorgang eine Ressource ist erfolgreich. |
| | Microsoft.Resources.ResourceWriteFailure | Wird ausgelöst, wenn eine Ressource zu erstellen oder Updatevorgang ein Fehler auftritt. |
| | Microsoft.Resources.ResourceWriteCancel | Wird ausgelöst, werden Wenn erstellungs- oder Aktualisierungsvorgang eine Ressource abgebrochen. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Ausgelöst, wenn der Löschvorgang einer Ressource erfolgreich ist. |
|  | Microsoft.Resources.ResourceDeleteFailure | Ausgelöst, wenn der Löschvorgang einer Ressource ein Fehler auftritt. |
| | Microsoft.Resources.ResourceDeleteCancel | Wird ausgelöst, wenn der Löschvorgang einer Ressource abgebrochen wird. Dieses Ereignis erfolgt, wenn eine vorlagenbereitstellung abgebrochen wird. |
| BLOB-Speicher | Microsoft.Storage.BlobCreated | Wird ausgelöst, wenn ein Blob erstellt wird. |
| | Microsoft.Storage.BlobDeleted | Wird ausgelöst, wenn ein Blob gelöscht wird. |
| Event hubs | Microsoft.EventHub.CaptureFileCreated | Wird ausgelöst, wenn eine erfassungsdatei erstellt wird.
| IoT Hub-Instanz | Microsoft.Devices.DeviceCreated | Veröffentlicht, wenn ein Gerät mit einem iothub registriert wird. |
| | Microsoft.Devices.DeviceDeleted | Veröffentlicht, wenn ein Gerät von einem iothub gelöscht wird. |
| Ressourcengruppen | Microsoft.Resources.ResourceWriteSuccess | Wird ausgelöst, wenn erstellungs- oder Aktualisierungsvorgang eine Ressource ist erfolgreich. |
| | Microsoft.Resources.ResourceWriteFailure | Wird ausgelöst, wenn eine Ressource zu erstellen oder Updatevorgang ein Fehler auftritt. |
| | Microsoft.Resources.ResourceWriteCancel | Wird ausgelöst, werden Wenn erstellungs- oder Aktualisierungsvorgang eine Ressource abgebrochen. |
| | Microsoft.Resources.ResourceDeleteSuccess | Ausgelöst, wenn der Löschvorgang einer Ressource erfolgreich ist. |
| | Microsoft.Resources.ResourceDeleteFailure | Ausgelöst, wenn der Löschvorgang einer Ressource ein Fehler auftritt. |
| | Microsoft.Resources.ResourceDeleteCancel | Wird ausgelöst, wenn der Löschvorgang einer Ressource abgebrochen wird. Dieses Ereignis erfolgt, wenn eine vorlagenbereitstellung abgebrochen wird. |

Weitere Informationen finden Sie unter [Azure Event Grid-Ereignisschema](https://docs.microsoft.com/azure/event-grid/event-schema).

Event Grid können Sie von jeder Art von Anwendung, selbst eine zugreifen, die lokal ausgeführt wird.

## <a name="conclusion"></a>Schlussbemerkung

In diesem Kapitel haben Sie über die Azure serverlose Plattform, die von Azure Functions, Logic Apps und Event Grid zusammengesetzt ist. Sie können diese Ressourcen verwenden, um eine vollständig serverlosen app-Architektur zu erstellen oder erstellen eine hybridlösung, die interagiert mit anderen Cloudressourcen und lokale Server. Wie z. B. in Kombination mit einer serverlosen Datenplattform [Azure SQL](https://docs.microsoft.com/azure/sql-database) oder [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), Sie können vollständig verwaltete Cloud native Anwendungen erstellen.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Application Insights-Analyse](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Azure: Bringen Sie Ihre app in die Cloud mit serverlosen Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102)
* [Azure Event Grid](https://docs.microsoft.com/azure/azure-event-grid/overview)
* [Azure Event Grid-Ereignisschema](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs)
* [Dokumentation zu Azure Functions](https://docs.microsoft.com/azure/azure-functions)
* [Azure Functions-Trigger und Bindungen-Konzepte](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
* [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
* [Azure-Tabellenspeicher](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [Vergleich von functions 1.x und 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [Herstellen einer Verbindung mit lokalen Datenquellen mit Azure On-Premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Erstellen Sie Ihrer ersten Funktion im Azure-portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Erstellen Sie Ihrer ersten Funktion mit der Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Erstellen Sie Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [Functions unterstützte Sprachen](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Überwachen von Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Arbeiten Sie mit Azure Functions-Proxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Zurück](logic-apps.md)
>[Weiter](durable-azure-functions.md)