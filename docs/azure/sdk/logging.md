---
title: Protokollierung mit dem Azure SDK für .NET
description: Erfahren Sie, wie Sie die Protokollierung mit dem Azure SDK für .NET-Clientbibliotheken aktivieren
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433223"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="e047d-103">Protokollierung mit dem Azure SDK für .NET</span><span class="sxs-lookup"><span data-stu-id="e047d-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="e047d-104">Das [Azure SDK](https://azure.microsoft.com/downloads/) für .NET-Clientbibliotheken bietet die Möglichkeit, Clientbibliotheksvorgänge zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="e047d-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="e047d-105">Auf diese Weise können Sie E/A-Anforderungen und Antworten überwachen, die Clientbibliotheken an Azure-Dienste erstellen.</span><span class="sxs-lookup"><span data-stu-id="e047d-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="e047d-106">In der Regel werden die Protokolle zum Debuggen oder Diagnostizieren von Kommunikationsproblemen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e047d-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="e047d-107">In diesem Artikel werden drei Ansätze beschrieben, um die Protokollierung mit dem Azure SDK für .NET zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="e047d-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="e047d-108">Protokollieren am Konsolenfenster</span><span class="sxs-lookup"><span data-stu-id="e047d-108">Log to the console window</span></span>
- <span data-ttu-id="e047d-109">Protokollieren bei .NET-Diagnoseablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="e047d-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="e047d-110">Konfigurieren der benutzerdefinierten Protokollierung</span><span class="sxs-lookup"><span data-stu-id="e047d-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e047d-111">Dieser Artikel gilt für Clientbibliotheken, die die neuesten Versionen des Azure SDK für .NET verwenden.</span><span class="sxs-lookup"><span data-stu-id="e047d-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="e047d-112">Informationen dazu, ob eine Bibliothek unterstützt wird, finden Sie in der Liste der [neuesten Azure SDK-Versionen](https://azure.github.io/azure-sdk/releases/latest/index.html).</span><span class="sxs-lookup"><span data-stu-id="e047d-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="e047d-113">Wenn Ihre Anwendung eine ältere Version der Azure SDK-Clientbibliotheken verwendet, lesen Sie bestimmte Anweisungen in der entsprechenden Dienstdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e047d-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="e047d-114">Protokollieren von Informationen</span><span class="sxs-lookup"><span data-stu-id="e047d-114">Log information</span></span>

<span data-ttu-id="e047d-115">Das SDK protokolliert die folgenden Informationen, sanitisierende Parameterabfrage und Headerwerte, um persönliche Daten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e047d-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="e047d-116">HTTP-Anforderungsprotokolleintrag:</span><span class="sxs-lookup"><span data-stu-id="e047d-116">HTTP request log entry:</span></span>

- <span data-ttu-id="e047d-117">Eindeutige Kennung</span><span class="sxs-lookup"><span data-stu-id="e047d-117">Unique ID</span></span>
- <span data-ttu-id="e047d-118">HTTP-Methode</span><span class="sxs-lookup"><span data-stu-id="e047d-118">HTTP method</span></span>
- <span data-ttu-id="e047d-119">URI</span><span class="sxs-lookup"><span data-stu-id="e047d-119">URI</span></span>
- <span data-ttu-id="e047d-120">Ausgehende Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e047d-120">Outgoing request headers</span></span>

<span data-ttu-id="e047d-121">HTTP-Antwortprotokolleintrag:</span><span class="sxs-lookup"><span data-stu-id="e047d-121">HTTP response log entry:</span></span>

- <span data-ttu-id="e047d-122">Dauer des E/A-Vorgangs (verstrichene Zeit)</span><span class="sxs-lookup"><span data-stu-id="e047d-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="e047d-123">Anfrage-ID</span><span class="sxs-lookup"><span data-stu-id="e047d-123">Request ID</span></span>
- <span data-ttu-id="e047d-124">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="e047d-124">HTTP status code</span></span>
- <span data-ttu-id="e047d-125">HTTP-Ursachenphrase</span><span class="sxs-lookup"><span data-stu-id="e047d-125">HTTP reason phrase</span></span>
- <span data-ttu-id="e047d-126">Antwortheader</span><span class="sxs-lookup"><span data-stu-id="e047d-126">Response headers</span></span>
- <span data-ttu-id="e047d-127">Fehlerinformationen, falls zutreffend</span><span class="sxs-lookup"><span data-stu-id="e047d-127">Error information, when applicable</span></span>

<span data-ttu-id="e047d-128">Für Anforderungs- und Antwortinhalte:</span><span class="sxs-lookup"><span data-stu-id="e047d-128">For request and response content:</span></span>

- <span data-ttu-id="e047d-129">Content Stream als Text oder Bytes, abhängig vom Content-Type-Header.</span><span class="sxs-lookup"><span data-stu-id="e047d-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="e047d-130">[! HINWEIS: Die Inhaltsprotokollierung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e047d-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="e047d-131">Um sie zu `Diagnostics.IsLoggingContentEnabled` `true` aktivieren, setzen Sie auf in `ClientOptions`.</span><span class="sxs-lookup"><span data-stu-id="e047d-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="e047d-132">Ereignisprotokolle werden in der Regel auf einer der folgenden drei Ebenen ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="e047d-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="e047d-133">Information für Anforderungs- und Antwortereignisse</span><span class="sxs-lookup"><span data-stu-id="e047d-133">Informational for request and response events</span></span>
- <span data-ttu-id="e047d-134">Warnung vor Fehlern</span><span class="sxs-lookup"><span data-stu-id="e047d-134">Warning for errors</span></span>
- <span data-ttu-id="e047d-135">Ausführlich für detaillierte Nachrichten und Inhaltsprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e047d-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="e047d-136">Aktivieren der Protokollierung mit integrierten Methoden</span><span class="sxs-lookup"><span data-stu-id="e047d-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="e047d-137">Das Azure SDK für .NET-Clientbibliotheken protokolliert Ereignisse in Event [ `EventSource` ](/dotnet/api/system.diagnostics.tracing.eventsource)Tracing for Windows (ETW) über die Klasse , die typisch für .NET ist.</span><span class="sxs-lookup"><span data-stu-id="e047d-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="e047d-138">Ereignisquellen ermöglichen die Verwendung strukturierter Protokollierung in Ihrem Anwendungscode mit minimalem Leistungsaufwand.</span><span class="sxs-lookup"><span data-stu-id="e047d-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="e047d-139">Um Zugriff auf diese Ereignisprotokolle zu erhalten, müssen Sie Ereignislistener registrieren.</span><span class="sxs-lookup"><span data-stu-id="e047d-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="e047d-140">Das SDK `Azure.Core.Diagnostics.AzureEventSourceListener` enthält die Klasse (definiert im Azure.Core NuGet-Paket), die zwei statische `CreateConsoleLogger` Methoden `CreateTraceLogger`enthält, die die umfassende Protokollierung für Ihre .NET-Anwendung vereinfachen: und .</span><span class="sxs-lookup"><span data-stu-id="e047d-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="e047d-141">Diese Methoden verwenden einen optionalen Parameter, der eine Protokollebene angibt.</span><span class="sxs-lookup"><span data-stu-id="e047d-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="e047d-142">Protokollieren am Konsolenfenster</span><span class="sxs-lookup"><span data-stu-id="e047d-142">Log to the console window</span></span>

<span data-ttu-id="e047d-143">Ein Kerngrundsatz des Azure SDK für .NET-Clientbibliotheken besteht darin, die Möglichkeit zu vereinfachen, umfassende Protokolle in Echtzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e047d-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="e047d-144">Mit `CreateConsoleLogger` der Methode können Sie Protokolle mit einer einzigen Codezeile an das Konsolenfenster senden:</span><span class="sxs-lookup"><span data-stu-id="e047d-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="e047d-145">Protokollieren zu Diagnoseablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="e047d-145">Log to diagnostic traces</span></span>

<span data-ttu-id="e047d-146">Wenn Sie Ablaufverfolgungslistener `CreateTraceLogger` implementieren, können Sie die Methode verwenden,[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)um sich am standardmäßigen .NET-Ereignisablaufverfolgungsmechanismus ( ) zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="e047d-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="e047d-147">Weitere Informationen zur Ereignisablaufverfolgung in .NET finden Sie unter Ablaufzeichnen von [Listenern](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span><span class="sxs-lookup"><span data-stu-id="e047d-147">For more information on event tracing in .NET, see [Trace Listeners](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="e047d-148">In diesem Beispiel wird eine Protokollebene von ausführlich angegeben:</span><span class="sxs-lookup"><span data-stu-id="e047d-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="e047d-149">Konfigurieren der benutzerdefinierten Protokollierung</span><span class="sxs-lookup"><span data-stu-id="e047d-149">Configure custom logging</span></span>

<span data-ttu-id="e047d-150">Wie oben erwähnt, müssen Sie Ereignislistener registrieren, um Protokollnachrichten vom Azure SDK für .NET zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="e047d-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="e047d-151">Wenn Sie keine umfassende Protokollierung mit einer der oben genannten vereinfachten `AzureEventSourceListener` Methoden implementieren möchten, können Sie eine Instanz der Klasse erstellen und eine Rückruffunktion übergeben, die Sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="e047d-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="e047d-152">Diese Methode empfängt Protokollnachrichten, die Sie nach Bedarf verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="e047d-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="e047d-153">Darüber hinaus können Sie beim Erstellen der Instanz die einzuschließenden Protokollebenen angeben.</span><span class="sxs-lookup"><span data-stu-id="e047d-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="e047d-154">Im folgenden Beispiel wird ein Ereignislistener erstellt, der sich mit einer benutzerdefinierten Nachricht an der Konsole anmeldet und zu Azure-Kernereignissen der Ebene exbose gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="e047d-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="e047d-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e047d-155">Next steps</span></span>

- [<span data-ttu-id="e047d-156">Aktivieren der Diagnoseprotokollierung für Apps in Azure App Service</span><span class="sxs-lookup"><span data-stu-id="e047d-156">Enable diagnostics logging for apps in Azure App Service</span></span>](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="e047d-157">Überprüfen der [Azure-Sicherheitsprotokollierungs- und Überwachungsoptionen](https://docs.microsoft.com/azure/security/fundamentals/log-audit)</span><span class="sxs-lookup"><span data-stu-id="e047d-157">Review [Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="e047d-158">Erfahren Sie, wie Sie mit [Azure-Plattformprotokollen](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) arbeiten</span><span class="sxs-lookup"><span data-stu-id="e047d-158">Learn how to work with [Azure platform logs](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="e047d-159">Weitere Informationen [zu .NET Core-Protokollierung und -Ablaufverfolgung](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span><span class="sxs-lookup"><span data-stu-id="e047d-159">Read more about [.NET Core logging and tracing](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span></span>
