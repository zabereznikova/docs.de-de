---
title: 'Application Insights: Serverlose Apps'
description: Application Insights ist eine serverlose Diagnoseplattform, die es Entwicklern ermöglicht, Probleme in Web-Apps, mobilen Apps, Desktop-Apps und Microservices zu erkennen, zu testen und zu diagnostizieren.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522746"
---
# <a name="telemetry-with-application-insights"></a>Telemetrie mit Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) ist eine serverlose Diagnoseplattform, die es Entwicklern ermöglicht, Probleme in Web-Apps, mobilen Apps, Desktop-Apps und Microservices zu erkennen, zu testen und zu diagnostizieren. Sie können Application Insights für Funktions-Apps aktivieren, indem Sie einfach einen Schalter im Portal umlegen. Application Insights bietet alle diese Funktionen, ohne dass Sie einen Server konfigurieren oder eine eigene Datenbank einrichten müssen. Alle Funktionen von Application Insights werden als Dienst bereitgestellt, der automatisch in Ihre Apps integriert wird.

![Application Insights-Logo](./media/application-insights-logo.png)

Das Hinzufügen von Application Insights zu vorhandenen Apps ist so einfach wie das Hinzufügen eines Instrumentierungsschlüssels zu den Einstellungen Ihrer Anwendung. Mit Application Insights können Sie folgende Aktionen ausführen:

- Erstellen von benutzerdefinierten Diagrammen und Warnungen auf der Grundlage von Metriken, etwa der Anzahl von Funktionsaufrufen, der zum Ausführen einer Funktion benötigte Zeit und aufgetretenen Ausnahmen.
- Analysieren von Fehlern und Serverausnahmen.
- Ausführen eines Drilldowns für die Leistung nach Vorgang und Messen der Zeit, die zum Aufrufen von Drittanbieterabhängigkeiten benötigt wird.
- Überwachen der CPU-Auslastung, des Arbeitsspeichers und der Raten auf allen Servern, die Ihre Funktions-Apps hosten.
- Anzeigen eines Livestreams der Metriken einschließlich der Anforderungsanzahl und Latenz für Ihre Funktions-Apps.
- Verwenden von [Analysen](https://docs.microsoft.com/azure/application-insights/app-insights-analytics), um benutzerdefinierte Diagramme für Ihre Funktionsdaten zu durchsuchen, abzufragen und zu erstellen.

![Metrik-Explorer](./media/metrics-explorer.png)

Zusätzlich zu den integrierten Telemetriefunktionen ist es auch möglich, benutzerdefinierte Telemetriedaten zu generieren. Der folgende Codeausschnitt erstellt einen benutzerdefinierten Telemetrieclient mit dem für die Funktions-App festgelegten Instrumentierungsschlüssel:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Der folgende Code misst, wie lange es dauert, eine neue Zeile in eine [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)-Instanz einzufügen:

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Das sich ergebende Leistungsdiagramm wird angezeigt:

![Benutzerdefinierte Telemetrie](./media/custom-telemetry.png)

Die benutzerdefinierte Telemetrie zeigt an, dass die durchschnittliche Zeit für das Einfügen einer neuen Zeile 32,6 Millisekunden beträgt.

Application Insights bietet eine leistungsfähige und bequeme Möglichkeit, ausführliche Telemetriedaten zu Ihren serverlosen Anwendungen zu protokollieren. Sie haben die vollständige Kontrolle über den Grad der bereitgestellten Ablaufverfolgung und Protokollierung. Sie können benutzerdefinierte Statistiken wie Ereignisse, Abhängigkeiten und die Seitenansicht nachverfolgen. Schließlich ermöglichen Ihnen die leistungsstarken Analysen das Schreiben von Abfragen, die wichtige Fragen stellen und Diagramme sowie erweiterte Einblicke generieren.

Weitere Informationen finden Sie unter [Überwachen von Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Zurück](azure-functions.md)
>[Weiter](logic-apps.md)
