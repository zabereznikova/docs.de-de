---
title: Application Insights Server Lose apps
description: Application Insights ist eine Server lose Diagnoseplattform, mit der Entwickler Probleme in Web-Apps, mobilen apps, Desktop-Apps und-Diensten erkennen, selektiviere und diagnostizieren können.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 1f5b99fba448c2c1c12139524ffdcd3708b3c956
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577723"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="2b62b-103">Telemetrie mit Application Insights</span><span class="sxs-lookup"><span data-stu-id="2b62b-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="2b62b-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) ist eine Server lose Diagnoseplattform, mit der Entwickler Probleme in Web-Apps, mobilen apps, Desktop-Apps und-Diensten erkennen, selektiviere und diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="2b62b-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="2b62b-105">Sie können Application Insights für Funktionen-Apps aktivieren, indem Sie einfach einen Switch im Portal kippen.</span><span class="sxs-lookup"><span data-stu-id="2b62b-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="2b62b-106">Application Insights bietet alle diese Funktionen, ohne dass Sie einen Server konfigurieren oder eine eigene Datenbank einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="2b62b-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="2b62b-107">Alle Application Insights-Funktionen werden als Dienst bereitgestellt, der automatisch in ihre Apps integriert wird.</span><span class="sxs-lookup"><span data-stu-id="2b62b-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Application Insights Logo](./media/application-insights-logo.png)

<span data-ttu-id="2b62b-109">Das Hinzufügen von Application Insights zu vorhandenen apps ist so einfach wie das Hinzufügen eines Instrumentierungs Schlüssels zu den Einstellungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2b62b-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="2b62b-110">Mit Application Insights können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="2b62b-110">With Application Insights you can:</span></span>

* <span data-ttu-id="2b62b-111">Erstellen von benutzerdefinierten Diagrammen und Warnungen auf der Grundlage von Metriken, wie z. b. der Anzahl von Funktionsaufrufen, der zum Ausführen einer Funktion benötigte Zeit und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2b62b-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="2b62b-112">Analysieren von Fehlern und Server Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2b62b-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="2b62b-113">Führen Sie einen Drilldown für die Leistung durch, und Messen Sie die Zeit, die zum Aufrufen von Drittanbieter Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="2b62b-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="2b62b-114">Überwachen der CPU-Auslastung, des Arbeitsspeichers und der Raten auf allen Servern, auf denen ihre Funktionen-apps</span><span class="sxs-lookup"><span data-stu-id="2b62b-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="2b62b-115">Einen Livestream mit Metriken anzeigen, einschließlich der Anforderungs Anzahl und Latenz für ihre Funktionen-apps</span><span class="sxs-lookup"><span data-stu-id="2b62b-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="2b62b-116">Verwenden von [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) zum Durchsuchen, Abfragen und Erstellen von benutzerdefinierten Diagrammen über die Funktionsdaten</span><span class="sxs-lookup"><span data-stu-id="2b62b-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Metrik-Explorer](./media/metrics-explorer.png)

<span data-ttu-id="2b62b-118">Zusätzlich zu den integrierten Telemetriedaten ist es auch möglich, benutzerdefinierte Telemetriedaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2b62b-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="2b62b-119">Der folgende Code Ausschnitt erstellt einen benutzerdefinierten telemetrieclient mit dem Instrumentierungs Schlüssel für die Funktionen-App:</span><span class="sxs-lookup"><span data-stu-id="2b62b-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="2b62b-120">Der folgende Code misst, wie lange es dauert, eine neue Zeile in eine [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) -Instanz einzufügen:</span><span class="sxs-lookup"><span data-stu-id="2b62b-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="2b62b-121">Das resultierende Leistungsdiagramm wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="2b62b-121">The resulting performance graph is shown:</span></span>

![Benutzerdefinierte Telemetrie](./media/custom-telemetry.png)

<span data-ttu-id="2b62b-123">Die benutzerdefinierte Telemetrie zeigt die durchschnittliche Zeit für das Einfügen einer neuen Zeile 32,6 Millisekunden an.</span><span class="sxs-lookup"><span data-stu-id="2b62b-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="2b62b-124">Application Insights bietet eine leistungsfähige und bequeme Möglichkeit, ausführliche Telemetriedaten über Ihre Server losen Anwendungen zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="2b62b-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="2b62b-125">Sie haben die vollständige Kontrolle über die Ebene der bereitgestellten Ablauf Verfolgung und Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="2b62b-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="2b62b-126">Sie können benutzerdefinierte Statistiken, z. b. Ereignisse, Abhängigkeiten und die Seitenansicht, nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="2b62b-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="2b62b-127">Zum Schluss ermöglichen Ihnen die leistungsstarken Analysen das Schreiben von Abfragen, die wichtige Fragen stellen und Diagramme sowie erweiterte Einblicke generieren.</span><span class="sxs-lookup"><span data-stu-id="2b62b-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="2b62b-128">Weitere Informationen finden Sie unter [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="2b62b-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2b62b-129">[Zurück](azure-functions.md)
>[Weiter](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="2b62b-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
