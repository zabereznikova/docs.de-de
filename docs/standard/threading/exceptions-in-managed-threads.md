---
title: Ausnahmen in verwalteten Threads
description: Informationen zur Verarbeitung von Ausnahmefehlern in .NET Die meisten Ausnahmefehler in Threads werden ordnungsgemäß fortgesetzt und führen zu einem Anwendungsabbruch.
ms.date: 03/30/2017
helpviewer_keywords:
- unhandled exceptions,in managed threads
- threading [.NET],unhandled exceptions
- threading [.NET],exceptions in managed threads
- managed threading
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
ms.openlocfilehash: 740cd1b78b96c2fcaecf39a725973d738037f403
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723752"
---
# <a name="exceptions-in-managed-threads"></a><span data-ttu-id="a3c16-104">Ausnahmen in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="a3c16-104">Exceptions in managed threads</span></span>

<span data-ttu-id="a3c16-105">Die Common Language Runtime lässt bei den meisten Ausnahmefehlern in Threads deren ordnungsgemäße Fortsetzung zu.</span><span class="sxs-lookup"><span data-stu-id="a3c16-105">The common language runtime allows most unhandled exceptions in threads to proceed naturally.</span></span> <span data-ttu-id="a3c16-106">Das für i. d R. dazu, dass die Anwendung durch die unbehandelte Ausnahme beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3c16-106">In most cases this means that the unhandled exception causes the application to terminate.</span></span>
  
<span data-ttu-id="a3c16-107">Die Common Language Runtime stellt für bestimmte unbehandelte Ausnahmen, die zum Steuern des Programmablaufs verwendet werden, ein Sicherheitsnetz bereit:</span><span class="sxs-lookup"><span data-stu-id="a3c16-107">The common language runtime provides a backstop for certain unhandled exceptions that are used for controlling program flow:</span></span>  
  
- <span data-ttu-id="a3c16-108">In einem Thread wird eine <xref:System.Threading.ThreadAbortException> ausgelöst, da <xref:System.Threading.Thread.Abort%2A> aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a3c16-108">A <xref:System.Threading.ThreadAbortException> is thrown in a thread because <xref:System.Threading.Thread.Abort%2A> was called.</span></span>  
  
- <span data-ttu-id="a3c16-109">In einem Thread wird eine <xref:System.AppDomainUnloadedException> ausgelöst, da die Anwendungsdomäne, in der der Thread ausgeführt wird, entladen wird.</span><span class="sxs-lookup"><span data-stu-id="a3c16-109">An <xref:System.AppDomainUnloadedException> is thrown in a thread because the application domain in which the thread is executing is being unloaded.</span></span>  
  
- <span data-ttu-id="a3c16-110">Die Common Language Runtime oder ein Hostprozess beendet den Thread durch Auslösen einer internen Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a3c16-110">The common language runtime or a host process terminates the thread by throwing an internal exception.</span></span>  
  
 <span data-ttu-id="a3c16-111">Wenn eine dieser Ausnahmen in Threads, die von der Common Language Runtime erstellt wurden, nicht behandelt werden, beendet die Ausnahme den Thread, die Common Language Runtime lässt jedoch die Weiterreichung der Ausnahme nicht zu.</span><span class="sxs-lookup"><span data-stu-id="a3c16-111">If any of these exceptions are unhandled in threads created by the common language runtime, the exception terminates the thread, but the common language runtime does not allow the exception to proceed further.</span></span>  
  
 <span data-ttu-id="a3c16-112">Wenn diese Ausnahmen im Hauptthread oder in Threads, die von nicht verwaltetem Code in die Laufzeit eintreten, nicht behandelt werden, werden sie normal fortgesetzt, d. h., sie beenden die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a3c16-112">If these exceptions are unhandled in the main thread, or in threads that entered the runtime from unmanaged code, they proceed normally, resulting in termination of the application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3c16-113">Die Laufzeit kann eine unbehandelte Ausnahme auslösen, bevor verwalteter Code einen Ausnahmehandler installieren kann.</span><span class="sxs-lookup"><span data-stu-id="a3c16-113">It is possible for the runtime to throw an unhandled exception before any managed code has had a chance to install an exception handler.</span></span> <span data-ttu-id="a3c16-114">Auch wenn verwalteter Code eine derartige Ausnahme nicht behandeln könnte, kann die Ausnahme normal fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a3c16-114">Even though managed code had no chance to handle such an exception, the exception is allowed to proceed naturally.</span></span>  
  
