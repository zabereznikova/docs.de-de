---
title: Application Insights Server Lose apps
description: Application Insights ist eine Server lose Diagnoseplattform, mit der Entwickler Probleme in Web-Apps, mobilen apps, Desktop-Apps und-Diensten erkennen, selektiviere und diagnostizieren können.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522746"
---
# <a name="telemetry-with-application-insights"></a>Telemetrie mit Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) ist eine Server lose Diagnoseplattform, mit der Entwickler Probleme in Web-Apps, mobilen apps, Desktop-Apps und-Diensten erkennen, selektiviere und diagnostizieren können. Sie können Application Insights für Funktionen-Apps aktivieren, indem Sie einfach einen Switch im Portal kippen. Application Insights bietet alle diese Funktionen, ohne dass Sie einen Server konfigurieren oder eine eigene Datenbank einrichten müssen. Alle Application Insights-Funktionen werden als Dienst bereitgestellt, der automatisch in ihre Apps integriert wird.

![Application Insights Logo](./media/application-insights-logo.png)

Das Hinzufügen von Application Insights zu vorhandenen apps ist so einfach wie das Hinzufügen eines Instrumentierungs Schlüssels zu den Einstellungen Ihrer Anwendung. Mit Application Insights können Sie folgende Aktionen ausführen:

- Erstellen von benutzerdefinierten Diagrammen und Warnungen auf der Grundlage von Metriken, wie z. b. der Anzahl von Funktionsaufrufen, der zum Ausführen einer Funktion benötigte Zeit und Ausnahmen
- Analysieren von Fehlern und Server Ausnahmen
- Führen Sie einen Drilldown für die Leistung durch, und Messen Sie die Zeit, die zum Aufrufen von Drittanbieter Abhängigkeiten
- Überwachen der CPU-Auslastung, des Arbeitsspeichers und der Raten auf allen Servern, auf denen ihre Funktionen-apps
- Einen Livestream mit Metriken anzeigen, einschließlich der Anforderungs Anzahl und Latenz für ihre Funktionen-apps
- Verwenden von [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) zum Durchsuchen, Abfragen und Erstellen von benutzerdefinierten Diagrammen über die Funktionsdaten

![Metrik-Explorer](./media/metrics-explorer.png)

Zusätzlich zu den integrierten Telemetriedaten ist es auch möglich, benutzerdefinierte Telemetriedaten zu generieren. Der folgende Code Ausschnitt erstellt einen benutzerdefinierten telemetrieclient mit dem Instrumentierungs Schlüssel für die Funktionen-App:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Der folgende Code misst, wie lange es dauert, eine neue Zeile in eine [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) -Instanz einzufügen:

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Das resultierende Leistungsdiagramm wird angezeigt:

![Benutzerdefinierte Telemetrie](./media/custom-telemetry.png)

Die benutzerdefinierte Telemetrie zeigt die durchschnittliche Zeit für das Einfügen einer neuen Zeile 32,6 Millisekunden an.

Application Insights bietet eine leistungsfähige und bequeme Möglichkeit, ausführliche Telemetriedaten über Ihre Server losen Anwendungen zu protokollieren. Sie haben die vollständige Kontrolle über die Ebene der bereitgestellten Ablauf Verfolgung und Protokollierung. Sie können benutzerdefinierte Statistiken, z. b. Ereignisse, Abhängigkeiten und die Seitenansicht, nachverfolgen. Zum Schluss ermöglichen Ihnen die leistungsstarken Analysen das Schreiben von Abfragen, die wichtige Fragen stellen und Diagramme sowie erweiterte Einblicke generieren.

Weitere Informationen finden Sie unter [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Zurück](azure-functions.md)
>[Weiter](logic-apps.md)
