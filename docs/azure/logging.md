---
title: Protokollieren mit dem Azure SDK für .NET
description: In diesem Artikel erfahren Sie, wie Sie die Protokollierung mit dem Azure SDK für .NET-Clientbibliotheken einrichten.
ms.date: 03/20/2020
ms.custom: devx-track-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: 6adc485867e9bad401a15da19e6cb4424d2ddb13
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700709"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="506b4-103">Protokollieren mit dem Azure SDK für .NET</span><span class="sxs-lookup"><span data-stu-id="506b4-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="506b4-104">Mit dem [Azure SDK-](https://azure.microsoft.com/downloads/) für .NET-Clientbibliotheken können Sie die Vorgänge in Clientbibliotheken protokollieren.</span><span class="sxs-lookup"><span data-stu-id="506b4-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="506b4-105">Dies ermöglicht es Ihnen, E/A-Anforderungen und -Antworten zu überwachen, die Clientbibliotheken an Azure-Dienste senden.</span><span class="sxs-lookup"><span data-stu-id="506b4-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="506b4-106">In der Regel werden die Protokolle verwendet, um Kommunikationsprobleme zu debuggen oder zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="506b4-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="506b4-107">In diesem Artikel werden drei Ansätze beschrieben, mit denen sich die Protokollierung mit dem Azure SDK für .NET konfigurieren lässt:</span><span class="sxs-lookup"><span data-stu-id="506b4-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="506b4-108">Protokollieren im Konsolenfenster</span><span class="sxs-lookup"><span data-stu-id="506b4-108">Log to the console window</span></span>
- <span data-ttu-id="506b4-109">Protokollieren in .NET- Diagnoseablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="506b4-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="506b4-110">Konfigurieren einer benutzerdefinierten Protokollierung</span><span class="sxs-lookup"><span data-stu-id="506b4-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="506b4-111">Dieser Artikel bezieht sich auf die Clientbibliotheken, die die neuesten Versionen des Azure SDK für .NET verwenden.</span><span class="sxs-lookup"><span data-stu-id="506b4-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="506b4-112">Informationen dazu, ob eine Bibliothek unterstützt wird, finden Sie in der Liste mit den [neuesten Azure SDK-Releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span><span class="sxs-lookup"><span data-stu-id="506b4-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="506b4-113">Wenn Ihre Anwendung eine ältere Version der Azure SDK-Clientbibliotheken verwendet, finden Sie entsprechende Anweisungen in der jeweiligen Dienstdokumentation.</span><span class="sxs-lookup"><span data-stu-id="506b4-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="506b4-114">Protokollieren von Informationen</span><span class="sxs-lookup"><span data-stu-id="506b4-114">Log information</span></span>

<span data-ttu-id="506b4-115">Das SDK protokolliert die folgenden Informationen und bereinigt die Abfrage- und Headerwerte der Parameter, um personenbezogene Daten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="506b4-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="506b4-116">Protokolleintrag der HTTP-Anforderung:</span><span class="sxs-lookup"><span data-stu-id="506b4-116">HTTP request log entry:</span></span>

- <span data-ttu-id="506b4-117">Eindeutige ID</span><span class="sxs-lookup"><span data-stu-id="506b4-117">Unique ID</span></span>
- <span data-ttu-id="506b4-118">HTTP-Methode</span><span class="sxs-lookup"><span data-stu-id="506b4-118">HTTP method</span></span>
- <span data-ttu-id="506b4-119">URI</span><span class="sxs-lookup"><span data-stu-id="506b4-119">URI</span></span>
- <span data-ttu-id="506b4-120">Ausgehende Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="506b4-120">Outgoing request headers</span></span>

<span data-ttu-id="506b4-121">Protokolleintrag der HTTP-Antwort:</span><span class="sxs-lookup"><span data-stu-id="506b4-121">HTTP response log entry:</span></span>

- <span data-ttu-id="506b4-122">Dauer des E/A-Vorgangs (verstrichene Zeit)</span><span class="sxs-lookup"><span data-stu-id="506b4-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="506b4-123">Anfrage-ID</span><span class="sxs-lookup"><span data-stu-id="506b4-123">Request ID</span></span>
- <span data-ttu-id="506b4-124">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="506b4-124">HTTP status code</span></span>
- <span data-ttu-id="506b4-125">HTTP-Ursachentext</span><span class="sxs-lookup"><span data-stu-id="506b4-125">HTTP reason phrase</span></span>
- <span data-ttu-id="506b4-126">Antwortheader</span><span class="sxs-lookup"><span data-stu-id="506b4-126">Response headers</span></span>
- <span data-ttu-id="506b4-127">Fehlerinformationen, falls verfügbar</span><span class="sxs-lookup"><span data-stu-id="506b4-127">Error information, when applicable</span></span>

<span data-ttu-id="506b4-128">Bezüglich des Anforderung- und Antwortinhalts:</span><span class="sxs-lookup"><span data-stu-id="506b4-128">For request and response content:</span></span>

- <span data-ttu-id="506b4-129">Ob im Inhaltsdatenstrom Text oder Byte übertragen werden, ist abhängig vom Header „Content-Type“.</span><span class="sxs-lookup"><span data-stu-id="506b4-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="506b4-130">[!HINWEIS] Die Inhaltsprotokollierung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="506b4-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="506b4-131">Legen Sie `Diagnostics.IsLoggingContentEnabled` in `ClientOptions` auf `true` fest, um diese zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="506b4-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="506b4-132">Ereignisprotokolle werden in der Regel auf einer der folgenden drei Ebenen ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="506b4-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="506b4-133">Informationell, für Anforderungs- und Antwortereignisse</span><span class="sxs-lookup"><span data-stu-id="506b4-133">Informational for request and response events</span></span>
- <span data-ttu-id="506b4-134">Warnungen, für Fehler</span><span class="sxs-lookup"><span data-stu-id="506b4-134">Warning for errors</span></span>
- <span data-ttu-id="506b4-135">Ausführlich, für detaillierte Meldungen und die Inhaltsprotokollierung</span><span class="sxs-lookup"><span data-stu-id="506b4-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="506b4-136">Aktivieren der Protokollierung mit integrierten Methoden</span><span class="sxs-lookup"><span data-stu-id="506b4-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="506b4-137">Das Azure SDK für .NET-Clientbibliotheken protokolliert Ereignisse in der Ereignisablaufverfolgung für Windows über die [Klasse `EventSource`](/dotnet/api/system.diagnostics.tracing.eventsource), die typisch für .NET ist.</span><span class="sxs-lookup"><span data-stu-id="506b4-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="506b4-138">Mit Ereignisquellen können Sie die strukturierte Protokollierung in Ihrem Anwendungscode mit minimalem Leistungsmehraufwand verwenden.</span><span class="sxs-lookup"><span data-stu-id="506b4-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="506b4-139">Sie müssen nur die Ereignislistener registrieren, um Zugriff auf diese Ereignisprotokolle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="506b4-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="506b4-140">Das SDK enthält die Klasse `Azure.Core.Diagnostics.AzureEventSourceListener` (definiert im NuGet-Paket „Azure.Core“), die zwei statische Methoden enthält, die die umfassende Protokollierung für Ihre .NET-Anwendung vereinfachen: `CreateConsoleLogger` und `CreateTraceLogger`.</span><span class="sxs-lookup"><span data-stu-id="506b4-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="506b4-141">Diese Methoden nehmen einen optionalen Parameter, der eine Protokollebene angibt.</span><span class="sxs-lookup"><span data-stu-id="506b4-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="506b4-142">Protokollieren im Konsolenfenster</span><span class="sxs-lookup"><span data-stu-id="506b4-142">Log to the console window</span></span>

<span data-ttu-id="506b4-143">Eine der Hauptfunktionen des Azure SDK für .NET-Clientbibliotheken besteht darin, die Anzeige von umfassenden Protokollen in Echtzeit zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="506b4-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="506b4-144">Mit der Methode `CreateConsoleLogger` können Sie Protokolle mit einer einzelnen Codezeile an das Konsolenfenster senden:</span><span class="sxs-lookup"><span data-stu-id="506b4-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="506b4-145">Protokollieren in Diagnoseablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="506b4-145">Log to diagnostic traces</span></span>

<span data-ttu-id="506b4-146">Wenn Sie Ablaufverfolgungslistener implementieren, können Sie mit der Methode `CreateTraceLogger` in der standardmäßigen .NET-Ereignisablaufverfolgung ([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing)) protokollieren.</span><span class="sxs-lookup"><span data-stu-id="506b4-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="506b4-147">Weitere Informationen zur Ereignisablaufverfolgung in .NET finden Sie unter [Ablaufverfolgungslistener](../framework/debug-trace-profile/trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="506b4-147">For more information on event tracing in .NET, see [Trace Listeners](../framework/debug-trace-profile/trace-listeners.md).</span></span> <span data-ttu-id="506b4-148">In diesem Beispiel wird die Protokollebene „Ausführlich“ dargestellt:</span><span class="sxs-lookup"><span data-stu-id="506b4-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="506b4-149">Konfigurieren der benutzerdefinierten Protokollierung</span><span class="sxs-lookup"><span data-stu-id="506b4-149">Configure custom logging</span></span>

<span data-ttu-id="506b4-150">Wie bereits erwähnt, müssen Sie Ereignislistener registrieren, um vom Azure SDK für .NET Protokollmeldungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="506b4-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="506b4-151">Wenn Sie die umfassende Protokollierung nicht mithilfe der oben genannten vereinfachten Methoden implementieren möchten, können Sie eine Instanz der Klasse `AzureEventSourceListener` erstellen und ihr eine Rückruffunktion übergeben, die Sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="506b4-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="506b4-152">Diese Methode empfängt Protokollmeldungen, die Sie nach Bedarf verarbeiten lassen können.</span><span class="sxs-lookup"><span data-stu-id="506b4-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="506b4-153">Wenn Sie die Instanz erstellen, können Sie außerdem die zu berücksichtigenden Protokollebenen angeben.</span><span class="sxs-lookup"><span data-stu-id="506b4-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="506b4-154">Im folgenden Beispiel wird ein Ereignislistener erstellt, der mit einer benutzerdefinierten Meldung in der Konsole protokolliert und nach wichtigen Azure-Ereignissen der Ebene „Ausführlich“ gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="506b4-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a><span data-ttu-id="506b4-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="506b4-155">Next steps</span></span>

- [<span data-ttu-id="506b4-156">Aktivieren der Diagnoseprotokollierung für Apps in Azure App Service</span><span class="sxs-lookup"><span data-stu-id="506b4-156">Enable diagnostics logging for apps in Azure App Service</span></span>](/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="506b4-157">Sehen Sie sich die Optionen unter [Azure-Sicherheitsprotokollierung und -Überwachung](/azure/security/fundamentals/log-audit) an.</span><span class="sxs-lookup"><span data-stu-id="506b4-157">Review [Azure security logging and auditing](/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="506b4-158">Machen Sie sich mit dem Umgang mit den [Protokollen der Azure-Plattform](/azure/azure-monitor/platform/platform-logs-overview) vertraut.</span><span class="sxs-lookup"><span data-stu-id="506b4-158">Learn how to work with [Azure platform logs](/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="506b4-159">Lesen Sie auch den Artikel [Protokollierung und Ablaufverfolgung mit .NET Core](../core/diagnostics/logging-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="506b4-159">Read more about [.NET Core logging and tracing](../core/diagnostics/logging-tracing.md)</span></span>
