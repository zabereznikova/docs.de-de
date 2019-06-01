---
title: CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80404e65263aa4ad245a8c8213630a4736bd7b11
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456883"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="49056-102">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="49056-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="49056-103">In diesem Abschnitt wird beschrieben, die Schnittstellen, die nicht verwaltete Hosts können die common Language Runtime (CLR) in ihre Anwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="49056-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="49056-104">Die Informationen bezieht sich auf die Version von .NET Framework 2.0 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="49056-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="49056-105">Diese Schnittstellen aktivieren Sie den Host zu steuern, zahlreiche weitere Aspekte der Laufzeit als in den Versionen 1.0 und 1.1 möglich war, und geben eine engere Integration zwischen der CLR und Ausführungsmodell des Hosts.</span><span class="sxs-lookup"><span data-stu-id="49056-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="49056-106">In .NET Framework, Version 1.0 und 1.1 aktiviert das hosting-Modell einen nicht verwalteten Host zum Laden der CLR in einen Prozess, um bestimmte Einstellungen zu konfigurieren und ereignisbenachrichtigungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="49056-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="49056-107">Allerdings wurde ausgeführt im Allgemeinen dem Host und die CLR unabhängig voneinander in diesem Prozess.</span><span class="sxs-lookup"><span data-stu-id="49056-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="49056-108">In der .NET Framework, Version 2.0 und höheren Versionen können neue Ebenen der Abstraktion den Host bieten viele der Ressourcen, die derzeit von den Typen in der Win32-Assembly bereitgestellt werden soll, und erweitern Sie den Satz von Funktionen, die der Host konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="49056-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49056-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="49056-109">In This Section</span></span>  
 [<span data-ttu-id="49056-110">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="49056-111">Stellt eine Methode, die einen Rückruf für ein registriertes Ereignis durchführt.</span><span class="sxs-lookup"><span data-stu-id="49056-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="49056-112">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="49056-113">Stellt Methoden für Rückrufe innerhalb einer Apartment.</span><span class="sxs-lookup"><span data-stu-id="49056-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="49056-114">IAppDomainBinding-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="49056-115">Stellt Methoden zum Festlegen der Runtime-Konfiguration bereit.</span><span class="sxs-lookup"><span data-stu-id="49056-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="49056-116">ICatalogServices-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="49056-117">Stellt Methoden zum Katalogisieren von Diensten bereit.</span><span class="sxs-lookup"><span data-stu-id="49056-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="49056-118">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="49056-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="49056-119">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="49056-120">Enthält Methoden, die Kommunikation zwischen dem Host und der CLR Informationen zu Assemblys zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="49056-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="49056-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="49056-122">Verwaltet eine Liste der Assemblys, die von der CLR und nicht vom Host geladen werden.</span><span class="sxs-lookup"><span data-stu-id="49056-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="49056-123">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="49056-124">Stellt Methoden für den Zugriff auf, und konfigurieren verschiedene Aspekte der CLR-Host bereit.</span><span class="sxs-lookup"><span data-stu-id="49056-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="49056-125">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="49056-126">Bietet Methoden, mit die einen Host eine Reihe von Aufgaben mit einem Bezeichner sowie einen Anzeigenamen zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="49056-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="49056-127">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="49056-128">Bietet Methoden, mit die den Host benutzerdefinierte Heap-Sicherungen für die Fehlerberichterstattung konfigurieren zu können.</span><span class="sxs-lookup"><span data-stu-id="49056-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="49056-129">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="49056-130">Enthält Methoden, die einen Host für die Interaktion mit der CLR Garbage Collection-System zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="49056-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="49056-131">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="49056-132">Stellt Methoden für den Host zum Auswerten und Übermitteln von Änderungen in Richtlinieninformationen für Assemblys.</span><span class="sxs-lookup"><span data-stu-id="49056-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="49056-133">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="49056-134">Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder aus, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="49056-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="49056-135">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="49056-136">Implementiert eine Rückrufmethode, die den Host zu benachrichtigen, die CLR über den Status der angegebenen e/a-Anforderungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="49056-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="49056-137">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="49056-138">Ermöglicht dem Host, den Berichts-speicherauslastung, die mit einem Ansatz ähnelt der von der Win32 `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="49056-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="49056-139">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="49056-140">Bietet Methoden, mit denen den Host zu registrieren und Aufheben der Registrierung von Rückrufen für CLR-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="49056-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="49056-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="49056-142">Enthält Methoden, die den Host Geben Sie die, die bei Fehlern oder Timeouts auszuführenden Richtlinienaktionen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="49056-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="49056-143">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="49056-144">Bietet Methoden, mit denen der Host zum Abrufen der gesuchten Identitäten einer Assembly mit Informationen zur Identität der Assembly, die zum Erstellen oder zu verstehen, die diese Identität ohne intern für die CLR ist.</span><span class="sxs-lookup"><span data-stu-id="49056-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="49056-145">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="49056-146">Bietet Methoden, mit die den Host den Satz von Assemblys, die auf die verwiesen wird von einer Datei oder den Stream unter Verwendung von Assembly-Identitätsdaten, die intern für die CLR ist, ohne diese Identitäten erstellen oder verstehen bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="49056-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="49056-147">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="49056-148">Bietet Funktionen, die ähnlich wie [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), mit der eine weitere Methode zum Festlegen der Schnittstelle des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="49056-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="49056-149">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="49056-150">Stellt Methoden für den Host zum Abrufen von Informationen zu den angeforderten Aufgaben und zum Erkennen von Deadlocks in die Synchronisierung-Implementierung bereit.</span><span class="sxs-lookup"><span data-stu-id="49056-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="49056-151">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="49056-152">Bietet Methoden, mit denen den Host aus, um die Anforderungen der CLR zu erstellen oder eine Benachrichtigung an die CLR über die zugewiesene Aufgabe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="49056-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="49056-153">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="49056-154">Bietet Methoden, mit denen der Host explizit anfordern, dass die CLR erstellen eine neue Aufgabe, die aktuell ausgeführte Aufgabe zu erhalten und legen Sie die geografische Sprache und Kultur für den Task.</span><span class="sxs-lookup"><span data-stu-id="49056-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="49056-155">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="49056-156">Stellt Methoden zum Überprüfen der übertragbaren ausführbaren Datei (PE)-Abbildern, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="49056-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="49056-157">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="49056-158">Stellt Methoden zum Konfigurieren der CLR.</span><span class="sxs-lookup"><span data-stu-id="49056-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="49056-159">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="49056-160">Stellt Methoden für den Zugriff auf den Threadpool.</span><span class="sxs-lookup"><span data-stu-id="49056-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="49056-161">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="49056-162">Stellt Methoden zum Abrufen von Informationen über den Status der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="49056-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="49056-163">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="49056-164">Stellt Methoden zum Benachrichtigen des Hosts über das Blockieren und Entsperren von Threads von den Debugdiensten.</span><span class="sxs-lookup"><span data-stu-id="49056-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="49056-165">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="49056-166">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="49056-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="49056-167">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="49056-168">Stellt die [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode, die einen Host, die Größe der Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 (null) auf Werte größer als festzulegen ermöglicht `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="49056-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="49056-169">IGCHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="49056-170">Stellt eine Methode, die der Garbage Collector, den Host zum Ändern der Grenzen des virtuellen Speichers ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="49056-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="49056-171">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="49056-172">Stellt Methoden für die Teilnahme an der Planung von Threads, die für die Garbagecollection andernfalls blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="49056-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="49056-173">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="49056-174">Bietet Methoden, mit denen einen Host aus, um Assemblys anzugeben, die von der CLR oder vom Host geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="49056-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="49056-175">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="49056-176">Enthält Methoden, die einen Host zum Laden von Assemblys und Modulen unabhängig von der CLR zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="49056-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="49056-177">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="49056-178">Bietet eine Darstellung der ein automatisches Zurücksetzungsereignis vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="49056-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="49056-179">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="49056-180">Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="49056-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="49056-181">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="49056-182">Dient als Darstellung des Hosts in einem kritischen Abschnitt für das Threading teilweise.</span><span class="sxs-lookup"><span data-stu-id="49056-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="49056-183">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="49056-184">Enthält Methoden, die den Host der Ereignisse in die Garbage Collection-Mechanismus implementiert, die von der CLR zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="49056-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="49056-185">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="49056-186">Enthält Methoden, die die CLR für die Interaktion mit e/a-Abschlussports, die vom Host zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="49056-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="49056-187">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="49056-188">Stellt Methoden für die CLR eine differenzierte Zuordnungen aus dem Heap über den Host anfordern.</span><span class="sxs-lookup"><span data-stu-id="49056-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="49056-189">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="49056-190">Stellt eine Darstellung der ein Ereignis mit manueller Rücksetzung Implementierung des Hosts.</span><span class="sxs-lookup"><span data-stu-id="49056-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="49056-191">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="49056-192">Stellt Methoden für die CLR um virtueller Arbeitsspeicher-Anforderungen über den Host, anstatt die standard Win32-Funktionen für virtuellen Arbeitsspeicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49056-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="49056-193">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="49056-194">Enthält Methoden, die der Host der CLR im Fall von durchgeführten Aktionen abgebrochen wird, Timeouts oder Fehlern zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="49056-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="49056-195">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="49056-196">Aktiviert die CLR vom Host implementierte Sicherheitskontextinformationen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="49056-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="49056-197">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="49056-198">Bietet Methoden, mit denen Zugriff auf und Kontrolle über den Sicherheitskontext des gerade ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="49056-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="49056-199">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="49056-200">Bietet eine Darstellung eines Semaphors vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="49056-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="49056-201">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="49056-202">Stellt Methoden für die CLR die Synchronisierungsprimitiven zu erstellen, indem Sie den Host, anstatt die Win32-Synchronisierung-Funktionen aufruft.</span><span class="sxs-lookup"><span data-stu-id="49056-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="49056-203">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="49056-204">Bietet Methoden, mit denen die CLR für die Kommunikation mit dem Host, um Aufgaben zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="49056-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="49056-205">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="49056-206">Enthält Methoden, die die CLR arbeiten mit Aufgaben, die über den Host aus, anstatt die Standardbetriebssystem threading oder Fiber-Funktionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="49056-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="49056-207">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="49056-208">Stellt Methoden für die CLR, die zum Konfigurieren der Threadpool der Warteschleife hinzu und zum Arbeitsaufgaben an den Threadpool-Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="49056-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="49056-209">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="49056-210">Stellt Methoden zum Steuern eines verwalteten Objekts.</span><span class="sxs-lookup"><span data-stu-id="49056-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="49056-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="49056-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="49056-212">Stellt eine Methode für das Entpacken Marshal-by-Value-Objekte aus der Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="49056-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="49056-213">ITypeName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="49056-214">Stellt Methoden zum Abrufen von Typinformationen für Namen bereit.</span><span class="sxs-lookup"><span data-stu-id="49056-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="49056-215">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="49056-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="49056-216">ITypeNameBuilder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="49056-217">Stellt Methoden zum Erstellen eines Typnamens.</span><span class="sxs-lookup"><span data-stu-id="49056-217">Provides methods for building a type name.</span></span> <span data-ttu-id="49056-218">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="49056-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="49056-219">ITypeNameFactory-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49056-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="49056-220">Stellt Methoden zum dekonstruieren von einem Typnamen.</span><span class="sxs-lookup"><span data-stu-id="49056-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="49056-221">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="49056-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="49056-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="49056-222">"IValidator"</span></span>  
 <span data-ttu-id="49056-223">Stellt Methoden zum Überprüfen der übertragbaren ausführbaren Datei (PE)-Abbildern, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="49056-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="49056-224">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="49056-224">Related Sections</span></span>  
 [<span data-ttu-id="49056-225">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="49056-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="49056-226">Enthält Themen, die in .NET Framework, Version 1.0 und 1.1 bereitgestellten Hostingschnittstellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49056-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="49056-227">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="49056-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="49056-228">Enthält Themen, die in .NET Framework 4 bereitgestellten Hostingschnittstellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49056-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
