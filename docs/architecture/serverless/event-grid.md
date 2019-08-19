---
title: Azure Event Grid Server Lose apps
description: Azure Event Grid ist eine Server lose Lösung für die zuverlässige Ereignis Übermittlung und das Routing in großem Umfang für ein Modell mit Zahlen pro Ereignis.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577573"
---
# <a name="event-grid"></a>Event Grid

[Azure Event Grid](/azure/event-grid/overview) stellt Server lose Infrastruktur für ereignisbasierte Anwendungen bereit. Sie können auf Event Grid aus beliebigen Quellen veröffentlichen und Nachrichten von einer beliebigen Plattform verarbeiten. Event Grid bietet auch eine integrierte Unterstützung für Ereignisse von Azure-Ressourcen, um die Integration in Ihre Anwendungen zu optimieren. Beispielsweise können Sie BLOB Storage-Ereignisse abonnieren, um die APP zu benachrichtigen, wenn eine Datei hochgeladen wird. Die Anwendung kann dann eine benutzerdefinierte Event Grid-Nachricht veröffentlichen, die von anderen cloudbasierten oder lokalen Anwendungen verwendet wird. Event Grid wurde erstellt, um eine hohe Skalierbarkeit zuverlässig bewältigen zu können. Sie profitieren von den Vorteilen der Veröffentlichung und dem Abonnieren von Nachrichten ohne den Aufwand für die Einrichtung der erforderlichen Infrastruktur.

![Event Grid Logo](./media/event-grid-logo.png)

Zu den wichtigsten Features von Event Grid gehören:

* Vollständig verwaltetes Ereignis Routing.
* Nahezu in Echtzeit Bereitstellung von Ereignissen.
* Umfassende Abdeckung sowohl innerhalb als auch außerhalb von Azure.

## <a name="scenarios"></a>Szenarien

Event Grid adressiert verschiedene Szenarien. In diesem Abschnitt werden drei der gängigsten behandelt.

### <a name="ops-automation"></a>OPS-Automatisierung

![OPS-Automatisierung](./media/ops-automation.png)