## <a name="exposing-threading-problems-during-development"></a><span data-ttu-id="a3c16-115">Aufdecken von Threadingproblemen bei der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="a3c16-115">Exposing Threading Problems During Development</span></span>  

 <span data-ttu-id="a3c16-116">Wenn Threads unerkannt fehlschlagen können, ohne die Anwendung zu beenden, können Sie gravierende Programmierfehler übersehen.</span><span class="sxs-lookup"><span data-stu-id="a3c16-116">When threads are allowed to fail silently, without terminating the application, serious programming problems can go undetected.</span></span> <span data-ttu-id="a3c16-117">Dies ist insbesondere bei Diensten und anderen Anwendungen ein Problem, die über einen längeren Zeitraum ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a3c16-117">This is a particular problem for services and other applications that run for extended periods.</span></span> <span data-ttu-id="a3c16-118">Durch das Fehlschlagen von Threads wird der Programmzustand allmählich beschädigt.</span><span class="sxs-lookup"><span data-stu-id="a3c16-118">As threads fail, program state gradually becomes corrupted.</span></span> <span data-ttu-id="a3c16-119">Dadurch kann sich die Anwendungsleistung verschlechtern, und es kann passieren, dass die Anwendung nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="a3c16-119">Application performance may degrade, or the application might become unresponsive.</span></span>  
  
 <span data-ttu-id="a3c16-120">Wenn Sie die normale Fortsetzung von unbehandelten Ausnahmen in Threads zulassen, bis das Programm vom Betriebssystem beendet wird, werden derartige Probleme bei der Entwicklung und beim Testen entdeckt.</span><span class="sxs-lookup"><span data-stu-id="a3c16-120">Allowing unhandled exceptions in threads to proceed naturally, until the operating system terminates the program, exposes such problems during development and testing.</span></span> <span data-ttu-id="a3c16-121">Fehlerberichte über Beendigungen des Programms unterstützen das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="a3c16-121">Error reports on program terminations support debugging.</span></span>  
  
## <a name="change-from-previous-versions"></a><span data-ttu-id="a3c16-122">Änderung im Vergleich zu früheren Versionen</span><span class="sxs-lookup"><span data-stu-id="a3c16-122">Change from previous versions</span></span>

<span data-ttu-id="a3c16-123">In den .NET Framework-Versionen 1.0 und 1.1 stellt die Common Language Runtime für Ausnahmefehler in den folgenden Situationen ein Sicherheitsnetz bereit:</span><span class="sxs-lookup"><span data-stu-id="a3c16-123">In .NET Framework versions 1.0 and 1.1, the common language runtime provides a backstop for unhandled exceptions in the following situations:</span></span>  
  
- <span data-ttu-id="a3c16-124">In einem Threadpoolthread gibt es keine unbehandelten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="a3c16-124">There is no such thing as an unhandled exception on a thread pool thread.</span></span> <span data-ttu-id="a3c16-125">Wenn eine Aufgabe eine Ausnahme auslöst, die sie nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus, und gibt den Thread an den Threadpool zurück.</span><span class="sxs-lookup"><span data-stu-id="a3c16-125">When a task throws an exception that it does not handle, the runtime prints the exception stack trace to the console and then returns the thread to the thread pool.</span></span>  
  
- <span data-ttu-id="a3c16-126">In einem Thread, der mit der <xref:System.Threading.Thread.Start%2A>-Methode der <xref:System.Threading.Thread>-Klasse behandelt wird, gibt es keine unbehandelten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="a3c16-126">There is no such thing as an unhandled exception on a thread created with the <xref:System.Threading.Thread.Start%2A> method of the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="a3c16-127">Wenn Code, der in einem derartigen Thread ausgeführt wird, eine Ausnahme auslöst, die er nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus und beendet den Thread dann ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="a3c16-127">When code running on such a thread throws an exception that it does not handle, the runtime prints the exception stack trace to the console and then gracefully terminates the thread.</span></span>  
  
- <span data-ttu-id="a3c16-128">In einem Finalizerthread gibt keine unbehandelten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="a3c16-128">There is no such thing as an unhandled exception on the finalizer thread.</span></span> <span data-ttu-id="a3c16-129">Wenn ein Finalizer eine Ausnahme auslöst, die er nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus und lässt den Finalizerthread dann die Ausführung von Finalizern fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="a3c16-129">When a finalizer throws an exception that it does not handle, the runtime prints the exception stack trace to the console and then allows the finalizer thread to resume running finalizers.</span></span>  
  
 <span data-ttu-id="a3c16-130">Der Vordergrund- oder Hintergrundstatus eines verwalteten Threads beeinflusst dieses Verhalten nicht.</span><span class="sxs-lookup"><span data-stu-id="a3c16-130">The foreground or background status of a managed thread does not affect this behavior.</span></span>  
  
 <span data-ttu-id="a3c16-131">Bei unbehandelten Ausnahmen in Threads, die aus nicht verwaltetem Code stammen, ist der Unterschied feiner.</span><span class="sxs-lookup"><span data-stu-id="a3c16-131">For unhandled exceptions on threads originating in unmanaged code, the difference is more subtle.</span></span> <span data-ttu-id="a3c16-132">Das Dialogfeld des an einen Prozess angefügten JIT hat bei verwalteten Ausnahmen oder systemeigenen Ausnahmen in Threads, die durch systemeigenen Code übergeben wurden, Vorrang vor dem Dialogfeld des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="a3c16-132">The runtime JIT-attach dialog preempts the operating system dialog for managed exceptions or native exceptions on threads that have passed through native code.</span></span> <span data-ttu-id="a3c16-133">Der Prozess wird in allen Fällen beendet.</span><span class="sxs-lookup"><span data-stu-id="a3c16-133">The process terminates in all cases.</span></span>

