---
title: ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e4002ae248022a9e4380c79174109494b5e4ca
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046766"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="a3572-102">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="a3572-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a3572-103">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a3572-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="a3572-104">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3572-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="a3572-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="a3572-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="a3572-106">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="a3572-107">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="a3572-108">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="a3572-109">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="a3572-110">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="a3572-111">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="a3572-112">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="a3572-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="a3572-113">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a3572-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="a3572-114">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a3572-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="a3572-115">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="a3572-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a3572-116">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a3572-116">Keyword for raising the event</span></span>|<span data-ttu-id="a3572-117">Ebene</span><span class="sxs-lookup"><span data-stu-id="a3572-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3572-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a3572-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a3572-119">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-119">Informational(4)</span></span>|  
|<span data-ttu-id="a3572-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a3572-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a3572-121">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="a3572-122">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a3572-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3572-123">event</span><span class="sxs-lookup"><span data-stu-id="a3572-123">Event</span></span>|<span data-ttu-id="a3572-124">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a3572-124">Event ID</span></span>|<span data-ttu-id="a3572-125">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a3572-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="a3572-126">85</span><span class="sxs-lookup"><span data-stu-id="a3572-126">85</span></span>|<span data-ttu-id="a3572-127">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3572-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="a3572-128">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a3572-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3572-129">Feldname</span><span class="sxs-lookup"><span data-stu-id="a3572-129">Field name</span></span>|<span data-ttu-id="a3572-130">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a3572-130">Data type</span></span>|<span data-ttu-id="a3572-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3572-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3572-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a3572-132">ThreadID</span></span>|<span data-ttu-id="a3572-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-133">win:UInt64</span></span>|<span data-ttu-id="a3572-134">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3572-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a3572-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a3572-135">AppDomainID</span></span>|<span data-ttu-id="a3572-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-136">win:UInt64</span></span>|<span data-ttu-id="a3572-137">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="a3572-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="a3572-138">Flags</span><span class="sxs-lookup"><span data-stu-id="a3572-138">Flags</span></span>|<span data-ttu-id="a3572-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3572-139">win:UInt32</span></span>|<span data-ttu-id="a3572-140">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="a3572-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="a3572-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="a3572-141">ManagedThreadIndex</span></span>|<span data-ttu-id="a3572-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3572-142">win:UInt32</span></span>|<span data-ttu-id="a3572-143">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3572-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="a3572-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="a3572-144">OSThreadID</span></span>|<span data-ttu-id="a3572-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3572-145">win:UInt32</span></span>|<span data-ttu-id="a3572-146">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3572-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a3572-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3572-147">ClrInstanceID</span></span>|<span data-ttu-id="a3572-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3572-148">win:UInt16</span></span>|<span data-ttu-id="a3572-149">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a3572-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3572-150">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a3572-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="a3572-151">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="a3572-152">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a3572-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3572-153">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a3572-153">Keyword for raising the event</span></span>|<span data-ttu-id="a3572-154">Ebene</span><span class="sxs-lookup"><span data-stu-id="a3572-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3572-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a3572-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a3572-156">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="a3572-157">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a3572-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3572-158">event</span><span class="sxs-lookup"><span data-stu-id="a3572-158">Event</span></span>|<span data-ttu-id="a3572-159">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a3572-159">Event ID</span></span>|<span data-ttu-id="a3572-160">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a3572-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="a3572-161">83</span><span class="sxs-lookup"><span data-stu-id="a3572-161">83</span></span>|<span data-ttu-id="a3572-162">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a3572-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="a3572-163">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a3572-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3572-164">Feldname</span><span class="sxs-lookup"><span data-stu-id="a3572-164">Field name</span></span>|<span data-ttu-id="a3572-165">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a3572-165">Data type</span></span>|<span data-ttu-id="a3572-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3572-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3572-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a3572-167">AppDomainID</span></span>|<span data-ttu-id="a3572-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-168">win:UInt64</span></span>|<span data-ttu-id="a3572-169">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="a3572-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a3572-170">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="a3572-170">Allocated</span></span>|<span data-ttu-id="a3572-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-171">win:UInt64</span></span>|<span data-ttu-id="a3572-172">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="a3572-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="a3572-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3572-173">ClrInstanceID</span></span>|<span data-ttu-id="a3572-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3572-174">win:UInt16</span></span>|<span data-ttu-id="a3572-175">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a3572-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3572-176">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a3572-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="a3572-177">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="a3572-178">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a3572-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3572-179">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a3572-179">Keyword for raising the event</span></span>|<span data-ttu-id="a3572-180">Ebene</span><span class="sxs-lookup"><span data-stu-id="a3572-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3572-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a3572-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a3572-182">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="a3572-183">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a3572-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3572-184">event</span><span class="sxs-lookup"><span data-stu-id="a3572-184">Event</span></span>|<span data-ttu-id="a3572-185">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a3572-185">Event ID</span></span>|<span data-ttu-id="a3572-186">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a3572-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="a3572-187">84</span><span class="sxs-lookup"><span data-stu-id="a3572-187">84</span></span>|<span data-ttu-id="a3572-188">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="a3572-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="a3572-189">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a3572-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3572-190">Feldname</span><span class="sxs-lookup"><span data-stu-id="a3572-190">Field name</span></span>|<span data-ttu-id="a3572-191">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a3572-191">Data type</span></span>|<span data-ttu-id="a3572-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3572-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3572-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a3572-193">AppDomainID</span></span>|<span data-ttu-id="a3572-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-194">win:UInt64</span></span>|<span data-ttu-id="a3572-195">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="a3572-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a3572-196">Noch vorhanden</span><span class="sxs-lookup"><span data-stu-id="a3572-196">Survived</span></span>|<span data-ttu-id="a3572-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-197">win:UInt64</span></span>|<span data-ttu-id="a3572-198">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a3572-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="a3572-199">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="a3572-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="a3572-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="a3572-200">ProcessSurvived</span></span>|<span data-ttu-id="a3572-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-201">win:UInt64</span></span>|<span data-ttu-id="a3572-202">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a3572-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="a3572-203">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a3572-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="a3572-204">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a3572-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="a3572-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3572-205">ClrInstanceID</span></span>|<span data-ttu-id="a3572-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3572-206">win:UInt16</span></span>|<span data-ttu-id="a3572-207">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a3572-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3572-208">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a3572-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="a3572-209">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="a3572-210">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a3572-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3572-211">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a3572-211">Keyword for raising the event</span></span>|<span data-ttu-id="a3572-212">Ebene</span><span class="sxs-lookup"><span data-stu-id="a3572-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3572-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a3572-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a3572-214">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-214">Informational(4)</span></span>|  
|<span data-ttu-id="a3572-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a3572-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a3572-216">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="a3572-217">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a3572-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3572-218">event</span><span class="sxs-lookup"><span data-stu-id="a3572-218">Event</span></span>|<span data-ttu-id="a3572-219">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a3572-219">Event ID</span></span>|<span data-ttu-id="a3572-220">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a3572-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="a3572-221">87</span><span class="sxs-lookup"><span data-stu-id="a3572-221">87</span></span>|<span data-ttu-id="a3572-222">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a3572-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="a3572-223">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a3572-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3572-224">Feldname</span><span class="sxs-lookup"><span data-stu-id="a3572-224">Field name</span></span>|<span data-ttu-id="a3572-225">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a3572-225">Data type</span></span>|<span data-ttu-id="a3572-226">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3572-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3572-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a3572-227">ThreadID</span></span>|<span data-ttu-id="a3572-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-228">win:UInt64</span></span>|<span data-ttu-id="a3572-229">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="a3572-229">The thread identifier.</span></span>|  
|<span data-ttu-id="a3572-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a3572-230">AppDomainID</span></span>|<span data-ttu-id="a3572-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-231">win:UInt64</span></span>|<span data-ttu-id="a3572-232">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a3572-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="a3572-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3572-233">ClrInstanceID</span></span>|<span data-ttu-id="a3572-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3572-234">win:UInt16</span></span>|<span data-ttu-id="a3572-235">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a3572-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3572-236">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a3572-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="a3572-237">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a3572-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="a3572-238">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a3572-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3572-239">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a3572-239">Keyword for raising the event</span></span>|<span data-ttu-id="a3572-240">Ebene</span><span class="sxs-lookup"><span data-stu-id="a3572-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3572-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a3572-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a3572-242">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-242">Informational(4)</span></span>|  
|<span data-ttu-id="a3572-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a3572-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a3572-244">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a3572-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="a3572-245">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a3572-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3572-246">event</span><span class="sxs-lookup"><span data-stu-id="a3572-246">Event</span></span>|<span data-ttu-id="a3572-247">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a3572-247">Event ID</span></span>|<span data-ttu-id="a3572-248">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a3572-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="a3572-249">86</span><span class="sxs-lookup"><span data-stu-id="a3572-249">86</span></span>|<span data-ttu-id="a3572-250">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="a3572-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="a3572-251">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="a3572-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="a3572-252">Feldname</span><span class="sxs-lookup"><span data-stu-id="a3572-252">Field name</span></span>|<span data-ttu-id="a3572-253">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a3572-253">Data type</span></span>|<span data-ttu-id="a3572-254">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3572-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3572-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a3572-255">ThreadID</span></span>|<span data-ttu-id="a3572-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-256">win:UInt64</span></span>|<span data-ttu-id="a3572-257">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="a3572-257">The thread identifier.</span></span>|  
|<span data-ttu-id="a3572-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a3572-258">AppDomainID</span></span>|<span data-ttu-id="a3572-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3572-259">win:UInt64</span></span>|<span data-ttu-id="a3572-260">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a3572-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="a3572-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3572-261">ClrInstanceID</span></span>|<span data-ttu-id="a3572-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3572-262">win:UInt16</span></span>|<span data-ttu-id="a3572-263">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a3572-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3572-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3572-264">See also</span></span>

- [<span data-ttu-id="a3572-265">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a3572-265">CLR ETW Events</span></span>](clr-etw-events.md)
