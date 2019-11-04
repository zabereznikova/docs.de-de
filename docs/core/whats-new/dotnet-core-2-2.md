---
title: Neuerungen in .NET Core 2.2
description: Informationen zu den neuen Features in .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: 917b51e0cf36cca45135fda4a084eb2bca62e835
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100690"
---
# <a name="whats-new-in-net-core-22"></a><span data-ttu-id="315ee-103">Neuerungen in .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="315ee-103">What's new in .NET Core 2.2</span></span>

<span data-ttu-id="315ee-104">.NET Core 2.2 enthält Verbesserungen für die Anwendungsbereitstellung, für die Ereignisbehandlung für Runtimedienste, für die Authentifizierung bei Azure SQL-Datenbanken, für die JIT-Compilerleistung und bei der Codeeinführung vor dem Einfügen der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="315ee-104">.NET Core 2.2 includes enhancements in application deployment, event handling for runtime services, authentication to Azure SQL databases, JIT compiler performance, and code injection prior to the execution of the `Main` method.</span></span>

## <a name="new-deployment-mode"></a><span data-ttu-id="315ee-105">Neuer Bereitstellungsmodus</span><span class="sxs-lookup"><span data-stu-id="315ee-105">New deployment mode</span></span>

<span data-ttu-id="315ee-106">Ab .NET Core 2.2 können Sie [frameworkabhängige ausführbare Dateien](../deploying/index.md#framework-dependent-executables-fde) bereitstellen, die **.exe**-Dateien anstelle von **.dll**-Dateien sind.</span><span class="sxs-lookup"><span data-stu-id="315ee-106">Starting with .NET Core 2.2, you can deploy [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde), which are **.exe** files instead of **.dll** files.</span></span> <span data-ttu-id="315ee-107">Frameworkabhängige ausführbare Dateien (FDE) funktionieren ähnlich wie frameworkabhängige Bereitstellungen, benötigen aber zur Ausführung eine freigegebene Version von .NET Core für das gesamte System.</span><span class="sxs-lookup"><span data-stu-id="315ee-107">Functionally similar to framework-dependent deployments, framework-dependent executables (FDE) still rely on the presence of a shared system-wide version of .NET Core to run.</span></span> <span data-ttu-id="315ee-108">Ihre Anwendung enthält nur Code und alle Drittanbieterabhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="315ee-108">Your app contains only your code and any third-party dependencies.</span></span> <span data-ttu-id="315ee-109">Im Gegensatz zu frameworkabhängigen Bereitstellungen sind FDEs plattformspezifisch.</span><span class="sxs-lookup"><span data-stu-id="315ee-109">Unlike framework-dependent deployments, FDEs are platform-specific.</span></span>

<span data-ttu-id="315ee-110">Dieser neue Bereitstellungsmodus hat den entscheidenden Vorteil, dass Sie eine ausführbare Datei anstelle einer Bibliothek erstellen, was bedeutet, dass Sie Ihre Anwendung direkt ausführen können, ohne vorher `dotnet` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="315ee-110">This new deployment mode has the distinct advantage of building an executable instead of a library, which means you can run your app directly without invoking `dotnet` first.</span></span>

## <a name="core"></a><span data-ttu-id="315ee-111">Kernspeicher</span><span class="sxs-lookup"><span data-stu-id="315ee-111">Core</span></span>

<span data-ttu-id="315ee-112">**Behandeln von Ereignissen in Runtimediensten**</span><span class="sxs-lookup"><span data-stu-id="315ee-112">**Handling events in runtime services**</span></span>

<span data-ttu-id="315ee-113">Möglicherweise möchten Sie die Nutzung von Runtimediensten wie GC, JIT und ThreadPool durch Ihre Anwendung überwachen, um zu verstehen, wie sich diese auf Ihre Anwendung auswirken.</span><span class="sxs-lookup"><span data-stu-id="315ee-113">You may often want to monitor your application's use of runtime services, such as the GC, JIT, and ThreadPool, to understand how they impact your application.</span></span><span data-ttu-id="315ee-114"> Auf Windows-Systemen geschieht dies in der Regel durch die Überwachung der ETW-Ereignisse des aktuellen Prozesses.</span><span class="sxs-lookup"><span data-stu-id="315ee-114"> On Windows systems, this is commonly done by monitoring the ETW events of the current process.</span></span><span data-ttu-id="315ee-115"> Obwohl dies weiterhin gut funktioniert, ist es nicht immer möglich, ETW zu verwenden, wenn Sie in einer Umgebung mit niedriger Priorität oder unter Linux oder macOS arbeiten.</span><span class="sxs-lookup"><span data-stu-id="315ee-115"> While this continues to work well, it's not always possible to use ETW if you're running in a low-privilege environment or on Linux or macOS.</span></span> 

<span data-ttu-id="315ee-116">Ab .NET Core 2.2 können CoreCLR-Ereignisse nun über die <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>-Klasse genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="315ee-116">Starting with .NET Core 2.2, CoreCLR events can now be consumed using the <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="315ee-117">Diese Ereignisse beschreiben das Verhalten der Runtimedienste wie GC, JIT-Kompilierung, ThreadPool und Interop.</span><span class="sxs-lookup"><span data-stu-id="315ee-117">These events describe the behavior of such runtime services as GC, JIT, ThreadPool, and interop.</span></span> <span data-ttu-id="315ee-118">Dies sind die gleichen Ereignisse wie bei Teilen des CoreCLR ETW-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="315ee-118">These are the same events that are exposed as part of the CoreCLR ETW provider.</span></span><span data-ttu-id="315ee-119">  Dies ermöglicht es Anwendungen, diese Ereignisse zu verarbeiten oder einen Transportmechanismus zu nutzen, um sie an einen Telemetrieaggregationsdienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="315ee-119">  This allows for applications to consume these events or use a transport mechanism to send them to a telemetry aggregation service.</span></span> <span data-ttu-id="315ee-120">Im folgenden Codebeispiel wird erläutert, wie Sie Ereignisse abonnieren:</span><span class="sxs-lookup"><span data-stu-id="315ee-120">You can see how to subscribe to events in the following code sample:</span></span>

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // Called whenever an EventSource is created.
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // Watch for the .NET runtime EventSource and enable all of its events.
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // Called whenever an event is written.
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // Write the contents of the event to the console.
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```

<span data-ttu-id="315ee-121">.NET Core 2.2 fügt der <xref:System.Diagnostics.Tracing.EventWrittenEventArgs>-Klasse die folgenden beiden Eigenschaften hinzu, um zusätzliche Informationen über ETW-Ereignisse bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="315ee-121">In addition, .NET Core 2.2 adds the following two properties to the <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> class to provide additional information about ETW events:</span></span>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a><span data-ttu-id="315ee-122">Daten</span><span class="sxs-lookup"><span data-stu-id="315ee-122">Data</span></span>

<span data-ttu-id="315ee-123">**AAD-Authentifizierung bei Azure SQL-Datenbanken mit der SqlConnection.AccessToken-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="315ee-123">**AAD authentication to Azure SQL databases with the SqlConnection.AccessToken property**</span></span>

<span data-ttu-id="315ee-124">Ab .NET Core 2.2 kann ein von Azure Active Directory ausgegebenes Zugriffstoken zur Authentifizierung bei einer Azure SQL-Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="315ee-124">Starting with .NET Core 2.2, an access token issued by Azure Active Directory can be used to authenticate to an Azure SQL database.</span></span> <span data-ttu-id="315ee-125">Zur Unterstützung von Zugriffstoken wurde die Eigenschaft <xref:System.Data.SqlClient.SqlConnection.AccessToken> zur <xref:System.Data.SqlClient.SqlConnection>-Klasse hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="315ee-125">To support access tokens, the <xref:System.Data.SqlClient.SqlConnection.AccessToken> property has been added to the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="315ee-126">Um die Vorteile der AAD-Authentifizierung zu nutzen, laden Sie die Version 4.6 des NuGet-Pakets „System.Data.SqlClient“ herunter.</span><span class="sxs-lookup"><span data-stu-id="315ee-126">To take advantage of AAD authentication, download version 4.6 of the System.Data.SqlClient NuGet package.</span></span> <span data-ttu-id="315ee-127">Um dieses Feature zu nutzen, können Sie den Wert des Zugriffstokens über die [Active Directory-Authentifizierungsbibliothek für .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) beziehen, die im NuGet-Paket [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="315ee-127">In order to use the feature, you can obtain the access token value using the [Active Directory Authentication Library for .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contained in the [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet package.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="315ee-128">Verbesserungen am JIT-Compiler</span><span class="sxs-lookup"><span data-stu-id="315ee-128">JIT compiler improvements</span></span>

<span data-ttu-id="315ee-129">**Mehrstufige Kompilierung bleibt ein abonnierbares Feature**</span><span class="sxs-lookup"><span data-stu-id="315ee-129">**Tiered compilation remains an opt-in feature**</span></span>

<span data-ttu-id="315ee-130">Der JIT-Compiler implementierte in .NET Core 2.1 eine neue Compilertechnologie, *mehrstufige Kompilierung*, als abonnierbares Feature.</span><span class="sxs-lookup"><span data-stu-id="315ee-130">In .NET Core 2.1, the JIT compiler implemented a new compiler technology, *tiered compilation*, as an opt-in feature.</span></span> <span data-ttu-id="315ee-131">Damit soll eine Leistungssteigerung erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="315ee-131">The goal of tiered compilation is improved performance.</span></span> <span data-ttu-id="315ee-132">Eine der wichtigen Aufgaben, die vom JIT-Compiler ausgeführt werden, ist die Optimierung der Ausführung des Codes.</span><span class="sxs-lookup"><span data-stu-id="315ee-132">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="315ee-133">Für wenig genutzte Codepfade muss der Compiler jedoch möglicherweise mehr Zeit zur Optimierung des Codes aufbringen, als die Runtime zur Ausführung nicht optimierten Codes benötigt.</span><span class="sxs-lookup"><span data-stu-id="315ee-133">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends executing unoptimized code.</span></span> <span data-ttu-id="315ee-134">Die mehrstufige Kompilierung unterteilt die JIT-Kompilierung in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="315ee-134">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="315ee-135">Eine **erste Stufe**, die so schnell wie möglich Code generiert.</span><span class="sxs-lookup"><span data-stu-id="315ee-135">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="315ee-136">Eine **zweite Stufe**, die optimiertem Code für Methoden generiert, die häufig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="315ee-136">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="315ee-137">Die zweite Stufe der Kompilierung wird parallel zum Verbessern der Leistung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="315ee-137">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="315ee-138">Informationen zur Leistungssteigerung, die sich aus der mehrstufigen Kompilierung ergeben kann, finden Sie unter [Ankündigung zu .NET Core 2.2 Vorschauversion 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="315ee-138">For information on the performance improvement that can result from tiered compilation, see [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span>

<span data-ttu-id="315ee-139">In .NET Core 2.2 Vorschauversion 2 wurde die mehrstufige Kompilierung standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="315ee-139">In .NET Core 2.2 Preview 2, tiered compilation was enabled by default.</span></span> <span data-ttu-id="315ee-140">Allerdings haben wir entschieden, dass wir noch nicht bereit sind, die mehrstufige Kompilierung standardmäßig zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="315ee-140">However, we've decided that we are still not ready to enable tiered compilation by default.</span></span> <span data-ttu-id="315ee-141">Daher bleibt die mehrstufigen Kompilierung in .NET Core 2.2 weiterhin ein abonnierbares Feature.</span><span class="sxs-lookup"><span data-stu-id="315ee-141">So in .NET Core 2.2, tiered compilation continues to be an opt-in feature.</span></span> <span data-ttu-id="315ee-142">Informationen zum Abonnieren der mehrstufigen Kompilierung finden Sie unter [Verbesserungen am Jit-Compiler](dotnet-core-2-1.md#jit-compiler-improvements) in [Neuerungen in .NET Core 2.1](dotnet-core-2-1.md).</span><span class="sxs-lookup"><span data-stu-id="315ee-142">For information on opting in to tiered compilation, see [Jit compiler improvements](dotnet-core-2-1.md#jit-compiler-improvements) in [What's new in .NET Core 2.1](dotnet-core-2-1.md).</span></span>

## <a name="runtime"></a><span data-ttu-id="315ee-143">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="315ee-143">Runtime</span></span>

<span data-ttu-id="315ee-144">**Einfügen von Code vor der Ausführung der Main-Methode**</span><span class="sxs-lookup"><span data-stu-id="315ee-144">**Injecting code prior to executing the Main method**</span></span>

<span data-ttu-id="315ee-145">Ab .NET Core 2.2 können Sie einen Startuphook verwenden, um Code vor der Ausführung der Main-Methode einer Anwendung einzufügen.</span><span class="sxs-lookup"><span data-stu-id="315ee-145">Starting with .NET Core 2.2, you can use a startup hook to inject code prior to running an application's Main method.</span></span> <span data-ttu-id="315ee-146">Startuphooks ermöglichen es einem Host, das Verhalten von Anwendungen nach dem Bereitstellung anzupassen, ohne die Anwendung neu kompilieren oder ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="315ee-146">Startup hooks make it possible for a host to customize the behavior of applications after they have been deployed without needing to recompile or change the application.</span></span>

<span data-ttu-id="315ee-147">Wir erwarten von Hostinganbietern, dass sie benutzerdefinierte Konfigurationen und Richtlinien definieren, einschließlich Einstellungen, die das Ladeverhalten des Haupteinstiegspunktes potenziell beeinflussen, wie beispielsweise das Verhalten  <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="315ee-147">We expect hosting providers to define custom configuration and policy, including settings that potentially influence the load behavior of the main entry point, such as the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> behavior.</span></span> <span data-ttu-id="315ee-148">Der Hook kann verwendet werden, um die Ablaufverfolgung oder Telemetrieinjektion einzurichten, Rückrufe zur Handhabung einzurichten oder um ein anderes umgebungsabhängiges Verhalten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="315ee-148">The hook can be used to set up tracing or telemetry injection, to set up callbacks for handling, or to define other environment-dependent behavior.</span></span> <span data-ttu-id="315ee-149">Der Hook ist vom Einstiegspunkt getrennt, sodass der Benutzercode nicht geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="315ee-149">The hook is separate from the entry point, so that user code doesn't need to be modified.</span></span>

<span data-ttu-id="315ee-150">Weitere Informationen finden Sie unter [Hoststartuphook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md).</span><span class="sxs-lookup"><span data-stu-id="315ee-150">See [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="315ee-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="315ee-151">See also</span></span>

- [<span data-ttu-id="315ee-152">Neuigkeiten in .NET Core</span><span class="sxs-lookup"><span data-stu-id="315ee-152">What's new in .NET Core</span></span>](index.md)
- [<span data-ttu-id="315ee-153">Neuerungen in ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="315ee-153">What's new in ASP.NET Core 2.2</span></span>](/aspnet/core/release-notes/aspnetcore-2.2)
- [<span data-ttu-id="315ee-154">Neue Features in EF Core 2.2</span><span class="sxs-lookup"><span data-stu-id="315ee-154">New features in EF Core 2.2</span></span>](/ef/core/what-is-new/ef-core-2.2)
