---
title: Application Insights – serverlose apps
description: Application Insights ist eine serverlose Diagnose-Plattform, mit der Entwickler zu erkennen, selektieren und Diagnostizieren von Problemen in Web-apps, mobile apps, desktop-apps und Microservices.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4884d483de07c1c2077f7280b6b77c6059572c0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154256"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="beb19-103">Telemetrie mit Application Insights</span><span class="sxs-lookup"><span data-stu-id="beb19-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="beb19-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) ist eine Plattform für die serverlose Diagnose, mit der Entwickler zu erkennen, selektieren und Diagnostizieren von Problemen in Web-apps, mobilen apps, desktop-apps und Microservices.</span><span class="sxs-lookup"><span data-stu-id="beb19-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="beb19-105">Sie können für Funktionen-apps in Application Insights aktivieren, indem Sie einfach das Umlegen eines Schalters im Portal.</span><span class="sxs-lookup"><span data-stu-id="beb19-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="beb19-106">Application Insights bietet alle Funktionen, ohne dass Sie einen Server konfigurieren, oder richten Sie Ihre eigene Datenbank.</span><span class="sxs-lookup"><span data-stu-id="beb19-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="beb19-107">Alle Application Insights-Funktionen werden als Dienst bereitgestellt, die automatisch mit Ihren apps integriert ist.</span><span class="sxs-lookup"><span data-stu-id="beb19-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Application Insights-logo](./media/application-insights-logo.png)

<span data-ttu-id="beb19-109">Hinzufügen von Application Insights auf vorhandene apps ist so einfach wie das Hinzufügen eines instrumentierungsschlüssels von, um die Einstellungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="beb19-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="beb19-110">Mit Application Insights können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="beb19-110">With Application Insights you can:</span></span>

* <span data-ttu-id="beb19-111">Erstellen Sie benutzerdefinierte Diagramme und Warnungen basierend auf Metriken wie die Anzahl der Aufrufe, die Zeit zum Ausführen einer Funktion und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="beb19-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="beb19-112">Analysieren von Fehlern und Serverausnahmen</span><span class="sxs-lookup"><span data-stu-id="beb19-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="beb19-113">Drilldown in die Leistung von Vorgang aus, und messen die Zeit, die es dauert, rufen Sie die Drittanbieter-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="beb19-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="beb19-114">Überwachen der CPU-Auslastung, Arbeitsspeicher und Gebühren auf allen Servern, die Ihre Funktionen-apps hosten</span><span class="sxs-lookup"><span data-stu-id="beb19-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="beb19-115">Zeigen Sie einen Livestream der Metriken anzeigen, einschließlich der Anzahl der Anforderungen und der Latenz für Ihre Funktions-apps</span><span class="sxs-lookup"><span data-stu-id="beb19-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="beb19-116">Verwendung [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) zum Durchsuchen, Abfragen und erstellen Sie benutzerdefinierte Diagramme für Ihre Funktionsdaten</span><span class="sxs-lookup"><span data-stu-id="beb19-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Metrik-explorer](./media/metrics-explorer.png)

<span data-ttu-id="beb19-118">Zusätzlich zur integrierten Telemetriedaten ist es auch möglich, benutzerdefinierte Telemetriedaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="beb19-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="beb19-119">Der folgende Codeausschnitt erstellt einen benutzerdefinierte Telemetrie-Client mit dem instrumentationsschlüssel, der für die Funktions-app festgelegt:</span><span class="sxs-lookup"><span data-stu-id="beb19-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="beb19-120">Der folgende Code wird gemessen, wie lange es dauert, fügen Sie eine neue Zeile in einer [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) Instanz:</span><span class="sxs-lookup"><span data-stu-id="beb19-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="beb19-121">Das resultierende Leistungsdiagramm wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="beb19-121">The resulting performance graph is shown:</span></span>

![Benutzerdefinierte Telemetrie](./media/custom-telemetry.png)

<span data-ttu-id="beb19-123">Die benutzerdefinierte Telemetrie zeigt an, dass die durchschnittliche Zeit zum Einfügen einer neuen Zeile 32.6 Millisekunden ist.</span><span class="sxs-lookup"><span data-stu-id="beb19-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="beb19-124">Application Insights bietet eine leistungsfähige und bequeme Möglichkeit, detaillierte Telemetriedaten über Ihre serverlosen Anwendungen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="beb19-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="beb19-125">Haben vollständige Kontrolle über die Stufe der Ablaufverfolgung und Protokollierung, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="beb19-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="beb19-126">Sie können benutzerdefinierte Statistiken wie Ereignisse, Abhängigkeiten und Seitenansicht nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="beb19-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="beb19-127">Aktivieren Sie schließlich die leistungsstarken Analysen Sie Abfragen schreiben, die wichtige Fragen stellen und Diagramme und erweiterte Einblicke zu generieren.</span><span class="sxs-lookup"><span data-stu-id="beb19-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="beb19-128">Weitere Informationen finden Sie unter [Überwachen von Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="beb19-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="beb19-129">[Zurück](azure-functions.md)
>[Weiter](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="beb19-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>