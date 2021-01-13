---
title: Protokollierung und Ablaufverfolgung – .NET Core
description: Eine Einführung in die Protokollierung und Ablaufverfolgung mit .NET Core.
ms.date: 10/12/2020
ms.openlocfilehash: fac8eeed63e8737ad42699d81b421747b207c69a
ms.sourcegitcommit: 35ca2255c6c86968eaef9e3a251c9739ce8e4288
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2020
ms.locfileid: "97753626"
---
# <a name="net-core-logging-and-tracing"></a><span data-ttu-id="237ea-103">Protokollierung und Ablaufverfolgung mit .NET Core</span><span class="sxs-lookup"><span data-stu-id="237ea-103">.NET Core logging and tracing</span></span>

<span data-ttu-id="237ea-104">Protokollierung und Ablaufverfolgung sind eigentlich zwei Bezeichnungen für dieselbe Technik.</span><span class="sxs-lookup"><span data-stu-id="237ea-104">Logging and tracing are really two names for the same technique.</span></span> <span data-ttu-id="237ea-105">Diese einfache Technik wurde seit den Frühzeiten der Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="237ea-105">The simple technique has been used since the early days of computers.</span></span> <span data-ttu-id="237ea-106">Sie umfasst einfach das Instrumentieren einer Anwendung zum Schreiben einer Ausgabe, die später verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="237ea-106">It simply involves instrumenting an application to write output to be consumed later.</span></span>

## <a name="reasons-to-use-logging-and-tracing"></a><span data-ttu-id="237ea-107">Gründe für die Verwendung von Protokollierung und Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="237ea-107">Reasons to use logging and tracing</span></span>

<span data-ttu-id="237ea-108">Diese einfache Technik ist überraschend leistungsfähig.</span><span class="sxs-lookup"><span data-stu-id="237ea-108">This simple technique is surprisingly powerful.</span></span> <span data-ttu-id="237ea-109">Sie kann in Situationen verwendet werden, in denen ein Debugger versagt:</span><span class="sxs-lookup"><span data-stu-id="237ea-109">It can be used in situations where a debugger fails:</span></span>

- <span data-ttu-id="237ea-110">Probleme, die über einen längeren Zeitraum auftreten, können mit einem herkömmlichen Debugger schwierig zu debuggen sein.</span><span class="sxs-lookup"><span data-stu-id="237ea-110">Issues occurring over long periods of time, can be difficult to debug with a traditional debugger.</span></span> <span data-ttu-id="237ea-111">Protokolle ermöglichen eine ausführliche nachträgliche Überprüfung über einen längeren Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="237ea-111">Logs allow for detailed post-mortem review spanning long periods of time.</span></span> <span data-ttu-id="237ea-112">Im Gegensatz dazu sind Debugger auf Echtzeitanalysen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="237ea-112">In contrast, debuggers are constrained to real-time analysis.</span></span>
- <span data-ttu-id="237ea-113">Multithreadanwendungen und verteilte Anwendungen sind häufig schwierig zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="237ea-113">Multi-threaded applications and distributed applications are often difficult to debug.</span></span>  <span data-ttu-id="237ea-114">Durch das Anfügen eines Debuggers wird häufig das Verhalten geändert.</span><span class="sxs-lookup"><span data-stu-id="237ea-114">Attaching a debugger tends to modify behaviors.</span></span> <span data-ttu-id="237ea-115">Ausführliche Protokolle können nach Bedarf analysiert werden, um komplexe Systeme zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="237ea-115">Detailed logs can be analyzed as needed to understand complex systems.</span></span>
- <span data-ttu-id="237ea-116">Probleme in verteilten Anwendungen können aus einer komplexen Interaktion zwischen vielen Komponenten entstehen, und es ist möglicherweise nicht sinnvoll, mit jedem Teil des Systems einen Debugger zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="237ea-116">Issues in distributed applications may arise from a complex interaction between many components and it may not be reasonable to connect a debugger to every part of the system.</span></span>
- <span data-ttu-id="237ea-117">Viele Dienste sollten nicht verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="237ea-117">Many services shouldn't be stalled.</span></span> <span data-ttu-id="237ea-118">Das Anfügen eines Debuggers verursacht häufig Timeoutfehler.</span><span class="sxs-lookup"><span data-stu-id="237ea-118">Attaching a debugger often causes timeout failures.</span></span>
- <span data-ttu-id="237ea-119">Probleme sind nicht immer vorhersehbar.</span><span class="sxs-lookup"><span data-stu-id="237ea-119">Issues aren't always foreseen.</span></span> <span data-ttu-id="237ea-120">Protokollierung und Ablaufverfolgung sind auf einen geringen Mehraufwand ausgelegt, sodass Programme immer aufzeichnen können, falls ein Problem auftritt.</span><span class="sxs-lookup"><span data-stu-id="237ea-120">Logging and tracing are designed for low overhead so that programs can always be recording in case an issue occurs.</span></span>