### <a name="migration"></a><span data-ttu-id="a3c16-134">Migration</span><span class="sxs-lookup"><span data-stu-id="a3c16-134">Migration</span></span>

<span data-ttu-id="a3c16-135">Wenn Sie von .NET Framework 1.0 oder 1.1 migrieren und das Runtime-Sicherheitsnetz ausgenutzt haben (z. B. zum Beenden von Threads), ziehen Sie eine der folgenden Migrationsstrategien in Betracht:</span><span class="sxs-lookup"><span data-stu-id="a3c16-135">If you are migrating from .NET Framework 1.0 or 1.1 and took advantage of the runtime backstop, for example to terminate threads, consider one of the following migration strategies:</span></span>  
  
- <span data-ttu-id="a3c16-136">Strukturieren Sie den Code so um, dass der Thread beim Empfang eines Signals ordnungsgemäß beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3c16-136">Restructure the code so the thread exits gracefully when a signal is received.</span></span>  
  
- <span data-ttu-id="a3c16-137">Verwenden Sie die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode, um den Thread abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="a3c16-137">Use the <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method to abort the thread.</span></span>  
  
- <span data-ttu-id="a3c16-138">Wenn ein Thread angehalten werden muss, um die Prozessbeendigung fortzusetzen, machen Sie den Thread zu einem Hintergrundthread, damit er beim Prozessende automatisch beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3c16-138">If a thread must be stopped so that process termination can proceed, make the thread a background thread so that it is automatically terminated on process exit.</span></span>  
  
<span data-ttu-id="a3c16-139">Sie sollten dabei auf jeden die Entwurfsrichtlinien für Ausnahmen einhalten.</span><span class="sxs-lookup"><span data-stu-id="a3c16-139">In all cases, the strategy should follow the design guidelines for exceptions.</span></span> <span data-ttu-id="a3c16-140">Siehe [Entwurfsrichtlinien für Ausnahmen](../design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="a3c16-140">See [Design Guidelines for Exceptions](../design-guidelines/exceptions.md).</span></span>  
  
<span data-ttu-id="a3c16-141">Administratoren können als vorübergehende Kompatibilitätsmaßnahme im `<runtime>`-Abschnitt der Anwendungskonfigurationsdatei ein Kompatibilitätsflag angeben.</span><span class="sxs-lookup"><span data-stu-id="a3c16-141">As a temporary compatibility measure, administrators can place a compatibility flag in the `<runtime>` section of the application configuration file.</span></span> <span data-ttu-id="a3c16-142">Dadurch wird die Common Language Runtime auf das Verhalten der Versionen 1.0 und 1.1 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a3c16-142">This causes the common language runtime to revert to the behavior of versions 1.0 and 1.1.</span></span>  
  
```xml  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## <a name="host-override"></a><span data-ttu-id="a3c16-143">Hostüberschreibung</span><span class="sxs-lookup"><span data-stu-id="a3c16-143">Host Override</span></span>

<span data-ttu-id="a3c16-144">Ein nicht verwalteter Host kann über die [ICLRPolicyManager](../../framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)-Schnittstelle in der Hosting-API die Standardrichtlinie für Ausnahmefehler der Common Language Runtime überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a3c16-144">An unmanaged host can use the [ICLRPolicyManager](../../framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface in the Hosting API to override the default unhandled exception policy of the common language runtime.</span></span> <span data-ttu-id="a3c16-145">Die [ICLRPolicyManager::SetUnhandledExceptionPolicy](../../framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)-Funktion wird zum Festlegen der Richtlinie für unbehandelte Ausnahmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3c16-145">The [ICLRPolicyManager::SetUnhandledExceptionPolicy](../../framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md) function is used to set the policy for unhandled exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c16-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3c16-146">See also</span></span>

- [<span data-ttu-id="a3c16-147">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="a3c16-147">Managed Threading Basics</span></span>](managed-threading-basics.md)
