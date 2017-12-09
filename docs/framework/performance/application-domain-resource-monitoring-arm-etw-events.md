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
ms.openlocfilehash: a93e8cc1ab0b7488f920b556d2073d2813c3b7a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="524e5-102">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="524e5-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="524e5-103">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="524e5-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="524e5-104">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="524e5-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="524e5-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="524e5-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="524e5-106">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="524e5-107">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="524e5-108">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="524e5-109">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="524e5-110">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="524e5-111">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="524e5-112">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="524e5-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="524e5-113">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="524e5-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="524e5-114">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="524e5-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="524e5-115">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="524e5-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="524e5-116">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="524e5-116">Keyword for raising the event</span></span>|<span data-ttu-id="524e5-117">Ebene</span><span class="sxs-lookup"><span data-stu-id="524e5-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="524e5-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="524e5-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="524e5-119">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-119">Informational(4)</span></span>|  
|<span data-ttu-id="524e5-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="524e5-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="524e5-121">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="524e5-122">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="524e5-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="524e5-123">Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-123">Event</span></span>|<span data-ttu-id="524e5-124">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="524e5-124">Event ID</span></span>|<span data-ttu-id="524e5-125">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="524e5-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="524e5-126">85</span><span class="sxs-lookup"><span data-stu-id="524e5-126">85</span></span>|<span data-ttu-id="524e5-127">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="524e5-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="524e5-128">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="524e5-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="524e5-129">Feldname</span><span class="sxs-lookup"><span data-stu-id="524e5-129">Field name</span></span>|<span data-ttu-id="524e5-130">Datentyp</span><span class="sxs-lookup"><span data-stu-id="524e5-130">Data type</span></span>|<span data-ttu-id="524e5-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="524e5-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="524e5-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="524e5-132">ThreadID</span></span>|<span data-ttu-id="524e5-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-133">win:UInt64</span></span>|<span data-ttu-id="524e5-134">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="524e5-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="524e5-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="524e5-135">AppDomainID</span></span>|<span data-ttu-id="524e5-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-136">win:UInt64</span></span>|<span data-ttu-id="524e5-137">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="524e5-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="524e5-138">Flags</span><span class="sxs-lookup"><span data-stu-id="524e5-138">Flags</span></span>|<span data-ttu-id="524e5-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="524e5-139">win:UInt32</span></span>|<span data-ttu-id="524e5-140">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="524e5-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="524e5-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="524e5-141">ManagedThreadIndex</span></span>|<span data-ttu-id="524e5-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="524e5-142">win:UInt32</span></span>|<span data-ttu-id="524e5-143">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="524e5-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="524e5-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="524e5-144">OSThreadID</span></span>|<span data-ttu-id="524e5-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="524e5-145">win:UInt32</span></span>|<span data-ttu-id="524e5-146">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="524e5-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="524e5-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="524e5-147">ClrInstanceID</span></span>|<span data-ttu-id="524e5-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="524e5-148">win:UInt16</span></span>|<span data-ttu-id="524e5-149">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="524e5-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="524e5-150">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="524e5-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="524e5-151">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="524e5-152">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="524e5-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="524e5-153">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="524e5-153">Keyword for raising the event</span></span>|<span data-ttu-id="524e5-154">Ebene</span><span class="sxs-lookup"><span data-stu-id="524e5-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="524e5-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="524e5-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="524e5-156">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="524e5-157">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="524e5-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="524e5-158">Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-158">Event</span></span>|<span data-ttu-id="524e5-159">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="524e5-159">Event ID</span></span>|<span data-ttu-id="524e5-160">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="524e5-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="524e5-161">83</span><span class="sxs-lookup"><span data-stu-id="524e5-161">83</span></span>|<span data-ttu-id="524e5-162">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="524e5-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="524e5-163">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="524e5-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="524e5-164">Feldname</span><span class="sxs-lookup"><span data-stu-id="524e5-164">Field name</span></span>|<span data-ttu-id="524e5-165">Datentyp</span><span class="sxs-lookup"><span data-stu-id="524e5-165">Data type</span></span>|<span data-ttu-id="524e5-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="524e5-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="524e5-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="524e5-167">AppDomainID</span></span>|<span data-ttu-id="524e5-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-168">win:UInt64</span></span>|<span data-ttu-id="524e5-169">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="524e5-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="524e5-170">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="524e5-170">Allocated</span></span>|<span data-ttu-id="524e5-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-171">win:UInt64</span></span>|<span data-ttu-id="524e5-172">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="524e5-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="524e5-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="524e5-173">ClrInstanceID</span></span>|<span data-ttu-id="524e5-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="524e5-174">win:UInt16</span></span>|<span data-ttu-id="524e5-175">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="524e5-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="524e5-176">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="524e5-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="524e5-177">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="524e5-178">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="524e5-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="524e5-179">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="524e5-179">Keyword for raising the event</span></span>|<span data-ttu-id="524e5-180">Ebene</span><span class="sxs-lookup"><span data-stu-id="524e5-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="524e5-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="524e5-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="524e5-182">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="524e5-183">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="524e5-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="524e5-184">Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-184">Event</span></span>|<span data-ttu-id="524e5-185">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="524e5-185">Event ID</span></span>|<span data-ttu-id="524e5-186">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="524e5-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="524e5-187">84</span><span class="sxs-lookup"><span data-stu-id="524e5-187">84</span></span>|<span data-ttu-id="524e5-188">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="524e5-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="524e5-189">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="524e5-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="524e5-190">Feldname</span><span class="sxs-lookup"><span data-stu-id="524e5-190">Field name</span></span>|<span data-ttu-id="524e5-191">Datentyp</span><span class="sxs-lookup"><span data-stu-id="524e5-191">Data type</span></span>|<span data-ttu-id="524e5-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="524e5-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="524e5-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="524e5-193">AppDomainID</span></span>|<span data-ttu-id="524e5-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-194">win:UInt64</span></span>|<span data-ttu-id="524e5-195">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="524e5-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="524e5-196">Noch vorhanden</span><span class="sxs-lookup"><span data-stu-id="524e5-196">Survived</span></span>|<span data-ttu-id="524e5-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-197">win:UInt64</span></span>|<span data-ttu-id="524e5-198">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="524e5-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="524e5-199">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="524e5-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="524e5-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="524e5-200">ProcessSurvived</span></span>|<span data-ttu-id="524e5-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-201">win:UInt64</span></span>|<span data-ttu-id="524e5-202">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="524e5-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="524e5-203">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="524e5-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="524e5-204">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="524e5-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="524e5-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="524e5-205">ClrInstanceID</span></span>|<span data-ttu-id="524e5-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="524e5-206">win:UInt16</span></span>|<span data-ttu-id="524e5-207">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="524e5-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="524e5-208">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="524e5-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="524e5-209">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="524e5-210">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="524e5-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="524e5-211">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="524e5-211">Keyword for raising the event</span></span>|<span data-ttu-id="524e5-212">Ebene</span><span class="sxs-lookup"><span data-stu-id="524e5-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="524e5-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="524e5-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="524e5-214">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-214">Informational(4)</span></span>|  
|<span data-ttu-id="524e5-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="524e5-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="524e5-216">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="524e5-217">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="524e5-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="524e5-218">Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-218">Event</span></span>|<span data-ttu-id="524e5-219">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="524e5-219">Event ID</span></span>|<span data-ttu-id="524e5-220">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="524e5-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="524e5-221">87</span><span class="sxs-lookup"><span data-stu-id="524e5-221">87</span></span>|<span data-ttu-id="524e5-222">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="524e5-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="524e5-223">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="524e5-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="524e5-224">Feldname</span><span class="sxs-lookup"><span data-stu-id="524e5-224">Field name</span></span>|<span data-ttu-id="524e5-225">Datentyp</span><span class="sxs-lookup"><span data-stu-id="524e5-225">Data type</span></span>|<span data-ttu-id="524e5-226">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="524e5-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="524e5-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="524e5-227">ThreadID</span></span>|<span data-ttu-id="524e5-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-228">win:UInt64</span></span>|<span data-ttu-id="524e5-229">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="524e5-229">The thread identifier.</span></span>|  
|<span data-ttu-id="524e5-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="524e5-230">AppDomainID</span></span>|<span data-ttu-id="524e5-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-231">win:UInt64</span></span>|<span data-ttu-id="524e5-232">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="524e5-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="524e5-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="524e5-233">ClrInstanceID</span></span>|<span data-ttu-id="524e5-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="524e5-234">win:UInt16</span></span>|<span data-ttu-id="524e5-235">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="524e5-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="524e5-236">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="524e5-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="524e5-237">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="524e5-238">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="524e5-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="524e5-239">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="524e5-239">Keyword for raising the event</span></span>|<span data-ttu-id="524e5-240">Ebene</span><span class="sxs-lookup"><span data-stu-id="524e5-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="524e5-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="524e5-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="524e5-242">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-242">Informational(4)</span></span>|  
|<span data-ttu-id="524e5-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="524e5-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="524e5-244">Information (4)</span><span class="sxs-lookup"><span data-stu-id="524e5-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="524e5-245">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="524e5-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="524e5-246">Ereignis</span><span class="sxs-lookup"><span data-stu-id="524e5-246">Event</span></span>|<span data-ttu-id="524e5-247">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="524e5-247">Event ID</span></span>|<span data-ttu-id="524e5-248">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="524e5-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="524e5-249">86</span><span class="sxs-lookup"><span data-stu-id="524e5-249">86</span></span>|<span data-ttu-id="524e5-250">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="524e5-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="524e5-251">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="524e5-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="524e5-252">Feldname</span><span class="sxs-lookup"><span data-stu-id="524e5-252">Field name</span></span>|<span data-ttu-id="524e5-253">Datentyp</span><span class="sxs-lookup"><span data-stu-id="524e5-253">Data type</span></span>|<span data-ttu-id="524e5-254">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="524e5-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="524e5-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="524e5-255">ThreadID</span></span>|<span data-ttu-id="524e5-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-256">win:UInt64</span></span>|<span data-ttu-id="524e5-257">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="524e5-257">The thread identifier.</span></span>|  
|<span data-ttu-id="524e5-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="524e5-258">AppDomainID</span></span>|<span data-ttu-id="524e5-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="524e5-259">win:UInt64</span></span>|<span data-ttu-id="524e5-260">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="524e5-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="524e5-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="524e5-261">ClrInstanceID</span></span>|<span data-ttu-id="524e5-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="524e5-262">win:UInt16</span></span>|<span data-ttu-id="524e5-263">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="524e5-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="524e5-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="524e5-264">See Also</span></span>  
 [<span data-ttu-id="524e5-265">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="524e5-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