## <a name="net-core-apis"></a><span data-ttu-id="237ea-121">.NET Core-APIs</span><span class="sxs-lookup"><span data-stu-id="237ea-121">.NET Core APIs</span></span>

### <a name="print-style-apis"></a><span data-ttu-id="237ea-122">Ausgabeformat-APIs</span><span class="sxs-lookup"><span data-stu-id="237ea-122">Print style APIs</span></span>

<span data-ttu-id="237ea-123">Die Klassen <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType> und <xref:System.Diagnostics.Debug?displayProperty=nameWithType> stellen jeweils ähnliche Ausgabeformat-APIs bereit, die für die Protokollierung gut geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="237ea-123">The <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes each provide similar print style APIs convenient for logging.</span></span>

<span data-ttu-id="237ea-124">Welche Ausgabeformat-API Sie verwenden, ist Ihnen überlassen.</span><span class="sxs-lookup"><span data-stu-id="237ea-124">The choice of which print style API to use is up to you.</span></span> <span data-ttu-id="237ea-125">Hauptunterschiede:</span><span class="sxs-lookup"><span data-stu-id="237ea-125">The key differences are:</span></span>

- <xref:System.Console?displayProperty=nameWithType>
  - <span data-ttu-id="237ea-126">Immer aktiviert und schreibt immer in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="237ea-126">Always enabled and always writes to the console.</span></span>
  - <span data-ttu-id="237ea-127">Nützlich für Informationen, die dem Kunden möglicherweise im Release gezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="237ea-127">Useful for information that your customer may need to see in the release.</span></span>
  - <span data-ttu-id="237ea-128">Da es sich um den einfachsten Ansatz handelt, wird er häufig für temporäres Ad-hoc-Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="237ea-128">Because it's the simplest approach, it's often used for ad-hoc temporary debugging.</span></span> <span data-ttu-id="237ea-129">Dieser Debugcode wird häufig nicht in die Quellcodeverwaltung eingecheckt.</span><span class="sxs-lookup"><span data-stu-id="237ea-129">This debug code is often never checked in to source control.</span></span>
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - <span data-ttu-id="237ea-130">Ist nur aktiviert, wenn `TRACE` durch Hinzufügen von `#define TRACE` zur Quelle oder durch Angabe der Option `/d:TRACE` bei der Kompilierung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="237ea-130">Only enabled when `TRACE` is defined by adding `#define TRACE` to your source or specifying the option `/d:TRACE` when compiling.</span></span>
  - <span data-ttu-id="237ea-131">Schreibt in angefügte <xref:System.Diagnostics.Trace.Listeners>, standardmäßig <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="237ea-131">Writes to attached <xref:System.Diagnostics.Trace.Listeners>, by default the <xref:System.Diagnostics.DefaultTraceListener>.</span></span>
  - <span data-ttu-id="237ea-132">Verwenden Sie diese API zum Erstellen von Protokollen, die in den meisten Builds aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="237ea-132">Use this API when creating logs that will be enabled in most builds.</span></span>
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - <span data-ttu-id="237ea-133">Ist nur aktiviert, wenn `DEBUG` durch Hinzufügen von `#define DEBUG` zur Quelle oder durch Angabe der Option `/d:DEBUG` bei der Kompilierung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="237ea-133">Only enabled when `DEBUG` is defined by adding `#define DEBUG` to your source or specifying the option `/d:DEBUG` when compiling.</span></span>
  - <span data-ttu-id="237ea-134">Schreibt in einen angefügten Debugger.</span><span class="sxs-lookup"><span data-stu-id="237ea-134">Writes to an attached debugger.</span></span>
  - <span data-ttu-id="237ea-135">Schreibt bei `*nix` in stderr, wenn `COMPlus_DebugWriteToStdErr` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="237ea-135">On `*nix` writes to stderr if `COMPlus_DebugWriteToStdErr` is set.</span></span>
  - <span data-ttu-id="237ea-136">Verwenden Sie diese API zum Erstellen von Protokollen, die nur in Debugbuilds aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="237ea-136">Use this API when creating logs that will be enabled only in debug builds.</span></span>

