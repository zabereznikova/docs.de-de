---
title: "ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6384700c7039cb705f2db759ebd3d733bf8954ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="11cab-102">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="11cab-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="11cab-103">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="11cab-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="11cab-104">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="11cab-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="11cab-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="11cab-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="11cab-106">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="11cab-107">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="11cab-108">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="11cab-109">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="11cab-110">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="11cab-111">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="11cab-112">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="11cab-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="11cab-113">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="11cab-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="11cab-114">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="11cab-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="11cab-115">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="11cab-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="11cab-116">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="11cab-116">Keyword for raising the event</span></span>|<span data-ttu-id="11cab-117">Ebene</span><span class="sxs-lookup"><span data-stu-id="11cab-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="11cab-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="11cab-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="11cab-119">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-119">Informational(4)</span></span>|  
|<span data-ttu-id="11cab-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="11cab-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="11cab-121">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="11cab-122">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="11cab-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="11cab-123">Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-123">Event</span></span>|<span data-ttu-id="11cab-124">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="11cab-124">Event ID</span></span>|<span data-ttu-id="11cab-125">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="11cab-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="11cab-126">85</span><span class="sxs-lookup"><span data-stu-id="11cab-126">85</span></span>|<span data-ttu-id="11cab-127">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="11cab-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="11cab-128">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="11cab-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="11cab-129">Feldname</span><span class="sxs-lookup"><span data-stu-id="11cab-129">Field name</span></span>|<span data-ttu-id="11cab-130">Datentyp</span><span class="sxs-lookup"><span data-stu-id="11cab-130">Data type</span></span>|<span data-ttu-id="11cab-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11cab-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="11cab-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="11cab-132">ThreadID</span></span>|<span data-ttu-id="11cab-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-133">win:UInt64</span></span>|<span data-ttu-id="11cab-134">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="11cab-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="11cab-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="11cab-135">AppDomainID</span></span>|<span data-ttu-id="11cab-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-136">win:UInt64</span></span>|<span data-ttu-id="11cab-137">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="11cab-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="11cab-138">Flags</span><span class="sxs-lookup"><span data-stu-id="11cab-138">Flags</span></span>|<span data-ttu-id="11cab-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="11cab-139">win:UInt32</span></span>|<span data-ttu-id="11cab-140">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="11cab-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="11cab-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="11cab-141">ManagedThreadIndex</span></span>|<span data-ttu-id="11cab-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="11cab-142">win:UInt32</span></span>|<span data-ttu-id="11cab-143">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="11cab-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="11cab-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="11cab-144">OSThreadID</span></span>|<span data-ttu-id="11cab-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="11cab-145">win:UInt32</span></span>|<span data-ttu-id="11cab-146">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="11cab-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="11cab-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="11cab-147">ClrInstanceID</span></span>|<span data-ttu-id="11cab-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="11cab-148">win:UInt16</span></span>|<span data-ttu-id="11cab-149">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="11cab-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="11cab-150">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="11cab-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="11cab-151">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="11cab-152">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="11cab-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="11cab-153">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="11cab-153">Keyword for raising the event</span></span>|<span data-ttu-id="11cab-154">Ebene</span><span class="sxs-lookup"><span data-stu-id="11cab-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="11cab-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="11cab-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="11cab-156">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="11cab-157">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="11cab-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="11cab-158">Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-158">Event</span></span>|<span data-ttu-id="11cab-159">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="11cab-159">Event ID</span></span>|<span data-ttu-id="11cab-160">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="11cab-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="11cab-161">83</span><span class="sxs-lookup"><span data-stu-id="11cab-161">83</span></span>|<span data-ttu-id="11cab-162">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="11cab-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="11cab-163">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="11cab-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="11cab-164">Feldname</span><span class="sxs-lookup"><span data-stu-id="11cab-164">Field name</span></span>|<span data-ttu-id="11cab-165">Datentyp</span><span class="sxs-lookup"><span data-stu-id="11cab-165">Data type</span></span>|<span data-ttu-id="11cab-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11cab-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="11cab-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="11cab-167">AppDomainID</span></span>|<span data-ttu-id="11cab-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-168">win:UInt64</span></span>|<span data-ttu-id="11cab-169">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="11cab-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="11cab-170">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="11cab-170">Allocated</span></span>|<span data-ttu-id="11cab-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-171">win:UInt64</span></span>|<span data-ttu-id="11cab-172">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="11cab-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="11cab-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="11cab-173">ClrInstanceID</span></span>|<span data-ttu-id="11cab-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="11cab-174">win:UInt16</span></span>|<span data-ttu-id="11cab-175">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="11cab-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="11cab-176">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="11cab-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="11cab-177">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="11cab-178">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="11cab-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="11cab-179">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="11cab-179">Keyword for raising the event</span></span>|<span data-ttu-id="11cab-180">Ebene</span><span class="sxs-lookup"><span data-stu-id="11cab-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="11cab-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="11cab-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="11cab-182">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="11cab-183">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="11cab-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="11cab-184">Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-184">Event</span></span>|<span data-ttu-id="11cab-185">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="11cab-185">Event ID</span></span>|<span data-ttu-id="11cab-186">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="11cab-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="11cab-187">84</span><span class="sxs-lookup"><span data-stu-id="11cab-187">84</span></span>|<span data-ttu-id="11cab-188">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="11cab-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="11cab-189">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="11cab-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="11cab-190">Feldname</span><span class="sxs-lookup"><span data-stu-id="11cab-190">Field name</span></span>|<span data-ttu-id="11cab-191">Datentyp</span><span class="sxs-lookup"><span data-stu-id="11cab-191">Data type</span></span>|<span data-ttu-id="11cab-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11cab-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="11cab-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="11cab-193">AppDomainID</span></span>|<span data-ttu-id="11cab-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-194">win:UInt64</span></span>|<span data-ttu-id="11cab-195">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="11cab-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="11cab-196">Noch vorhanden</span><span class="sxs-lookup"><span data-stu-id="11cab-196">Survived</span></span>|<span data-ttu-id="11cab-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-197">win:UInt64</span></span>|<span data-ttu-id="11cab-198">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="11cab-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="11cab-199">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="11cab-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="11cab-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="11cab-200">ProcessSurvived</span></span>|<span data-ttu-id="11cab-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-201">win:UInt64</span></span>|<span data-ttu-id="11cab-202">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="11cab-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="11cab-203">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="11cab-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="11cab-204">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="11cab-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="11cab-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="11cab-205">ClrInstanceID</span></span>|<span data-ttu-id="11cab-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="11cab-206">win:UInt16</span></span>|<span data-ttu-id="11cab-207">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="11cab-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="11cab-208">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="11cab-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="11cab-209">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="11cab-210">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="11cab-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="11cab-211">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="11cab-211">Keyword for raising the event</span></span>|<span data-ttu-id="11cab-212">Ebene</span><span class="sxs-lookup"><span data-stu-id="11cab-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="11cab-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="11cab-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="11cab-214">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-214">Informational(4)</span></span>|  
|<span data-ttu-id="11cab-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="11cab-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="11cab-216">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="11cab-217">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="11cab-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="11cab-218">Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-218">Event</span></span>|<span data-ttu-id="11cab-219">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="11cab-219">Event ID</span></span>|<span data-ttu-id="11cab-220">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="11cab-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="11cab-221">87</span><span class="sxs-lookup"><span data-stu-id="11cab-221">87</span></span>|<span data-ttu-id="11cab-222">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="11cab-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="11cab-223">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="11cab-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="11cab-224">Feldname</span><span class="sxs-lookup"><span data-stu-id="11cab-224">Field name</span></span>|<span data-ttu-id="11cab-225">Datentyp</span><span class="sxs-lookup"><span data-stu-id="11cab-225">Data type</span></span>|<span data-ttu-id="11cab-226">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11cab-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="11cab-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="11cab-227">ThreadID</span></span>|<span data-ttu-id="11cab-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-228">win:UInt64</span></span>|<span data-ttu-id="11cab-229">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="11cab-229">The thread identifier.</span></span>|  
|<span data-ttu-id="11cab-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="11cab-230">AppDomainID</span></span>|<span data-ttu-id="11cab-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-231">win:UInt64</span></span>|<span data-ttu-id="11cab-232">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="11cab-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="11cab-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="11cab-233">ClrInstanceID</span></span>|<span data-ttu-id="11cab-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="11cab-234">win:UInt16</span></span>|<span data-ttu-id="11cab-235">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="11cab-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="11cab-236">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="11cab-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="11cab-237">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="11cab-238">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="11cab-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="11cab-239">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="11cab-239">Keyword for raising the event</span></span>|<span data-ttu-id="11cab-240">Ebene</span><span class="sxs-lookup"><span data-stu-id="11cab-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="11cab-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="11cab-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="11cab-242">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-242">Informational(4)</span></span>|  
|<span data-ttu-id="11cab-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="11cab-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="11cab-244">Information (4)</span><span class="sxs-lookup"><span data-stu-id="11cab-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="11cab-245">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="11cab-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="11cab-246">Ereignis</span><span class="sxs-lookup"><span data-stu-id="11cab-246">Event</span></span>|<span data-ttu-id="11cab-247">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="11cab-247">Event ID</span></span>|<span data-ttu-id="11cab-248">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="11cab-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="11cab-249">86</span><span class="sxs-lookup"><span data-stu-id="11cab-249">86</span></span>|<span data-ttu-id="11cab-250">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="11cab-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="11cab-251">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="11cab-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="11cab-252">Feldname</span><span class="sxs-lookup"><span data-stu-id="11cab-252">Field name</span></span>|<span data-ttu-id="11cab-253">Datentyp</span><span class="sxs-lookup"><span data-stu-id="11cab-253">Data type</span></span>|<span data-ttu-id="11cab-254">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11cab-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="11cab-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="11cab-255">ThreadID</span></span>|<span data-ttu-id="11cab-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-256">win:UInt64</span></span>|<span data-ttu-id="11cab-257">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="11cab-257">The thread identifier.</span></span>|  
|<span data-ttu-id="11cab-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="11cab-258">AppDomainID</span></span>|<span data-ttu-id="11cab-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="11cab-259">win:UInt64</span></span>|<span data-ttu-id="11cab-260">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="11cab-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="11cab-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="11cab-261">ClrInstanceID</span></span>|<span data-ttu-id="11cab-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="11cab-262">win:UInt16</span></span>|<span data-ttu-id="11cab-263">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="11cab-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11cab-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11cab-264">See Also</span></span>  
 [<span data-ttu-id="11cab-265">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="11cab-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
