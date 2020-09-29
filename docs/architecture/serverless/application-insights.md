---
title: 'Application Insights: Serverlose Apps'
description: Application Insights ist eine serverlose Diagnoseplattform, die es Entwicklern ermöglicht, Probleme in Web-Apps, mobilen Apps, Desktop-Apps und Microservices zu erkennen, zu testen und zu diagnostizieren.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 42791b052ebb068c9b7109291e66b30b47e5821f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173320"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="02a0b-103">Telemetrie mit Application Insights</span><span class="sxs-lookup"><span data-stu-id="02a0b-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="02a0b-104">[Application Insights](/azure/application-insights) ist eine serverlose Diagnoseplattform, die es Entwicklern ermöglicht, Probleme in Web-Apps, mobilen Apps, Desktop-Apps und Microservices zu erkennen, zu testen und zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="02a0b-104">[Application Insights](/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="02a0b-105">Sie können Application Insights für Funktions-Apps aktivieren, indem Sie einfach einen Schalter im Portal umlegen.</span><span class="sxs-lookup"><span data-stu-id="02a0b-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="02a0b-106">Application Insights bietet alle diese Funktionen, ohne dass Sie einen Server konfigurieren oder eine eigene Datenbank einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="02a0b-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="02a0b-107">Alle Funktionen von Application Insights werden als Dienst bereitgestellt, der automatisch in Ihre Apps integriert wird.</span><span class="sxs-lookup"><span data-stu-id="02a0b-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Application Insights-Logo](./media/application-insights-logo.png)

<span data-ttu-id="02a0b-109">Das Hinzufügen von Application Insights zu vorhandenen Apps ist so einfach wie das Hinzufügen eines Instrumentierungsschlüssels zu den Einstellungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="02a0b-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="02a0b-110">Mit Application Insights können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="02a0b-110">With Application Insights you can:</span></span>

- <span data-ttu-id="02a0b-111">Erstellen von benutzerdefinierten Diagrammen und Warnungen auf der Grundlage von Metriken, etwa der Anzahl von Funktionsaufrufen, der zum Ausführen einer Funktion benötigte Zeit und aufgetretenen Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="02a0b-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="02a0b-112">Analysieren von Fehlern und Serverausnahmen.</span><span class="sxs-lookup"><span data-stu-id="02a0b-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="02a0b-113">Ausführen eines Drilldowns für die Leistung nach Vorgang und Messen der Zeit, die zum Aufrufen von Drittanbieterabhängigkeiten benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="02a0b-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="02a0b-114">Überwachen der CPU-Auslastung, des Arbeitsspeichers und der Raten auf allen Servern, die Ihre Funktions-Apps hosten.</span><span class="sxs-lookup"><span data-stu-id="02a0b-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="02a0b-115">Anzeigen eines Livestreams der Metriken einschließlich der Anforderungsanzahl und Latenz für Ihre Funktions-Apps.</span><span class="sxs-lookup"><span data-stu-id="02a0b-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="02a0b-116">Verwenden von [Analysen](/azure/application-insights/app-insights-analytics), um benutzerdefinierte Diagramme für Ihre Funktionsdaten zu durchsuchen, abzufragen und zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="02a0b-116">Use [Analytics](/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Metrik-Explorer](./media/metrics-explorer.png)

<span data-ttu-id="02a0b-118">Zusätzlich zu den integrierten Telemetriefunktionen ist es auch möglich, benutzerdefinierte Telemetriedaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="02a0b-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="02a0b-119">Der folgende Codeausschnitt erstellt einen benutzerdefinierten Telemetrieclient mit dem für die Funktions-App festgelegten Instrumentierungsschlüssel:</span><span class="sxs-lookup"><span data-stu-id="02a0b-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="02a0b-120">Der folgende Code misst, wie lange es dauert, eine neue Zeile in eine [Azure Table Storage](/azure/cosmos-db/table-storage-overview)-Instanz einzufügen:</span><span class="sxs-lookup"><span data-stu-id="02a0b-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="02a0b-121">Das sich ergebende Leistungsdiagramm wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="02a0b-121">The resulting performance graph is shown:</span></span>

![Benutzerdefinierte Telemetrie](./media/custom-telemetry.png)

<span data-ttu-id="02a0b-123">Die benutzerdefinierte Telemetrie zeigt an, dass die durchschnittliche Zeit für das Einfügen einer neuen Zeile 32,6 Millisekunden beträgt.</span><span class="sxs-lookup"><span data-stu-id="02a0b-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="02a0b-124">Application Insights bietet eine leistungsfähige und bequeme Möglichkeit, ausführliche Telemetriedaten zu Ihren serverlosen Anwendungen zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="02a0b-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="02a0b-125">Sie haben die vollständige Kontrolle über den Grad der bereitgestellten Ablaufverfolgung und Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="02a0b-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="02a0b-126">Sie können benutzerdefinierte Statistiken wie Ereignisse, Abhängigkeiten und die Seitenansicht nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="02a0b-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="02a0b-127">Schließlich ermöglichen Ihnen die leistungsstarken Analysen das Schreiben von Abfragen, die wichtige Fragen stellen und Diagramme sowie erweiterte Einblicke generieren.</span><span class="sxs-lookup"><span data-stu-id="02a0b-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="02a0b-128">Weitere Informationen finden Sie unter [Überwachen von Azure Functions](/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="02a0b-128">For more information, see [Monitor Azure Functions](/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="02a0b-129">[Zurück](azure-functions.md)
>[Weiter](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="02a0b-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
