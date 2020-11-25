---
title: CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 77f2ba64d9bdbe9793d56e88dae46fd506119ab8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719046"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="43340-102">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="43340-102">CLR Hosting Interfaces</span></span>

<span data-ttu-id="43340-103">In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in Ihre Anwendungen integrieren können.</span><span class="sxs-lookup"><span data-stu-id="43340-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="43340-104">Die Informationen beziehen sich auf den .NET Framework Version 2,0 und höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="43340-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="43340-105">Diese Schnittstellen ermöglichen es dem Host, viele weitere Aspekte der Laufzeit zu steuern, als dies in den Versionen 1,0 und 1,1 möglich war, und eine weitaus engere Integration zwischen der CLR und dem Ausführungs Modell des Hosts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="43340-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="43340-106">In den .NET Framework, Version 1,0 und 1,1, ermöglichte das Hostingmodell einen nicht verwalteten Host, die CLR in einen Prozess zu laden, bestimmte Einstellungen zu konfigurieren und Ereignis Benachrichtigungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="43340-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="43340-107">Im allgemeinen wurden der Host und die CLR in diesem Prozess jedoch unabhängig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43340-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="43340-108">In der .NET Framework Version 2,0 und höheren Versionen ermöglichen neue Abstraktions Ebenen dem Host die Bereitstellung zahlreicher Ressourcen, die derzeit von den Typen in der Win32-Assembly bereitgestellt werden, und erweitern den Satz von Funktionen, die der Host konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="43340-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43340-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="43340-109">In This Section</span></span>  

 [<span data-ttu-id="43340-110">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-110">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)  
 <span data-ttu-id="43340-111">Stellt eine Methode bereit, die einen Rückruf für ein registriertes Ereignis ausführt.</span><span class="sxs-lookup"><span data-stu-id="43340-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="43340-112">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-112">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)  
 <span data-ttu-id="43340-113">Stellt Methoden bereit, um Rückrufe in einem Apartment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43340-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="43340-114">IAppDomainBinding-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-114">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)  
 <span data-ttu-id="43340-115">Stellt Methoden zum Festlegen der Laufzeitkonfiguration bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="43340-116">ICatalogServices-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-116">ICatalogServices Interface</span></span>](icatalogservices-interface.md)  
 <span data-ttu-id="43340-117">Stellt Methoden für das Katalogisieren von Diensten bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="43340-118">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)</span><span class="sxs-lookup"><span data-stu-id="43340-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="43340-119">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="43340-120">Stellt Methoden bereit, die die Kommunikation zwischen dem Host und der CLR über Assemblys unterstützen.</span><span class="sxs-lookup"><span data-stu-id="43340-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="43340-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="43340-122">Verwaltet eine Liste von Assemblys, die von der CLR und nicht vom Host geladen werden.</span><span class="sxs-lookup"><span data-stu-id="43340-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="43340-123">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)  
 <span data-ttu-id="43340-124">Stellt Methoden bereit, mit denen der Host auf die CLR zugreifen und verschiedene Aspekte konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="43340-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="43340-125">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)  
 <span data-ttu-id="43340-126">Stellt Methoden bereit, mit deren Hilfe einem Host eine Reihe von Tasks mit einem Bezeichner und einem anzeigen Amen verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="43340-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="43340-127">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-127">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="43340-128">Stellt Methoden bereit, die es dem Host ermöglichen, benutzerdefinierte Heap-Abbilder für die Fehlerberichterstattung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="43340-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="43340-129">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-129">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)  
 <span data-ttu-id="43340-130">Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System der CLR interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="43340-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="43340-131">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-131">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="43340-132">Stellt Methoden bereit, mit denen der Host Änderungen an Richtlinien Informationen für Assemblys auswerten und übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="43340-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="43340-133">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-133">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="43340-134">Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="43340-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="43340-135">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-135">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)  
 <span data-ttu-id="43340-136">Implementiert eine Rückruf Methode, die es dem Host ermöglicht, die CLR über den Status der angegebenen e/a-Anforderungen zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="43340-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="43340-137">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="43340-138">Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-Funktion zu melden `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="43340-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="43340-139">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-139">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)  
 <span data-ttu-id="43340-140">Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für CLR-Ereignisse zu registrieren und die Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="43340-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="43340-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)  
 <span data-ttu-id="43340-142">Stellt Methoden bereit, die es dem Host ermöglichen, Richtlinien Aktionen anzugeben, die im Fall von Fehlern und Timeouts durchgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="43340-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="43340-143">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="43340-144">Stellt Methoden bereit, die es dem Host ermöglichen, die in der CLR internen Identitätsinformationen der Assembly zu ermitteln, ohne diese Identität erstellen oder verstehen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="43340-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="43340-145">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-145">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="43340-146">Stellt Methoden bereit, die es dem Host ermöglichen, den Satz von Assemblys, auf die von einer Datei oder einem Stream verwiesen wird, mithilfe von Assemblyidentitätsdaten zu bearbeiten, die für die CLR intern sind, ohne dass diese Identitäten</span><span class="sxs-lookup"><span data-stu-id="43340-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="43340-147">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-147">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)  
 <span data-ttu-id="43340-148">Bietet ähnliche Funktionen wie [ICorRuntimeHost](icorruntimehost-interface.md)mit einer zusätzlichen Methode zum Festlegen der Host Steuerungs Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="43340-148">Provides capabilities similar to [ICorRuntimeHost](icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="43340-149">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-149">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)  
 <span data-ttu-id="43340-150">Stellt Methoden bereit, mit denen der Hostinformationen zu angeforderten Tasks und Deadlocks in der Synchronisierungs Implementierung erhält.</span><span class="sxs-lookup"><span data-stu-id="43340-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="43340-151">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-151">ICLRTask Interface</span></span>](iclrtask-interface.md)  
 <span data-ttu-id="43340-152">Stellt Methoden bereit, die es dem Host ermöglichen, Anforderungen an die CLR zu senden oder die CLR über die zugeordnete Aufgabe benachrichtigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="43340-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="43340-153">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-153">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)  
 <span data-ttu-id="43340-154">Stellt Methoden bereit, die es dem Host ermöglichen, explizit anzufordern, dass die CLR einen neuen Task erstellt, die aktuell ausgeführte Aufgabe erhält und die geografische Sprache und Kultur für den Task festgelegt.</span><span class="sxs-lookup"><span data-stu-id="43340-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="43340-155">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-155">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)  
 <span data-ttu-id="43340-156">Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="43340-157">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-157">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)  
 <span data-ttu-id="43340-158">Stellt Methoden zum Konfigurieren der CLR bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="43340-159">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-159">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)  
 <span data-ttu-id="43340-160">Stellt Methoden für den Zugriff auf den Thread Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="43340-161">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-161">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)  
 <span data-ttu-id="43340-162">Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="43340-163">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-163">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="43340-164">Stellt Methoden bereit, mit denen der Host über die Blockierung und Aufhebung der Blockierung von Threads durch die Debugdienste benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="43340-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="43340-165">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-165">IGCHost Interface</span></span>](igchost-interface.md)  
 <span data-ttu-id="43340-166">Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="43340-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="43340-167">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-167">IGCHost2 Interface</span></span>](igchost2-interface.md)  
 <span data-ttu-id="43340-168">Stellt die [setgcstartuplimitsex](igchost2-setgcstartuplimitsex-method.md) -Methode bereit, die es einem Host ermöglicht, die Größe des Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte größer als festzulegen `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="43340-168">Provides the [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="43340-169">IGCHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-169">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)  
 <span data-ttu-id="43340-170">Stellt eine Methode bereit, die es dem Garbage Collector ermöglicht, den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.</span><span class="sxs-lookup"><span data-stu-id="43340-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="43340-171">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-171">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)  
 <span data-ttu-id="43340-172">Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für Garbage Collection blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="43340-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="43340-173">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-173">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)  
 <span data-ttu-id="43340-174">Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die von der CLR oder vom Host geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="43340-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="43340-175">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-175">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)  
 <span data-ttu-id="43340-176">Stellt Methoden bereit, mit denen ein Host Assemblys und Module unabhängig von der CLR laden kann.</span><span class="sxs-lookup"><span data-stu-id="43340-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="43340-177">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-177">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)  
 <span data-ttu-id="43340-178">Stellt eine Darstellung eines vom Host implementierten automatischen Zurücksetzungs Ereignisses bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="43340-179">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-179">IHostControl Interface</span></span>](ihostcontrol-interface.md)  
 <span data-ttu-id="43340-180">Bietet Methoden zum Konfigurieren des Ladens von Assemblys und zum bestimmen, welche Hostingschnittstellen der Host unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43340-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="43340-181">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-181">IHostCrst Interface</span></span>](ihostcrst-interface.md)  
 <span data-ttu-id="43340-182">Dient als Host Darstellung eines kritischen Abschnitts zum Threading.</span><span class="sxs-lookup"><span data-stu-id="43340-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="43340-183">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-183">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)  
 <span data-ttu-id="43340-184">Stellt Methoden bereit, die den Host von Ereignissen in der von der CLR implementierten Garbage Collection Mechanismus benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="43340-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="43340-185">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-185">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="43340-186">Stellt Methoden bereit, mit denen die CLR mit e/a-Abschlussports interagieren kann, die vom Host bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="43340-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="43340-187">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-187">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)  
 <span data-ttu-id="43340-188">Stellt Methoden für die CLR bereit, um differenzierte Zuordnungen vom Heap über den Host anzufordern.</span><span class="sxs-lookup"><span data-stu-id="43340-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="43340-189">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-189">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)  
 <span data-ttu-id="43340-190">Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="43340-191">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-191">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)  
 <span data-ttu-id="43340-192">Stellt Methoden für die CLR bereit, um virtuelle Speicheranforderungen über den Host zu erstellen, statt die standardmäßigen Win32-Funktionen für den virtuellen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="43340-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="43340-193">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-193">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)  
 <span data-ttu-id="43340-194">Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die CLR im Falle von Abbrüche, Timeouts oder Fehlern ausführt.</span><span class="sxs-lookup"><span data-stu-id="43340-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="43340-195">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-195">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)  
 <span data-ttu-id="43340-196">Ermöglicht der CLR die Verwaltung von Sicherheitskontext Informationen, die vom Host implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="43340-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="43340-197">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-197">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)  
 <span data-ttu-id="43340-198">Stellt Methoden bereit, die den Zugriff auf den Sicherheitskontext des aktuell ausgeführten Threads ermöglichen und dessen Steuerung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="43340-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="43340-199">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-199">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)  
 <span data-ttu-id="43340-200">Stellt eine Darstellung eines Semaphors bereit, der vom Host implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="43340-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="43340-201">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-201">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="43340-202">Stellt Methoden für die CLR bereit, um Synchronisierungs primitive durch Aufrufen des Hosts zu erstellen, statt die Win32-Synchronisierungs Funktionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="43340-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="43340-203">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-203">IHostTask Interface</span></span>](ihosttask-interface.md)  
 <span data-ttu-id="43340-204">Stellt Methoden bereit, mit denen die CLR mit dem Host kommunizieren kann, um Aufgaben zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="43340-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="43340-205">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-205">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)  
 <span data-ttu-id="43340-206">Stellt Methoden bereit, mit denen die CLR mit Aufgaben über den Host arbeiten kann, anstatt die Threading-oder Fiber-Funktionen des Standard Betriebssystems zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="43340-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="43340-207">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-207">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="43340-208">Stellt Methoden für die CLR bereit, um den Thread Pool zu konfigurieren und Arbeitselemente in die Warteschlange des Thread Pools zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="43340-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="43340-209">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-209">IManagedObject Interface</span></span>](imanagedobject-interface.md)  
 <span data-ttu-id="43340-210">Stellt Methoden zum Steuern eines verwalteten Objekts bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="43340-211">IObjectHandle</span><span class="sxs-lookup"><span data-stu-id="43340-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="43340-212">Stellt eine Methode zum Entpacken von Marshal-by-Value-Objekten aus der Dereferenzierung bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="43340-213">ITypeName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-213">ITypeName Interface</span></span>](itypename-interface.md)  
 <span data-ttu-id="43340-214">Stellt Methoden zum Abrufen von Informationen zum Typnamen bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="43340-215">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)</span><span class="sxs-lookup"><span data-stu-id="43340-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="43340-216">ITypeNameBuilder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-216">ITypeNameBuilder Interface</span></span>](itypenamebuilder-interface.md)  
 <span data-ttu-id="43340-217">Stellt Methoden zum Entwickeln eines Typnamens bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-217">Provides methods for building a type name.</span></span> <span data-ttu-id="43340-218">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)</span><span class="sxs-lookup"><span data-stu-id="43340-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="43340-219">ITypeNameFactory-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43340-219">ITypeNameFactory Interface</span></span>](itypenamefactory-interface.md)  
 <span data-ttu-id="43340-220">Stellt Methoden zum dekonstruieren eines Typnamens bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="43340-221">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)</span><span class="sxs-lookup"><span data-stu-id="43340-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="43340-222">IValidator</span><span class="sxs-lookup"><span data-stu-id="43340-222">"IValidator"</span></span>  
 <span data-ttu-id="43340-223">Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="43340-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43340-224">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="43340-224">Related Sections</span></span>  

 [<span data-ttu-id="43340-225">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="43340-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="43340-226">Enthält Themen, in denen die Hostingschnittstellen in den .NET Framework Version 1,0 und 1,1 beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="43340-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="43340-227">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="43340-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="43340-228">Enthält Themen, in denen die Hostingschnittstellen in den .NET Framework 4 beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="43340-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
