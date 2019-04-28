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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788062"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="af8a3-102">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="af8a3-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="af8a3-103">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="af8a3-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="af8a3-104">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="af8a3-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="af8a3-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="af8a3-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="af8a3-106">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="af8a3-107">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="af8a3-108">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="af8a3-109">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="af8a3-110">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="af8a3-111">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="af8a3-112">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="af8a3-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="af8a3-113">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="af8a3-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="af8a3-114">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="af8a3-115">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="af8a3-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="af8a3-116">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="af8a3-116">Keyword for raising the event</span></span>|<span data-ttu-id="af8a3-117">Ebene</span><span class="sxs-lookup"><span data-stu-id="af8a3-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="af8a3-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="af8a3-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="af8a3-119">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-119">Informational(4)</span></span>|  
|<span data-ttu-id="af8a3-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="af8a3-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="af8a3-121">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="af8a3-122">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="af8a3-123">event</span><span class="sxs-lookup"><span data-stu-id="af8a3-123">Event</span></span>|<span data-ttu-id="af8a3-124">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="af8a3-124">Event ID</span></span>|<span data-ttu-id="af8a3-125">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="af8a3-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="af8a3-126">85</span><span class="sxs-lookup"><span data-stu-id="af8a3-126">85</span></span>|<span data-ttu-id="af8a3-127">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="af8a3-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="af8a3-128">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="af8a3-129">Feldname</span><span class="sxs-lookup"><span data-stu-id="af8a3-129">Field name</span></span>|<span data-ttu-id="af8a3-130">Datentyp</span><span class="sxs-lookup"><span data-stu-id="af8a3-130">Data type</span></span>|<span data-ttu-id="af8a3-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af8a3-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="af8a3-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="af8a3-132">ThreadID</span></span>|<span data-ttu-id="af8a3-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-133">win:UInt64</span></span>|<span data-ttu-id="af8a3-134">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="af8a3-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="af8a3-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="af8a3-135">AppDomainID</span></span>|<span data-ttu-id="af8a3-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-136">win:UInt64</span></span>|<span data-ttu-id="af8a3-137">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="af8a3-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="af8a3-138">Flags</span><span class="sxs-lookup"><span data-stu-id="af8a3-138">Flags</span></span>|<span data-ttu-id="af8a3-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af8a3-139">win:UInt32</span></span>|<span data-ttu-id="af8a3-140">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="af8a3-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="af8a3-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="af8a3-141">ManagedThreadIndex</span></span>|<span data-ttu-id="af8a3-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af8a3-142">win:UInt32</span></span>|<span data-ttu-id="af8a3-143">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="af8a3-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="af8a3-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="af8a3-144">OSThreadID</span></span>|<span data-ttu-id="af8a3-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="af8a3-145">win:UInt32</span></span>|<span data-ttu-id="af8a3-146">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="af8a3-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="af8a3-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af8a3-147">ClrInstanceID</span></span>|<span data-ttu-id="af8a3-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af8a3-148">win:UInt16</span></span>|<span data-ttu-id="af8a3-149">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="af8a3-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="af8a3-150">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="af8a3-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="af8a3-151">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="af8a3-152">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="af8a3-153">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="af8a3-153">Keyword for raising the event</span></span>|<span data-ttu-id="af8a3-154">Ebene</span><span class="sxs-lookup"><span data-stu-id="af8a3-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="af8a3-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="af8a3-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="af8a3-156">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="af8a3-157">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="af8a3-158">event</span><span class="sxs-lookup"><span data-stu-id="af8a3-158">Event</span></span>|<span data-ttu-id="af8a3-159">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="af8a3-159">Event ID</span></span>|<span data-ttu-id="af8a3-160">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="af8a3-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="af8a3-161">83</span><span class="sxs-lookup"><span data-stu-id="af8a3-161">83</span></span>|<span data-ttu-id="af8a3-162">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="af8a3-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="af8a3-163">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="af8a3-164">Feldname</span><span class="sxs-lookup"><span data-stu-id="af8a3-164">Field name</span></span>|<span data-ttu-id="af8a3-165">Datentyp</span><span class="sxs-lookup"><span data-stu-id="af8a3-165">Data type</span></span>|<span data-ttu-id="af8a3-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af8a3-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="af8a3-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="af8a3-167">AppDomainID</span></span>|<span data-ttu-id="af8a3-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-168">win:UInt64</span></span>|<span data-ttu-id="af8a3-169">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="af8a3-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="af8a3-170">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="af8a3-170">Allocated</span></span>|<span data-ttu-id="af8a3-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-171">win:UInt64</span></span>|<span data-ttu-id="af8a3-172">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="af8a3-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="af8a3-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af8a3-173">ClrInstanceID</span></span>|<span data-ttu-id="af8a3-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af8a3-174">win:UInt16</span></span>|<span data-ttu-id="af8a3-175">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="af8a3-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="af8a3-176">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="af8a3-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="af8a3-177">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="af8a3-178">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="af8a3-179">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="af8a3-179">Keyword for raising the event</span></span>|<span data-ttu-id="af8a3-180">Ebene</span><span class="sxs-lookup"><span data-stu-id="af8a3-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="af8a3-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="af8a3-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="af8a3-182">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="af8a3-183">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="af8a3-184">event</span><span class="sxs-lookup"><span data-stu-id="af8a3-184">Event</span></span>|<span data-ttu-id="af8a3-185">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="af8a3-185">Event ID</span></span>|<span data-ttu-id="af8a3-186">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="af8a3-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="af8a3-187">84</span><span class="sxs-lookup"><span data-stu-id="af8a3-187">84</span></span>|<span data-ttu-id="af8a3-188">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="af8a3-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="af8a3-189">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="af8a3-190">Feldname</span><span class="sxs-lookup"><span data-stu-id="af8a3-190">Field name</span></span>|<span data-ttu-id="af8a3-191">Datentyp</span><span class="sxs-lookup"><span data-stu-id="af8a3-191">Data type</span></span>|<span data-ttu-id="af8a3-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af8a3-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="af8a3-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="af8a3-193">AppDomainID</span></span>|<span data-ttu-id="af8a3-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-194">win:UInt64</span></span>|<span data-ttu-id="af8a3-195">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="af8a3-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="af8a3-196">Noch vorhanden</span><span class="sxs-lookup"><span data-stu-id="af8a3-196">Survived</span></span>|<span data-ttu-id="af8a3-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-197">win:UInt64</span></span>|<span data-ttu-id="af8a3-198">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="af8a3-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="af8a3-199">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="af8a3-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="af8a3-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="af8a3-200">ProcessSurvived</span></span>|<span data-ttu-id="af8a3-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-201">win:UInt64</span></span>|<span data-ttu-id="af8a3-202">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="af8a3-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="af8a3-203">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="af8a3-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="af8a3-204">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="af8a3-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="af8a3-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af8a3-205">ClrInstanceID</span></span>|<span data-ttu-id="af8a3-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af8a3-206">win:UInt16</span></span>|<span data-ttu-id="af8a3-207">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="af8a3-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="af8a3-208">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="af8a3-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="af8a3-209">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="af8a3-210">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="af8a3-211">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="af8a3-211">Keyword for raising the event</span></span>|<span data-ttu-id="af8a3-212">Ebene</span><span class="sxs-lookup"><span data-stu-id="af8a3-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="af8a3-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="af8a3-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="af8a3-214">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-214">Informational(4)</span></span>|  
|<span data-ttu-id="af8a3-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="af8a3-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="af8a3-216">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="af8a3-217">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="af8a3-218">event</span><span class="sxs-lookup"><span data-stu-id="af8a3-218">Event</span></span>|<span data-ttu-id="af8a3-219">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="af8a3-219">Event ID</span></span>|<span data-ttu-id="af8a3-220">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="af8a3-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="af8a3-221">87</span><span class="sxs-lookup"><span data-stu-id="af8a3-221">87</span></span>|<span data-ttu-id="af8a3-222">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="af8a3-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="af8a3-223">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="af8a3-224">Feldname</span><span class="sxs-lookup"><span data-stu-id="af8a3-224">Field name</span></span>|<span data-ttu-id="af8a3-225">Datentyp</span><span class="sxs-lookup"><span data-stu-id="af8a3-225">Data type</span></span>|<span data-ttu-id="af8a3-226">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af8a3-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="af8a3-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="af8a3-227">ThreadID</span></span>|<span data-ttu-id="af8a3-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-228">win:UInt64</span></span>|<span data-ttu-id="af8a3-229">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="af8a3-229">The thread identifier.</span></span>|  
|<span data-ttu-id="af8a3-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="af8a3-230">AppDomainID</span></span>|<span data-ttu-id="af8a3-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-231">win:UInt64</span></span>|<span data-ttu-id="af8a3-232">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="af8a3-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="af8a3-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af8a3-233">ClrInstanceID</span></span>|<span data-ttu-id="af8a3-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af8a3-234">win:UInt16</span></span>|<span data-ttu-id="af8a3-235">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="af8a3-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="af8a3-236">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="af8a3-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="af8a3-237">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="af8a3-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="af8a3-238">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="af8a3-239">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="af8a3-239">Keyword for raising the event</span></span>|<span data-ttu-id="af8a3-240">Ebene</span><span class="sxs-lookup"><span data-stu-id="af8a3-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="af8a3-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="af8a3-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="af8a3-242">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-242">Informational(4)</span></span>|  
|<span data-ttu-id="af8a3-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="af8a3-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="af8a3-244">Information (4)</span><span class="sxs-lookup"><span data-stu-id="af8a3-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="af8a3-245">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="af8a3-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="af8a3-246">event</span><span class="sxs-lookup"><span data-stu-id="af8a3-246">Event</span></span>|<span data-ttu-id="af8a3-247">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="af8a3-247">Event ID</span></span>|<span data-ttu-id="af8a3-248">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="af8a3-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="af8a3-249">86</span><span class="sxs-lookup"><span data-stu-id="af8a3-249">86</span></span>|<span data-ttu-id="af8a3-250">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="af8a3-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="af8a3-251">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="af8a3-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="af8a3-252">Feldname</span><span class="sxs-lookup"><span data-stu-id="af8a3-252">Field name</span></span>|<span data-ttu-id="af8a3-253">Datentyp</span><span class="sxs-lookup"><span data-stu-id="af8a3-253">Data type</span></span>|<span data-ttu-id="af8a3-254">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af8a3-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="af8a3-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="af8a3-255">ThreadID</span></span>|<span data-ttu-id="af8a3-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-256">win:UInt64</span></span>|<span data-ttu-id="af8a3-257">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="af8a3-257">The thread identifier.</span></span>|  
|<span data-ttu-id="af8a3-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="af8a3-258">AppDomainID</span></span>|<span data-ttu-id="af8a3-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="af8a3-259">win:UInt64</span></span>|<span data-ttu-id="af8a3-260">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="af8a3-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="af8a3-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="af8a3-261">ClrInstanceID</span></span>|<span data-ttu-id="af8a3-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="af8a3-262">win:UInt16</span></span>|<span data-ttu-id="af8a3-263">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="af8a3-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af8a3-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af8a3-264">See also</span></span>

- [<span data-ttu-id="af8a3-265">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="af8a3-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