Mithilfe Event Grid können Sie die Automatisierung beschleunigen und die Richtlinien Erzwingung vereinfachen, indem Sie [Azure Automation](https://docs.microsoft.com/azure/automation) Benachrichtigen, wenn die Infrastruktur bereitgestellt wird.

### <a name="application-integration"></a>Anwendungsintegration

![Anwendungsintegration](./media/app-integration.png)

Sie können Event Grid verwenden, um Ihre APP mit anderen Diensten zu verbinden. Mithilfe von standardmäßigen HTTP-Protokollen können auch ältere apps problemlos geändert werden, um Event Grid-Nachrichten zu veröffentlichen. Webhooks stehen anderen Diensten und Plattformen zur Verfügung, um Event Grid-Nachrichten zu verarbeiten.

### <a name="serverless-apps"></a>Server Lose apps

![Server Lose apps](./media/serverless-apps.png)

Event Grid können Azure Functions, Logic Apps oder ihren eigenen benutzerdefinierten Code auslöst. Ein großer Vorteil der Verwendung von Event Grid besteht darin, dass ein *Push* -Mechanismus verwendet wird, um Nachrichten zu senden, wenn Ereignisse auftreten. Die pusharchitektur beansprucht weniger Ressourcen und skaliert besser als Abruf Mechanismen. Der Abruf muss in regelmäßigen Abständen nach Updates suchen.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Event Grid im Vergleich zu anderen Azure-Messaging Diensten

Azure bietet mehrere Messaging Dienste, einschließlich [Event Hubs](https://docs.microsoft.com/azure/event-hubs) und [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging). Jede ist so konzipiert, dass Sie einen bestimmten Satz von Anwendungsfällen adressiert. Das folgende Diagramm bietet eine allgemeine Übersicht über die Unterschiede zwischen den-Diensten.

![Azure-Messaging-Vergleich](./media/azure-messaging-services.png)

Einen ausführlicheren Vergleich finden Sie unter Vergleichen von [Messaging Diensten](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Leistungsziele

Mithilfe Event Grid können Sie die folgenden Leistungsgarantien nutzen:

* End-to-End-Latenzzeit im 99. Perzentil.
* 99,99% Verfügbarkeit.
* 10 Millionen Ereignisse pro Sekunde pro Region.
* 100 Millionen-Abonnements pro Region.
* 50-ms-Verleger Latenz.
* 24-Stunden-Wiederholung mit exponentiellem Backoff für garantierte Übermittlung im 1-tägigen Fenster.
* Transparentes regionales Failover.

## <a name="event-grid-schema"></a>Event Grid-Schema

Event Grid verwendet ein Standardschema, um benutzerdefinierte Ereignisse zu wrappen. Das Schema ist wie ein Umschlag, der das benutzerdefinierte Datenelement umschließt. Im folgenden finden Sie ein Beispiel Event Grid Meldung:

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

Alles über die Nachricht ist standardmäßig mit `data` Ausnahme der-Eigenschaft. Sie können die Meldung `eventType` `dataVersion` überprüfen und verwenden, um den benutzerdefinierten Teil der Nutzlast zu deserialisieren.

## <a name="azure-resources"></a>Azure-Ressourcen

Ein großer Vorteil der Verwendung von Event Grid sind die von Azure erzeugten automatischen Nachrichten. In Azure werden Ressourcen automatisch in einem *Thema* veröffentlicht, mit dem Sie verschiedene Ereignisse abonnieren können. In der folgenden Tabelle werden die Ressourcentypen, Nachrichten Typen und Ereignisse aufgelistet, die automatisch verfügbar sind.

| Azure-Ressource | Ereignistyp | Beschreibung |
| -------------- | ---------- | ----------- |
| Azure-Abonnement | Microsoft.Resources.ResourceWriteSuccess | Wird ausgelöst, wenn ein Vorgang zum Erstellen oder Aktualisieren einer Ressource erfolgreich ist. |
| | Microsoft.Resources.ResourceWriteFailure | Wird ausgelöst, wenn ein Vorgang zum Erstellen oder Aktualisieren einer Ressource fehlschlägt. |
| | Microsoft.Resources.ResourceWriteCancel | Wird ausgelöst, wenn ein Vorgang zum Erstellen oder Aktualisieren einer Ressource abgebrochen wird. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Wird ausgelöst, wenn ein Löschvorgang einer Ressource erfolgreich ist. |
|  | Microsoft.Resources.ResourceDeleteFailure | Wird ausgelöst, wenn ein Löschvorgang einer Ressource fehlschlägt. |
| | Microsoft.Resources.ResourceDeleteCancel | Wird ausgelöst, wenn ein Vorgang zum Löschen einer Ressource abgebrochen wird. Dieses Ereignis tritt auf, wenn eine Vorlagen Bereitstellung abgebrochen wird. |
| Blobspeicher | Microsoft.Storage.BlobCreated | Wird ausgelöst, wenn ein BLOB erstellt wird. |
| | Microsoft.Storage.BlobDeleted | Wird ausgelöst, wenn ein BLOB gelöscht wird. |
| Event Hubs | Microsoft.EventHub.CaptureFileCreated | Wird ausgelöst, wenn eine Erfassungs Datei erstellt wird.
| IoT Hub | Microsoft.Devices.DeviceCreated | Wird veröffentlicht, wenn ein Gerät bei einem IOT Hub registriert wird. |
| | Microsoft.Devices.DeviceDeleted | Wird veröffentlicht, wenn ein Gerät aus einem IOT Hub gelöscht wird. |
| Ressourcengruppen | Microsoft.Resources.ResourceWriteSuccess | Wird ausgelöst, wenn ein Vorgang zum Erstellen oder Aktualisieren einer Ressource erfolgreich ist. |
| | Microsoft.Resources.ResourceWriteFailure | Wird ausgelöst, wenn ein Vorgang zum Erstellen oder Aktualisieren einer Ressource fehlschlägt. |
| | Microsoft.Resources.ResourceWriteCancel | Wird ausgelöst, wenn ein Vorgang zum Erstellen oder Aktualisieren einer Ressource abgebrochen wird. |
| | Microsoft.Resources.ResourceDeleteSuccess | Wird ausgelöst, wenn ein Löschvorgang einer Ressource erfolgreich ist. |
| | Microsoft.Resources.ResourceDeleteFailure | Wird ausgelöst, wenn ein Löschvorgang einer Ressource fehlschlägt. |
| | Microsoft.Resources.ResourceDeleteCancel | Wird ausgelöst, wenn ein Vorgang zum Löschen einer Ressource abgebrochen wird. Dieses Ereignis tritt auf, wenn eine Vorlagen Bereitstellung abgebrochen wird. |

Weitere Informationen finden Sie unter [Azure Event Grid-Ereignis Schema](https://docs.microsoft.com/azure/event-grid/event-schema).

Sie können von jedem Anwendungstyp aus auf Event Grid zugreifen, auch auf einem lokalen Standort.

## <a name="conclusion"></a>Schlussbemerkung

In diesem Kapitel haben Sie die Azure-Server lose Plattform kennengelernt, die aus Azure Functions, Logic apps und Event Grid besteht. Sie können diese Ressourcen verwenden, um eine vollständig Server lose App-Architektur zu erstellen oder eine Hybridlösung zu erstellen, die mit anderen cloudressourcen und lokalen Servern interagiert. In Kombination mit einer Server losen Datenplattform wie [Azure SQL](https://docs.microsoft.com/azure/sql-database) oder [cosmosdb](https://docs.microsoft.com/azure/cosmos-db/introduction)können Sie vollständig verwaltete native cloudbasierte Anwendungen erstellen.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Application Insights Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Azure Bringen Sie Ihre APP mit Server losem Azure Functions in die Cloud.](https://channel9.msdn.com/events/Connect/2017/E102)
* [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
* [Azure Event Grid-Ereignis Schema](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Azure-Event Hubs](https://docs.microsoft.com/azure/event-hubs)
* [Dokumentation zu Azure Functions](https://docs.microsoft.com/azure/azure-functions)
* [Konzepte von Azure Functions Triggern und Bindungen](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
* [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
* [Azure-Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [Vergleichen von Funktionen 1. x und 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [Herstellen einer Verbindung mit lokalen Datenquellen mit dem lokalen Azure-Daten Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Erstellen Sie Ihre erste Funktion im Azure-Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Erstellen Sie Ihre erste Funktion mit dem Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Erstellen Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [Von Functions unterstützte Sprachen](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Arbeiten mit Azure-Funktionsproxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Zurück](logic-apps.md)
>[Weiter](durable-azure-functions.md)
