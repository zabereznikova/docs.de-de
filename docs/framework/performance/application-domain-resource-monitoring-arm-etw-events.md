---
title: ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bb2b0dd95877fc6492f6d23a19c14688cd78f7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133821"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="c5d83-102">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="c5d83-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="c5d83-103">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="c5d83-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="c5d83-104">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c5d83-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="c5d83-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="c5d83-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="c5d83-106">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="c5d83-107">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="c5d83-108">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="c5d83-109">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="c5d83-110">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="c5d83-111">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="c5d83-112">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="c5d83-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="c5d83-113">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c5d83-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="c5d83-114">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="c5d83-115">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="c5d83-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c5d83-116">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c5d83-116">Keyword for raising the event</span></span>|<span data-ttu-id="c5d83-117">Ebene</span><span class="sxs-lookup"><span data-stu-id="c5d83-117">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c5d83-118">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c5d83-118">(0x800)</span></span>|<span data-ttu-id="c5d83-119">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-119">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="c5d83-120">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="c5d83-120">(0x10000)</span></span>|<span data-ttu-id="c5d83-121">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="c5d83-122">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c5d83-123">event</span><span class="sxs-lookup"><span data-stu-id="c5d83-123">Event</span></span>|<span data-ttu-id="c5d83-124">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c5d83-124">Event ID</span></span>|<span data-ttu-id="c5d83-125">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="c5d83-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="c5d83-126">85</span><span class="sxs-lookup"><span data-stu-id="c5d83-126">85</span></span>|<span data-ttu-id="c5d83-127">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="c5d83-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="c5d83-128">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c5d83-129">Feldname</span><span class="sxs-lookup"><span data-stu-id="c5d83-129">Field name</span></span>|<span data-ttu-id="c5d83-130">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c5d83-130">Data type</span></span>|<span data-ttu-id="c5d83-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5d83-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c5d83-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="c5d83-132">ThreadID</span></span>|<span data-ttu-id="c5d83-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-133">win:UInt64</span></span>|<span data-ttu-id="c5d83-134">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5d83-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="c5d83-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c5d83-135">AppDomainID</span></span>|<span data-ttu-id="c5d83-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-136">win:UInt64</span></span>|<span data-ttu-id="c5d83-137">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="c5d83-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="c5d83-138">Flags</span><span class="sxs-lookup"><span data-stu-id="c5d83-138">Flags</span></span>|<span data-ttu-id="c5d83-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c5d83-139">win:UInt32</span></span>|<span data-ttu-id="c5d83-140">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="c5d83-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="c5d83-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="c5d83-141">ManagedThreadIndex</span></span>|<span data-ttu-id="c5d83-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c5d83-142">win:UInt32</span></span>|<span data-ttu-id="c5d83-143">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5d83-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="c5d83-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="c5d83-144">OSThreadID</span></span>|<span data-ttu-id="c5d83-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c5d83-145">win:UInt32</span></span>|<span data-ttu-id="c5d83-146">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5d83-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="c5d83-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c5d83-147">ClrInstanceID</span></span>|<span data-ttu-id="c5d83-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c5d83-148">win:UInt16</span></span>|<span data-ttu-id="c5d83-149">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c5d83-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c5d83-150">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="c5d83-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="c5d83-151">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="c5d83-152">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c5d83-153">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c5d83-153">Keyword for raising the event</span></span>|<span data-ttu-id="c5d83-154">Ebene</span><span class="sxs-lookup"><span data-stu-id="c5d83-154">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c5d83-155">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c5d83-155">(0x800)</span></span>|<span data-ttu-id="c5d83-156">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="c5d83-157">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c5d83-158">event</span><span class="sxs-lookup"><span data-stu-id="c5d83-158">Event</span></span>|<span data-ttu-id="c5d83-159">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c5d83-159">Event ID</span></span>|<span data-ttu-id="c5d83-160">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="c5d83-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="c5d83-161">83</span><span class="sxs-lookup"><span data-stu-id="c5d83-161">83</span></span>|<span data-ttu-id="c5d83-162">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5d83-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="c5d83-163">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c5d83-164">Feldname</span><span class="sxs-lookup"><span data-stu-id="c5d83-164">Field name</span></span>|<span data-ttu-id="c5d83-165">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c5d83-165">Data type</span></span>|<span data-ttu-id="c5d83-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5d83-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c5d83-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c5d83-167">AppDomainID</span></span>|<span data-ttu-id="c5d83-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-168">win:UInt64</span></span>|<span data-ttu-id="c5d83-169">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="c5d83-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="c5d83-170">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="c5d83-170">Allocated</span></span>|<span data-ttu-id="c5d83-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-171">win:UInt64</span></span>|<span data-ttu-id="c5d83-172">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="c5d83-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="c5d83-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c5d83-173">ClrInstanceID</span></span>|<span data-ttu-id="c5d83-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c5d83-174">win:UInt16</span></span>|<span data-ttu-id="c5d83-175">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c5d83-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c5d83-176">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="c5d83-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="c5d83-177">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="c5d83-178">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c5d83-179">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c5d83-179">Keyword for raising the event</span></span>|<span data-ttu-id="c5d83-180">Ebene</span><span class="sxs-lookup"><span data-stu-id="c5d83-180">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c5d83-181">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c5d83-181">(0x800)</span></span>|<span data-ttu-id="c5d83-182">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="c5d83-183">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c5d83-184">event</span><span class="sxs-lookup"><span data-stu-id="c5d83-184">Event</span></span>|<span data-ttu-id="c5d83-185">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c5d83-185">Event ID</span></span>|<span data-ttu-id="c5d83-186">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="c5d83-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="c5d83-187">84</span><span class="sxs-lookup"><span data-stu-id="c5d83-187">84</span></span>|<span data-ttu-id="c5d83-188">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="c5d83-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="c5d83-189">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c5d83-190">Feldname</span><span class="sxs-lookup"><span data-stu-id="c5d83-190">Field name</span></span>|<span data-ttu-id="c5d83-191">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c5d83-191">Data type</span></span>|<span data-ttu-id="c5d83-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5d83-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c5d83-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c5d83-193">AppDomainID</span></span>|<span data-ttu-id="c5d83-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-194">win:UInt64</span></span>|<span data-ttu-id="c5d83-195">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="c5d83-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="c5d83-196">Noch vorhanden</span><span class="sxs-lookup"><span data-stu-id="c5d83-196">Survived</span></span>|<span data-ttu-id="c5d83-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-197">win:UInt64</span></span>|<span data-ttu-id="c5d83-198">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c5d83-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="c5d83-199">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="c5d83-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="c5d83-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="c5d83-200">ProcessSurvived</span></span>|<span data-ttu-id="c5d83-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-201">win:UInt64</span></span>|<span data-ttu-id="c5d83-202">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c5d83-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="c5d83-203">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c5d83-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="c5d83-204">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c5d83-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="c5d83-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c5d83-205">ClrInstanceID</span></span>|<span data-ttu-id="c5d83-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c5d83-206">win:UInt16</span></span>|<span data-ttu-id="c5d83-207">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c5d83-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c5d83-208">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="c5d83-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="c5d83-209">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="c5d83-210">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c5d83-211">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c5d83-211">Keyword for raising the event</span></span>|<span data-ttu-id="c5d83-212">Ebene</span><span class="sxs-lookup"><span data-stu-id="c5d83-212">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c5d83-213">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c5d83-213">(0x800)</span></span>|<span data-ttu-id="c5d83-214">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-214">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="c5d83-215">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="c5d83-215">(0x10000)</span></span>|<span data-ttu-id="c5d83-216">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="c5d83-217">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c5d83-218">event</span><span class="sxs-lookup"><span data-stu-id="c5d83-218">Event</span></span>|<span data-ttu-id="c5d83-219">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c5d83-219">Event ID</span></span>|<span data-ttu-id="c5d83-220">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="c5d83-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="c5d83-221">87</span><span class="sxs-lookup"><span data-stu-id="c5d83-221">87</span></span>|<span data-ttu-id="c5d83-222">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="c5d83-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="c5d83-223">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c5d83-224">Feldname</span><span class="sxs-lookup"><span data-stu-id="c5d83-224">Field name</span></span>|<span data-ttu-id="c5d83-225">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c5d83-225">Data type</span></span>|<span data-ttu-id="c5d83-226">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5d83-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c5d83-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="c5d83-227">ThreadID</span></span>|<span data-ttu-id="c5d83-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-228">win:UInt64</span></span>|<span data-ttu-id="c5d83-229">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="c5d83-229">The thread identifier.</span></span>|  
|<span data-ttu-id="c5d83-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c5d83-230">AppDomainID</span></span>|<span data-ttu-id="c5d83-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-231">win:UInt64</span></span>|<span data-ttu-id="c5d83-232">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="c5d83-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="c5d83-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c5d83-233">ClrInstanceID</span></span>|<span data-ttu-id="c5d83-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c5d83-234">win:UInt16</span></span>|<span data-ttu-id="c5d83-235">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c5d83-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c5d83-236">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="c5d83-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="c5d83-237">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c5d83-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="c5d83-238">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c5d83-239">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c5d83-239">Keyword for raising the event</span></span>|<span data-ttu-id="c5d83-240">Ebene</span><span class="sxs-lookup"><span data-stu-id="c5d83-240">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c5d83-241">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c5d83-241">(0x800)</span></span>|<span data-ttu-id="c5d83-242">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-242">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="c5d83-243">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="c5d83-243">(0x10000)</span></span>|<span data-ttu-id="c5d83-244">Information (4)</span><span class="sxs-lookup"><span data-stu-id="c5d83-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="c5d83-245">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="c5d83-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c5d83-246">event</span><span class="sxs-lookup"><span data-stu-id="c5d83-246">Event</span></span>|<span data-ttu-id="c5d83-247">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c5d83-247">Event ID</span></span>|<span data-ttu-id="c5d83-248">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="c5d83-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="c5d83-249">86</span><span class="sxs-lookup"><span data-stu-id="c5d83-249">86</span></span>|<span data-ttu-id="c5d83-250">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="c5d83-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="c5d83-251">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="c5d83-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="c5d83-252">Feldname</span><span class="sxs-lookup"><span data-stu-id="c5d83-252">Field name</span></span>|<span data-ttu-id="c5d83-253">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c5d83-253">Data type</span></span>|<span data-ttu-id="c5d83-254">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5d83-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c5d83-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="c5d83-255">ThreadID</span></span>|<span data-ttu-id="c5d83-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-256">win:UInt64</span></span>|<span data-ttu-id="c5d83-257">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="c5d83-257">The thread identifier.</span></span>|  
|<span data-ttu-id="c5d83-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c5d83-258">AppDomainID</span></span>|<span data-ttu-id="c5d83-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c5d83-259">win:UInt64</span></span>|<span data-ttu-id="c5d83-260">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="c5d83-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="c5d83-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c5d83-261">ClrInstanceID</span></span>|<span data-ttu-id="c5d83-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c5d83-262">win:UInt16</span></span>|<span data-ttu-id="c5d83-263">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c5d83-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5d83-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5d83-264">See also</span></span>

- [<span data-ttu-id="c5d83-265">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c5d83-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
