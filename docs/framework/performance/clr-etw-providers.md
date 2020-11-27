---
title: CLR-ETW-Anbieter
description: 'Überprüfen Sie die Details zu den beiden Common Language Runtime (CLR)-Anbieter für die Ereignis Ablauf Verfolgung für Windows (ETW): den runtimne-Anbieter und den rundownanbieter.'
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, CLR providers
- CLR ETW providers
ms.assetid: 0beafad4-b2c8-47f4-b342-83411d57a51f
ms.openlocfilehash: f537a2e0557f1b0434d1f303d74f9cd48f157edc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283873"
---
# <a name="clr-etw-providers"></a><span data-ttu-id="59fc7-103">CLR-ETW-Anbieter</span><span class="sxs-lookup"><span data-stu-id="59fc7-103">CLR ETW Providers</span></span>

<span data-ttu-id="59fc7-104">Die Common Language Runtime (CLR) verfügt über zwei Anbieter: den Laufzeitanbieter und den Rundownanbieter.</span><span class="sxs-lookup"><span data-stu-id="59fc7-104">The common language runtime (CLR) has two providers: the runtime provider and the rundown provider.</span></span>  
  
 <span data-ttu-id="59fc7-105">Der Laufzeitanbieter löst Ereignisse in Abhängigkeit von den aktivierten Schlüsselwörtern (Ereigniskategorien) aus.</span><span class="sxs-lookup"><span data-stu-id="59fc7-105">The runtime provider raises events, depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="59fc7-106">Sie können z. B. Ladeprogrammereignisse sammeln, indem Sie das Schlüsselwort `LoaderKeyword` aktivieren.</span><span class="sxs-lookup"><span data-stu-id="59fc7-106">For example, you can collect loader events by enabling the `LoaderKeyword` keyword.</span></span>  
  
 <span data-ttu-id="59fc7-107">Ereignisse der Ereignis Ablauf Verfolgung für Windows (Event Tracing for Windows, etw) werden in einer Datei mit der Erweiterung ETL protokolliert, die später nach Bedarf in durch Trennzeichen getrennten Werten (CSV-Dateien) verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="59fc7-107">Event Tracing for Windows (ETW) events are logged into a file that has an .etl extension, which can later be post-processed in comma-separated value (.csv) files as needed.</span></span> <span data-ttu-id="59fc7-108">Informationen zum Konvertieren der ETL-Datei in eine CSV-Datei finden Sie unter [Steuern der Protokollierung in .NET Framework](controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="59fc7-108">For information about how to convert the .etl file to a .csv file, see [Controlling .NET Framework Logging](controlling-logging.md).</span></span>  
  
## <a name="the-runtime-provider"></a><span data-ttu-id="59fc7-109">Der Laufzeitanbieter</span><span class="sxs-lookup"><span data-stu-id="59fc7-109">The Runtime Provider</span></span>  

 <span data-ttu-id="59fc7-110">Der Laufzeitanbieter ist der zentrale CLR-ETW-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="59fc7-110">The runtime provider is the main CLR ETW provider.</span></span>  
  
 <span data-ttu-id="59fc7-111">Die GUID des CLR-Laufzeitanbieters ist e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="59fc7-111">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
 <span data-ttu-id="59fc7-112">Beispiele zum Protokollieren und Anzeigen von CLR-ETW-Ereignissen mithilfe gängiger Tools finden Sie unter [Steuern der Protokollierung in .NET Framework](controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="59fc7-112">For examples of how to log and view CLR ETW events by using commonly available tools, see [Controlling .NET Framework Logging](controlling-logging.md).</span></span>  
  
 <span data-ttu-id="59fc7-113">Neben Schlüsselwörtern wie `LoaderKeyword` müssen Sie möglicherweise Schlüsselwörter zum Protokollieren von Ereignissen aktivieren, die möglicherweise zu häufig ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="59fc7-113">In addition to using keywords such as `LoaderKeyword`, you may have to enable keywords for logging events that may be raised too frequently.</span></span> <span data-ttu-id="59fc7-114">Die `StartEnumerationKeyword`- und `EndEnumerationKeyword`-Schlüsselwörter aktivieren diese Ereignisse und werden in [CLR-ETW-Schlüsselwörter und -Ebenen](clr-etw-keywords-and-levels.md) zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="59fc7-114">The `StartEnumerationKeyword` and the `EndEnumerationKeyword` keywords enable these events and are summarized in [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>  
  
## <a name="the-rundown-provider"></a><span data-ttu-id="59fc7-115">Der Rundownanbieter</span><span class="sxs-lookup"><span data-stu-id="59fc7-115">The Rundown Provider</span></span>  

 <span data-ttu-id="59fc7-116">Für bestimmte Verwendungszwecke muss der Rundownanbieter aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="59fc7-116">The rundown provider must be turned on for certain special-purpose uses.</span></span> <span data-ttu-id="59fc7-117">Für die Mehrheit der Benutzer sollte nur der Laufzeitanbieter in Frage kommen.</span><span class="sxs-lookup"><span data-stu-id="59fc7-117">However, for a majority of users, the runtime provider should suffice.</span></span>  
  
 <span data-ttu-id="59fc7-118">Die GUID des CLR-Rundownanbieters ist A669021C-C450-4609-A035-5AF59AF4DF18.</span><span class="sxs-lookup"><span data-stu-id="59fc7-118">The CLR rundown provider GUID is A669021C-C450-4609-A035-5AF59AF4DF18.</span></span>  
  
 <span data-ttu-id="59fc7-119">Normalerweise wird die ETW-Protokollierung vor dem Start eines Prozesses aktiviert, und die Protokollierung wird nach dem Beenden des Prozesses deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="59fc7-119">Normally, ETW logging is enabled before a process launches, and the logging is turned off after the process exits.</span></span> <span data-ttu-id="59fc7-120">Wenn jedoch die ETW-Protokollierung aktiviert wird, während der Prozess ausgeführt wird, werden zusätzliche Informationen zum Prozess benötigt.</span><span class="sxs-lookup"><span data-stu-id="59fc7-120">However, if ETW logging is turned on while the process is executing, additional information is needed about the process.</span></span> <span data-ttu-id="59fc7-121">Für die Symbolauflösung müssen Sie zum Beispiel Methodenereignisse für Methoden protokollieren, die bereits vor dem Aktivieren der Protokollierung geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="59fc7-121">For example, for symbol resolution you have to log method events for methods that were already loaded before logging was turned on.</span></span>  
  
 <span data-ttu-id="59fc7-122">Das `DCStart`-Ereignis und das `DCEnd`-Ereignis erfassen den Zustand des Prozesses, als die Datensammlung gestartet und beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="59fc7-122">The `DCStart` and `DCEnd` events capture the state of the process when data collection was started and stopped.</span></span> <span data-ttu-id="59fc7-123">(State bezieht sich auf Informationen auf hoher Ebene, einschließlich der Methoden, die bereits JIT-kompilierte (Just-in-Time)-und geladene Assemblys waren.) Diese beiden Ereignisse können Informationen darüber bereitstellen, was bereits im Prozess passiert ist. beispielsweise, welche Methoden JIT-kompiliert wurden, usw.</span><span class="sxs-lookup"><span data-stu-id="59fc7-123">(State refers to information at a high level, including the methods that were already just-in-time (JIT) compiled and assemblies that were loaded.) These two events can provide information about what has already happened in the process; for example, which methods were JIT- compiled, and so on.</span></span>  
  
 <span data-ttu-id="59fc7-124">Nur die Ereignisse mit `DC`, `DCStart`, `DCEnd` oder `DCInit` in ihren Namen werden unter dem Rundownanbieter ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="59fc7-124">Only the events with `DC`, `DCStart`, `DCEnd`, or `DCInit` in their names are raised under the rundown provider.</span></span> <span data-ttu-id="59fc7-125">Darüber hinaus werden diese Ereignisse nur unter dem Rundownanbieter ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="59fc7-125">Additionally, these events are raised only under the rundown provider.</span></span>  
  
 <span data-ttu-id="59fc7-126">Neben den Ereignisschlüsselwortfiltern unterstützt der Rundownanbieter auch die Schlüsselwörter `StartRundownKeyword` und `EndRundownKeyword`, um eine gezielte Filterung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="59fc7-126">In addition to the event keyword filters, the rundown provider also supports the `StartRundownKeyword` and `EndRundownKeyword` keywords to provide targeted filtering.</span></span>  
  
### <a name="start-rundown"></a><span data-ttu-id="59fc7-127">Startrundown</span><span class="sxs-lookup"><span data-stu-id="59fc7-127">Start Rundown</span></span>  

 <span data-ttu-id="59fc7-128">Ein Startrundown wird ausgelöst, wenn Protokollierung unter dem Rundownanbieter mit dem `StartRundownKeyword`-Schlüsselwort aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="59fc7-128">A start rundown is triggered when logging under the rundown provider is enabled with the `StartRundownKeyword` keyword.</span></span> <span data-ttu-id="59fc7-129">Dadurch wird das `DCStart`-Ereignis ausgelöst und der Zustand des Systems erfasst.</span><span class="sxs-lookup"><span data-stu-id="59fc7-129">This causes the `DCStart` event to be raised, and captures the state of the system.</span></span> <span data-ttu-id="59fc7-130">Vor dem Start der Enumeration wird das `DCStartInit`-Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="59fc7-130">Before the start of the enumeration, the `DCStartInit` event is raised.</span></span> <span data-ttu-id="59fc7-131">Am Ende der Enumeration wird das `DCStartComplete`-Ereignis ausgelöst, um den Controller zu benachrichtigen, dass die Datensammlung ordnungsgemäß beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="59fc7-131">At the end of the enumeration, the `DCStartComplete` event is raised to notify the controller that data collection terminated normally.</span></span>  
  
### <a name="end-rundown"></a><span data-ttu-id="59fc7-132">Endrundown</span><span class="sxs-lookup"><span data-stu-id="59fc7-132">End Rundown</span></span>  

 <span data-ttu-id="59fc7-133">Ein Endrundown wird ausgelöst, wenn Protokollierung unter dem Rundownanbieter mit dem Schlüsselwort `EndRundownKeyword` aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="59fc7-133">An end rundown is triggered when logging under the rundown provider is enabled with the `EndRundownKeyword` keyword.</span></span> <span data-ttu-id="59fc7-134">Der Endrundown beendet die Profilerstellung für einen Prozess, der weiterhin ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="59fc7-134">End rundown stops profiling on a process that continues to execute.</span></span> <span data-ttu-id="59fc7-135">Die `DCEnd`-Ereignisse erfassen den Zustand des Systems, wenn die Profilerstellung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="59fc7-135">The `DCEnd` events capture the state of the system when profiling is stopped.</span></span>  
  
 <span data-ttu-id="59fc7-136">Vor dem Start der Enumeration wird das `DCEndInit`-Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="59fc7-136">Before the start of the enumeration, the `DCEndInit` event is raised.</span></span> <span data-ttu-id="59fc7-137">Am Ende der Enumeration wird das `DCEndComplete`-Ereignis ausgelöst, um den Consumer zu benachrichtigen, dass die Datensammlung ordnungsgemäß beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="59fc7-137">At the end of the enumeration, the `DCEndComplete` event is raised to notify the consumer that data collection terminated normally.</span></span> <span data-ttu-id="59fc7-138">Start- und Endrundown werden hauptsächlich für verwaltete Symbolauflösung verwendet.</span><span class="sxs-lookup"><span data-stu-id="59fc7-138">Start rundown and end rundown are primarily used for managed symbol resolution.</span></span> <span data-ttu-id="59fc7-139">Der Startrundown kann Adressbereichsinformationen für Methoden enthalten, die bereits JIT-kompiliert wurden, bevor die Profilerstellungssitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="59fc7-139">Start rundown can provide address range information for methods that were already JIT-compiled before the profiling session was started.</span></span> <span data-ttu-id="59fc7-140">Der Endrundown kann Adressbereichsinformationen für alle Methoden liefern, deren JIT-Kompilierung zum Zeitpunkt der Deaktivierung der Profilerstellung erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="59fc7-140">End rundown can provide address range information for all methods that have been JIT-compiled when profiling is about to be turned off.</span></span>  
  
 <span data-ttu-id="59fc7-141">Der Endrundown wird nicht automatisch ausgeführt, wenn eine Profilerstellungssitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="59fc7-141">End rundown does not happen automatically when a profiling session is stopped.</span></span> <span data-ttu-id="59fc7-142">Stattdessen muss ein Tool, von dem eine verwaltete Symbolauflösung ausgeführt werden soll, explizit eine CLR-Rundownanbietersitzung aufrufen, bei der das Schlüsselwort `EndRundownKeyword` aktiviert ist (unmittelbar vor dem Beenden der Profilerstellung).</span><span class="sxs-lookup"><span data-stu-id="59fc7-142">Instead, a tool that is seeking to perform managed symbol resolution has to explicitly invoke a CLR rundown provider session with the `EndRundownKeyword` keyword enabled, just before profiling is stopped.</span></span>  
  
 <span data-ttu-id="59fc7-143">Obwohl entweder vom Start- oder vom Endrundown Methodenadressbereichs-Informationen für verwaltete Symbolauflösung bereitgestellt werden können, wird empfohlen, das Schlüsselwort `EndRundownKeyword` (das `DCEnd`-Ereignisse angibt) anstelle des Schlüsselworts `StartRundownKeyword` zu verwenden (das `DCStart`-Ereignisse angibt).</span><span class="sxs-lookup"><span data-stu-id="59fc7-143">Although either start rundown or end rundown can provide method address range information for managed symbol resolution, we recommend that you use the `EndRundownKeyword` keyword (which supplies `DCEnd` events) instead of the `StartRundownKeyword` keyword (which supplies `DCStart` events).</span></span> <span data-ttu-id="59fc7-144">Mit `StartRundownKeyword` wird der Rundown während der Profilerstellungssitzung ausgeführt, wodurch u. U. das Szenario, für das ein Profil erstellt wurde, beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="59fc7-144">Using `StartRundownKeyword` causes the rundown to happen during the profiling session, which may disturb the profiled scenario.</span></span>  
  
## <a name="etw-data-collection-using-runtime-and-rundown-providers"></a><span data-ttu-id="59fc7-145">ETW-Datensammlung mit Laufzeit- und Rundownanbietern</span><span class="sxs-lookup"><span data-stu-id="59fc7-145">ETW Data Collection Using Runtime and Rundown Providers</span></span>  

 <span data-ttu-id="59fc7-146">Im folgenden Beispiel wird veranschaulicht, wie der CLR-Rundownanbieter so verwendet wird, dass die Symbolauflösung verwalteter Prozesse mit minimalen Auswirkungen ermöglicht wird, unabhängig davon, ob die Prozesse innerhalb oder außerhalb des Fensters, für das ein Profil erstellt wurde, beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="59fc7-146">The following example demonstrates how to use the CLR rundown provider in a way that allows symbol resolution of managed processes with minimal impact, regardless of whether the processes start or end inside or outside the profiled window.</span></span>  
  
1. <span data-ttu-id="59fc7-147">Aktivieren Sie die ETW-Protokollierung mit dem CLR-Laufzeitanbieter:</span><span class="sxs-lookup"><span data-stu-id="59fc7-147">Turn on ETW logging by using the CLR runtime provider:</span></span>  
  
    ```console
    xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:0x5 -f clr1.etl
    ```  
  
     <span data-ttu-id="59fc7-148">Das Protokoll wird in der Datei clr1.etl gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59fc7-148">The log will be saved to the clr1.etl file.</span></span>  
  
2. <span data-ttu-id="59fc7-149">Um die Profilerstellung zu beenden, während der Prozess weiterhin ausgeführt wird, starten Sie den Rundownanbieter, um die `DCEnd`-Ereignisse zu erfassen:</span><span class="sxs-lookup"><span data-stu-id="59fc7-149">To stop profiling while the process continues to execute, start the rundown provider to capture the `DCEnd` events:</span></span>  
  
    ```console
    xperf -start clrRundown -on A669021C-C450-4609-A035-5AF59AF4DF18:0xB8:0x5 -f clr2.etl
    ```  
  
     <span data-ttu-id="59fc7-150">Dadurch kann mit dem Sammeln von `DCEnd`-Ereignissen eine Rundownsitzung begonnen werden.</span><span class="sxs-lookup"><span data-stu-id="59fc7-150">This enables the collection of `DCEnd` events to start a rundown session.</span></span> <span data-ttu-id="59fc7-151">Das Sammeln aller Ereignisse dauert möglicherweise 30 bis 60 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="59fc7-151">You may need to wait 30 to 60 seconds for all events to be collected.</span></span> <span data-ttu-id="59fc7-152">Das Protokoll wird in der Datei clr1.et2 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59fc7-152">The log will be saved to the clr1.et2 file.</span></span>  
  
3. <span data-ttu-id="59fc7-153">Deaktivieren Sie die gesamte ETW-Profilerstellung:</span><span class="sxs-lookup"><span data-stu-id="59fc7-153">Turn off all ETW profiling:</span></span>  
  
    ```console
    xperf -stop clrRundown
    xperf -stop clr  
    ```  
  
4. <span data-ttu-id="59fc7-154">Führen Sie die Profile zusammen, um eine Protokolldatei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="59fc7-154">Merge the profiles to create one log file:</span></span>  
  
    ```console
    xperf -merge clr1.etl clr2.etl merged.etl  
    ```  
  
     <span data-ttu-id="59fc7-155">Die Datei "merged.etl" enthält die Ereignisse von den Laufzeit- und Rundownanbietersitzungen.</span><span class="sxs-lookup"><span data-stu-id="59fc7-155">The merged.etl file will contain the events from the runtime and the rundown provider sessions.</span></span>  
  
 <span data-ttu-id="59fc7-156">Ein Tool kann die Schritte 2 und 3 ausführen (dabei wird eine Rundownsitzung gestartet und anschließend die Profilerstellung beendet), anstatt sofort die Profilerstellung zu deaktivieren, wenn ein Benutzer das Beenden der Profilerstellung anfordert.</span><span class="sxs-lookup"><span data-stu-id="59fc7-156">A tool can execute steps 2 and 3 (starting a rundown session and then terminating profiling) instead of immediately turning off profiling when a user requests profiling to be stopped.</span></span> <span data-ttu-id="59fc7-157">Schritt 4 kann auch mit einem Tool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="59fc7-157">A tool can also execute step 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fc7-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59fc7-158">See also</span></span>

- [<span data-ttu-id="59fc7-159">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="59fc7-159">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