### <a name="logging-events"></a><span data-ttu-id="237ea-137">Protokollieren von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="237ea-137">Logging events</span></span>

<span data-ttu-id="237ea-138">Die folgenden APIs sind eher ereignisorientiert.</span><span class="sxs-lookup"><span data-stu-id="237ea-138">The following APIs are more event oriented.</span></span> <span data-ttu-id="237ea-139">Anstelle von einfachen Zeichenfolgen protokollieren sie Ereignisobjekte.</span><span class="sxs-lookup"><span data-stu-id="237ea-139">Rather than logging simple strings they log event objects.</span></span>

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - <span data-ttu-id="237ea-140">EventSource ist die primäre Stamm-API für die .NET Core-Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="237ea-140">EventSource is the primary root .NET Core tracing API.</span></span>
  - <span data-ttu-id="237ea-141">In allen .NET-Standardversionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="237ea-141">Available in all .NET Standard versions.</span></span>
  - <span data-ttu-id="237ea-142">Ermöglicht nur die Ablaufverfolgung serialisierbarer Objekte.</span><span class="sxs-lookup"><span data-stu-id="237ea-142">Only allows tracing serializable objects.</span></span>
  - <span data-ttu-id="237ea-143">Kann innerhalb des Prozesses über alle [EventListener](xref:System.Diagnostics.Tracing.EventListener)-Instanzen, die für die Verwendung von EventSource konfiguriert sind, genutzt werden</span><span class="sxs-lookup"><span data-stu-id="237ea-143">Can be consumed in-process via any [EventListener](xref:System.Diagnostics.Tracing.EventListener) instances configured to consume the EventSource.</span></span>
  - <span data-ttu-id="237ea-144">Kann außerhalb des Prozesses über Folgendes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="237ea-144">Can be consumed out-of-process via:</span></span>
    - <span data-ttu-id="237ea-145">[.NET Core-EventPipe](./eventpipe.md) auf allen Plattformen</span><span class="sxs-lookup"><span data-stu-id="237ea-145">[.NET Core's EventPipe](./eventpipe.md) on all platforms</span></span>
    - [<span data-ttu-id="237ea-146">Ereignisablaufverfolgung für Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="237ea-146">Event Tracing for Windows (ETW)</span></span>](/windows/win32/etw/event-tracing-portal)
    - [<span data-ttu-id="237ea-147">LTTng-Ablaufverfolgungs-Framework für Linux</span><span class="sxs-lookup"><span data-stu-id="237ea-147">LTTng tracing framework for Linux</span></span>](https://lttng.org/)
      - <span data-ttu-id="237ea-148">Exemplarische Vorgehensweise: [Erfassen einer LTTng-Ablaufverfolgung mit PerfCollect](trace-perfcollect-lttng.md)</span><span class="sxs-lookup"><span data-stu-id="237ea-148">Walkthrough: [Collect an LTTng trace using PerfCollect](trace-perfcollect-lttng.md).</span></span>

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - <span data-ttu-id="237ea-149">Enthalten in .NET Core sowie als [NuGet-Paket](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) für .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="237ea-149">Included in .NET Core and as a [NuGet package](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) for .NET Framework.</span></span>
  - <span data-ttu-id="237ea-150">Ermöglicht die prozessinterne Ablaufverfolgung von nicht serialisierbaren Objekten.</span><span class="sxs-lookup"><span data-stu-id="237ea-150">Allows in-process tracing of non-serializable objects.</span></span>
  - <span data-ttu-id="237ea-151">Schließt eine Bridge ein, damit ausgewählte Felder der protokollierten Objekte in eine <xref:System.Diagnostics.Tracing.EventSource> geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="237ea-151">Includes a bridge to allow selected fields of logged objects to be written to an <xref:System.Diagnostics.Tracing.EventSource>.</span></span>

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - <span data-ttu-id="237ea-152">Bietet eine eindeutige Methode zum Identifizieren von Protokollmeldungen, die sich aus einer bestimmten Aktivität oder Transaktion ergeben.</span><span class="sxs-lookup"><span data-stu-id="237ea-152">Provides a definitive way to identify log messages resulting from a specific activity or transaction.</span></span> <span data-ttu-id="237ea-153">Dieses Objekt kann zum dienstübergreifenden Korrelieren von Protokollen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="237ea-153">This object can be used to correlate logs across different services.</span></span>

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - <span data-ttu-id="237ea-154">Nur Windows.</span><span class="sxs-lookup"><span data-stu-id="237ea-154">Windows only.</span></span>
  - <span data-ttu-id="237ea-155">Schreibt Nachrichten in das Windows-Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="237ea-155">Writes messages to the Windows Event Log.</span></span>
  - <span data-ttu-id="237ea-156">Systemadministratoren erwarten, dass schwerwiegende Anwendungsfehlermeldungen im Windows-Ereignisprotokoll aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="237ea-156">System administrators expect fatal application error messages to appear in the Windows Event Log.</span></span>

## <a name="ilogger-and-logging-frameworks"></a><span data-ttu-id="237ea-157">ILogger und Protokollierungsframeworks</span><span class="sxs-lookup"><span data-stu-id="237ea-157">ILogger and logging frameworks</span></span>

<span data-ttu-id="237ea-158">Die Low-Level-APIs sind möglicherweise nicht die richtige Wahl für Ihre Protokollierungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="237ea-158">The low-level APIs may not be the right choice for your logging needs.</span></span> <span data-ttu-id="237ea-159">Ein Protokollierungsframework ist eventuell besser geeignet.</span><span class="sxs-lookup"><span data-stu-id="237ea-159">You may want to consider a logging framework.</span></span>

<span data-ttu-id="237ea-160">Über die <xref:Microsoft.Extensions.Logging.ILogger>-Schnittstelle wurde eine gemeinsame Protokollierungsschnittstelle erstellt, bei der die Protokollierungen mithilfe einer Abhängigkeitsinjektion eingefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="237ea-160">The <xref:Microsoft.Extensions.Logging.ILogger> interface has been used to create a common logging interface where the loggers can be inserted through dependency injection.</span></span>

<span data-ttu-id="237ea-161">Damit Sie beispielsweise die beste Wahl für Ihre Anwendung treffen können, bietet .NET Unterstützung für integrierte Frameworks sowie für Frameworks von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="237ea-161">For instance, to allow you to make the best choice for your application .NET offers support for a selection of built-in and third-party frameworks:</span></span>

- [<span data-ttu-id="237ea-162">Integrierte .NET-Protokollierungsanbieter</span><span class="sxs-lookup"><span data-stu-id="237ea-162">.NET Built-in logging providers</span></span>](../extensions/logging-providers.md#built-in-logging-providers)
- [<span data-ttu-id="237ea-163">Dritte .NET-Protokollierungsanbieter</span><span class="sxs-lookup"><span data-stu-id="237ea-163">.NET Third-party logging providers</span></span>](../extensions/logging-providers.md#third-party-logging-providers)

## <a name="logging-related-references"></a><span data-ttu-id="237ea-164">Verweise zur Protokollierung</span><span class="sxs-lookup"><span data-stu-id="237ea-164">Logging related references</span></span>

- [<span data-ttu-id="237ea-165">Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen</span><span class="sxs-lookup"><span data-stu-id="237ea-165">How to: Compile Conditionally with Trace and Debug</span></span>](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [<span data-ttu-id="237ea-166">Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="237ea-166">How to: Add Trace Statements to Application Code</span></span>](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- <span data-ttu-id="237ea-167">[Die .NET-Protokollierung](../extensions/logging.md) bietet eine Übersicht über die unterstützten Protokollierungstechniken.</span><span class="sxs-lookup"><span data-stu-id="237ea-167">[Logging in .NET](../extensions/logging.md) provides an overview of the logging techniques it supports.</span></span>

- <span data-ttu-id="237ea-168">Die [C#-Zeichenfolgeninterpolation](../../csharp/language-reference/tokens/interpolated.md) kann das Schreiben von Protokollierungscode vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="237ea-168">[C# string interpolation](../../csharp/language-reference/tokens/interpolated.md) can simplify writing logging code.</span></span>

- [<span data-ttu-id="237ea-169">Ereignisliste für Runtimeanbieter</span><span class="sxs-lookup"><span data-stu-id="237ea-169">Runtime Provider Event List</span></span>](../../fundamentals/diagnostics/runtime-events.md)

- [<span data-ttu-id="237ea-170">Bekannte Ereignisanbieter in .NET</span><span class="sxs-lookup"><span data-stu-id="237ea-170">Well-known Event Providers in .NET</span></span>](well-known-event-providers.md)

- <span data-ttu-id="237ea-171">Die <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft ist nützlich für das Protokollieren von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="237ea-171">The <xref:System.Exception.Message?displayProperty=nameWithType> property is useful for logging exceptions.</span></span>

- <span data-ttu-id="237ea-172">Die <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType>-Klasse kann nützlich sein, um in Ihren Protokollen Stapelinformationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="237ea-172">The <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> class can be useful to provide stack info in your logs.</span></span>

## <a name="performance-considerations"></a><span data-ttu-id="237ea-173">Überlegungen zur Leistung</span><span class="sxs-lookup"><span data-stu-id="237ea-173">Performance considerations</span></span>

<span data-ttu-id="237ea-174">Die Zeichenfolgenformatierung kann eine deutliche CPU-Verarbeitungszeit beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="237ea-174">String formatting can take noticeable CPU processing time.</span></span>

<span data-ttu-id="237ea-175">Bei leistungskritischen Anwendungen empfiehlt sich Folgendes:</span><span class="sxs-lookup"><span data-stu-id="237ea-175">In performance critical applications, it's recommended that you:</span></span>

- <span data-ttu-id="237ea-176">Vermeiden Sie umfassende Protokollierung, wenn diese nicht überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="237ea-176">Avoid lots of logging when no one is listening.</span></span> <span data-ttu-id="237ea-177">Vermeiden Sie das Erstellen aufwendiger Protokollierungsnachrichten, indem Sie zuerst überprüfen, ob die Protokollierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="237ea-177">Avoid constructing costly logging messages by checking if logging is enabled first.</span></span>
- <span data-ttu-id="237ea-178">Protokollieren Sie nur nützliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="237ea-178">Only log what's useful.</span></span>
- <span data-ttu-id="237ea-179">Verschieben Sie anspruchsvolle Formatierung in die Analysephase.</span><span class="sxs-lookup"><span data-stu-id="237ea-179">Defer fancy formatting to the analysis stage.</span></span>
