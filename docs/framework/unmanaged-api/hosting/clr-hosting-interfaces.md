---
title: CLR-Hostingschnittstellen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3efdf649d0039f2eb6b39d5cb17c839b90e97508
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="a47ed-102">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a47ed-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="a47ed-103">Dieser Abschnitt beschreibt die Schnittstellen, die nicht verwaltete Hosts können Sie die common Language Runtime (CLR) in ihre Anwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="a47ed-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="a47ed-104">Die Informationen bezieht sich auf die Version von .NET Framework 2.0 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="a47ed-105">Diese Schnittstellen aktivieren Sie den Host zu steuern, zahlreiche weitere Aspekte der Laufzeit, als dies in den Versionen 1.0 und 1.1 möglich war, und geben eine engere Integration zwischen der CLR und Ausführungsmodell des Hosts.</span><span class="sxs-lookup"><span data-stu-id="a47ed-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="a47ed-106">In .NET Framework, Version 1.0 und 1.1 aktiviert die Host-Modell einen nicht verwalteten Host zum Laden der CLR in einen Prozess, um bestimmte Einstellungen konfigurieren und ereignisbenachrichtigungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="a47ed-107">Allerdings ausgeführt hat, im Allgemeinen dem Host und der CLR unabhängig im jeweiligen Prozess.</span><span class="sxs-lookup"><span data-stu-id="a47ed-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="a47ed-108">In der .NET Framework Version 2.0 und höheren Versionen können neue Ebenen Abstraktionsebene Hosts bereitzustellen Großteil der Ressourcen, die derzeit von den Typen in der Win32-Assembly bereitgestellt, und erweitern Sie den Satz von Funktionen, die der Host konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="a47ed-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a47ed-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a47ed-109">In This Section</span></span>  
 [<span data-ttu-id="a47ed-110">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="a47ed-111">Stellt eine Methode, die einen Rückruf für ein registriertes Ereignis ausführt.</span><span class="sxs-lookup"><span data-stu-id="a47ed-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="a47ed-112">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="a47ed-113">Stellt Methoden für Rückrufe innerhalb eines Apartments bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="a47ed-114">IAppDomainBinding-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="a47ed-115">Stellt Methoden zum Festlegen der Konfiguration zur Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="a47ed-116">ICatalogServices-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="a47ed-117">Stellt Methoden zum Katalogisieren von Diensten bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="a47ed-118">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="a47ed-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="a47ed-119">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="a47ed-120">Enthält Methoden, die Kommunikation zwischen dem Host und der CLR zu Assemblys zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="a47ed-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="a47ed-122">Verwaltet eine Liste der Assemblys, die von der CLR und nicht vom Host geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a47ed-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="a47ed-123">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="a47ed-124">Stellt Methoden für den Zugriff auf, und konfigurieren verschiedene Aspekte der CLR-Host bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="a47ed-125">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="a47ed-126">Enthält Methoden, mit die einen Host eine Reihe von Aufgaben mit einem Bezeichner und einen Anzeigenamen zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="a47ed-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="a47ed-127">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="a47ed-128">Enthält Methoden, die den Host so konfigurieren Sie benutzerdefinierte Heapdumps für die Fehlerberichterstattung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a47ed-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="a47ed-129">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="a47ed-130">Enthält Methoden, die einen Host für die Interaktion mit der CLR Garbage Collection-System zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a47ed-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="a47ed-131">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="a47ed-132">Stellt Methoden für den Host zum Auswerten und kommunizieren von Änderungen in Richtlinieninformationen für Assemblys bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="a47ed-133">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="a47ed-134">Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder in teilweise vertrauenswürdigem Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a47ed-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="a47ed-135">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="a47ed-136">Implementiert eine Rückrufmethode, die den Host zu benachrichtigen, die CLR über den Status der angegebenen e/a-Anfragen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a47ed-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="a47ed-137">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="a47ed-138">Ermöglicht es dem Host mit einem Ansatz ähnelt der des Win32-speicherauslastung des Berichts `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="a47ed-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="a47ed-139">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="a47ed-140">Enthält Methoden, die den Host zu registrieren und Aufheben der Rückrufe für CLR-Ereignisse zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a47ed-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="a47ed-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="a47ed-142">Enthält Methoden, mit die den Host Geben Sie die für Richtlinienaktionen, die im Falle von Fehlern und Timeouts ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="a47ed-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="a47ed-143">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="a47ed-144">Enthält Methoden, mit denen der Host zum Abrufen der gesuchten Identitäten einer Assembly mit der Assembly aneinander gehängt Identitätsinformationen, die ohne erstellen oder zu verstehen, die Identität für die CLR intern ist.</span><span class="sxs-lookup"><span data-stu-id="a47ed-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="a47ed-145">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="a47ed-146">Enthält Methoden, mit die den Host den Satz von Assemblys, auf eine Datei oder einen Stream mit der Assemblyidentitätsdaten, die für die CLR intern ist, ohne diese Identitäten erstellen oder verstehen verweist bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="a47ed-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="a47ed-147">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="a47ed-148">Bietet Funktionen, die ähnlich wie [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), mit der eine weitere Methode zum Festlegen der Schnittstelle des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="a47ed-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="a47ed-149">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="a47ed-150">Stellt Methoden für den Host zum Abrufen von Informationen zur angeforderten Aufgaben und zum Erkennen von Deadlocks in seiner Implementierung Synchronisierung bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="a47ed-151">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="a47ed-152">Enthält Methoden, mit denen den Host aus, um die Anforderungen der CLR auszuführen oder um eine Benachrichtigung an die CLR über die zugewiesene Aufgabe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="a47ed-153">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="a47ed-154">Enthält Methoden, die den Host explizit anfordern, dass CLR Erstellen eines neuen Tasks, die aktuell ausgeführte Aufgabe abrufen und festlegen, die geografische Sprache und Kultur für den Task zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a47ed-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="a47ed-155">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="a47ed-156">Stellt Methoden zum Überprüfen von portablen ausführbaren Datei (PE) Bilder aus, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="a47ed-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="a47ed-157">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="a47ed-158">Stellt Methoden zum Konfigurieren der CLR.</span><span class="sxs-lookup"><span data-stu-id="a47ed-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="a47ed-159">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="a47ed-160">Stellt Methoden für den Zugriff auf den Threadpool bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="a47ed-161">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="a47ed-162">Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="a47ed-163">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="a47ed-164">Stellt Methoden zum Benachrichtigen des Hosts über die Blockierung und zum Aufheben der Blockierung von Threads von den Debugdiensten bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="a47ed-165">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="a47ed-166">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern des einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="a47ed-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="a47ed-167">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="a47ed-168">Stellt die [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode, die einen Host für die Größe der Garbage Collection-Segment und die maximale Größe der Generation 0 (null), die Garbage Collection-System Werte größer als festzulegen ermöglicht `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="a47ed-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="a47ed-169">IGCHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="a47ed-170">Stellt eine Methode, die der Garbage Collector, den Host zum Ändern der Grenzen des virtuellen Speichers ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a47ed-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="a47ed-171">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="a47ed-172">Stellt Methoden für die Einbeziehung in die Planung von Threads, die andernfalls für die Garbagecollection blockiert werden würde.</span><span class="sxs-lookup"><span data-stu-id="a47ed-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="a47ed-173">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="a47ed-174">Enthält Methoden, mit denen einen Host Sätze von Assemblys angeben, die von der CLR oder vom Host geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a47ed-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="a47ed-175">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="a47ed-176">Enthält Methoden, die einen Host zum Laden von Assemblys und Modulen unabhängig von der CLR zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a47ed-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="a47ed-177">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="a47ed-178">Bietet eine Darstellung eines vom Host implementierte AutoReset-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="a47ed-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="a47ed-179">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="a47ed-180">Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="a47ed-181">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="a47ed-182">Dient als Host Darstellung eines kritischen Abschnitts für threading.</span><span class="sxs-lookup"><span data-stu-id="a47ed-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="a47ed-183">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="a47ed-184">Enthält Methoden, die den Host der Ereignisse in die Garbage Collection-Mechanismus implementiert, die von der CLR zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="a47ed-185">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="a47ed-186">Enthält Methoden, die die CLR für die Interaktion mit e/a-Abschlussports vom Host zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="a47ed-187">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="a47ed-188">Stellt Methoden für die CLR eine präzisere Zuordnungen aus dem Heap über den Host anfordern.</span><span class="sxs-lookup"><span data-stu-id="a47ed-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="a47ed-189">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="a47ed-190">Stellt den Host-Implementierung der eine Repräsentation ein Ereignis für manuelles Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="a47ed-191">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="a47ed-192">Stellt Methoden für die CLR über den Host, anstelle der standardmäßigen Win32 virtueller Arbeitsspeicher Funktionen virtueller Arbeitsspeicher anzufordern.</span><span class="sxs-lookup"><span data-stu-id="a47ed-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="a47ed-193">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="a47ed-194">Enthält Methoden, mit die benachrichtigt der Host über die Aktionen, die im Fall von die CLR führt abbricht, Timeouts oder Fehlern.</span><span class="sxs-lookup"><span data-stu-id="a47ed-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="a47ed-195">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="a47ed-196">Aktiviert die CLR vom Host implementiert wurde Sicherheitskontextinformationen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a47ed-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="a47ed-197">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="a47ed-198">Stellt Methoden, die zum Aktivieren des Zugriffs auf und die Kontrolle über den Sicherheitskontext des aktuell ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="a47ed-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="a47ed-199">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="a47ed-200">Bietet eine Darstellung einer vom Host implementierte Semaphore.</span><span class="sxs-lookup"><span data-stu-id="a47ed-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="a47ed-201">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="a47ed-202">Stellt Methoden für die CLR Synchronisierungsprimitive durch Aufrufen des Hosts, anstatt die Win32-Synchronisierungsfunktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="a47ed-203">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="a47ed-204">Enthält Methoden, die die CLR für die Kommunikation mit dem Host zum Verwalten von Aufgaben ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="a47ed-205">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="a47ed-206">Enthält Methoden, die die CLR arbeiten mit Aufgaben, die über den Host anstatt das standard-Betriebssystems threading oder Fiber-Funktionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a47ed-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="a47ed-207">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="a47ed-208">Stellt Methoden für die CLR den Threadpool konfigurieren und Arbeitsaufgaben für den Threadpool in die Warteschlange bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="a47ed-209">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="a47ed-210">Stellt Methoden zum Steuern von eines verwalteten Objekts.</span><span class="sxs-lookup"><span data-stu-id="a47ed-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="a47ed-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="a47ed-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="a47ed-212">Stellt eine Methode zum Entpacken Marshal-by-Value-Objekten aus Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="a47ed-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="a47ed-213">ITypeName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="a47ed-214">Stellt Methoden zum Abrufen von Name-Typinformationen.</span><span class="sxs-lookup"><span data-stu-id="a47ed-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="a47ed-215">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="a47ed-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="a47ed-216">ITypeNameBuilder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="a47ed-217">Stellt Methoden zum Erstellen eines Typnamens bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-217">Provides methods for building a type name.</span></span> <span data-ttu-id="a47ed-218">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="a47ed-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="a47ed-219">ITypeNameFactory-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ed-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="a47ed-220">Stellt Methoden zum Zerlegen eines Typnamens bereit.</span><span class="sxs-lookup"><span data-stu-id="a47ed-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="a47ed-221">(Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="a47ed-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="a47ed-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="a47ed-222">"IValidator"</span></span>  
 <span data-ttu-id="a47ed-223">Stellt Methoden zum Überprüfen von portablen ausführbaren Datei (PE) Bilder aus, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="a47ed-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a47ed-224">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a47ed-224">Related Sections</span></span>  
 [<span data-ttu-id="a47ed-225">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="a47ed-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="a47ed-226">Enthält Themen, die in .NET Framework, Version 1.0 und 1.1 bereitgestellten Hostingschnittstellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a47ed-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="a47ed-227">CLR-Hostingschnittstellen hinzugefügt in .NET Framework 4 und 4.5</span><span class="sxs-lookup"><span data-stu-id="a47ed-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="a47ed-228">Enthält Themen, die bereitgestellten Hostingschnittstellen beschreiben, die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47ed-228">Contains topics that describe the hosting interfaces provided in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>
