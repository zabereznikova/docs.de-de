---
title: ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: 0e453b2bafffd9e07a1bdddd97282c5b97f5483d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716214"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="26dda-102">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="26dda-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="26dda-103">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="26dda-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="26dda-104">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="26dda-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="26dda-105">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="26dda-105">ThreadCreated Event</span></span>

<span data-ttu-id="26dda-106">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="26dda-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="26dda-107">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="26dda-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="26dda-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="26dda-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="26dda-109">Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="26dda-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="26dda-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="26dda-110">Keyword for raising the event</span></span>|<span data-ttu-id="26dda-111">Level</span><span class="sxs-lookup"><span data-stu-id="26dda-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="26dda-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="26dda-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="26dda-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-113">Informational(4)</span></span>|
|<span data-ttu-id="26dda-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="26dda-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="26dda-115">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-115">Informational(4)</span></span>|

<span data-ttu-id="26dda-116">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="26dda-116">The following table shows the event information:</span></span>

|<span data-ttu-id="26dda-117">Event</span><span class="sxs-lookup"><span data-stu-id="26dda-117">Event</span></span>|<span data-ttu-id="26dda-118">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="26dda-118">Event ID</span></span>|<span data-ttu-id="26dda-119">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="26dda-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="26dda-120">85</span><span class="sxs-lookup"><span data-stu-id="26dda-120">85</span></span>|<span data-ttu-id="26dda-121">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="26dda-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="26dda-122">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="26dda-122">The following table shows the event data:</span></span>

|<span data-ttu-id="26dda-123">Feldname</span><span class="sxs-lookup"><span data-stu-id="26dda-123">Field name</span></span>|<span data-ttu-id="26dda-124">Datentyp</span><span class="sxs-lookup"><span data-stu-id="26dda-124">Data type</span></span>|<span data-ttu-id="26dda-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26dda-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="26dda-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="26dda-126">ThreadID</span></span>|<span data-ttu-id="26dda-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-127">win:UInt64</span></span>|<span data-ttu-id="26dda-128">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="26dda-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="26dda-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="26dda-129">AppDomainID</span></span>|<span data-ttu-id="26dda-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-130">win:UInt64</span></span>|<span data-ttu-id="26dda-131">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="26dda-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="26dda-132">Flags</span><span class="sxs-lookup"><span data-stu-id="26dda-132">Flags</span></span>|<span data-ttu-id="26dda-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26dda-133">win:UInt32</span></span>|<span data-ttu-id="26dda-134">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="26dda-134">Thread creation flags.</span></span>|
|<span data-ttu-id="26dda-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="26dda-135">ManagedThreadIndex</span></span>|<span data-ttu-id="26dda-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26dda-136">win:UInt32</span></span>|<span data-ttu-id="26dda-137">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="26dda-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="26dda-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="26dda-138">OSThreadID</span></span>|<span data-ttu-id="26dda-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26dda-139">win:UInt32</span></span>|<span data-ttu-id="26dda-140">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="26dda-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="26dda-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26dda-141">ClrInstanceID</span></span>|<span data-ttu-id="26dda-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26dda-142">win:UInt16</span></span>|<span data-ttu-id="26dda-143">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26dda-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="26dda-144">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="26dda-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="26dda-145">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="26dda-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="26dda-146">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="26dda-146">Keyword for raising the event</span></span>|<span data-ttu-id="26dda-147">Level</span><span class="sxs-lookup"><span data-stu-id="26dda-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="26dda-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="26dda-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="26dda-149">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-149">Informational(4)</span></span>|

<span data-ttu-id="26dda-150">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="26dda-150">The following table shows the event information:</span></span>

|<span data-ttu-id="26dda-151">Event</span><span class="sxs-lookup"><span data-stu-id="26dda-151">Event</span></span>|<span data-ttu-id="26dda-152">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="26dda-152">Event ID</span></span>|<span data-ttu-id="26dda-153">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="26dda-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="26dda-154">83</span><span class="sxs-lookup"><span data-stu-id="26dda-154">83</span></span>|<span data-ttu-id="26dda-155">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="26dda-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="26dda-156">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="26dda-156">The following table shows the event data:</span></span>

|<span data-ttu-id="26dda-157">Feldname</span><span class="sxs-lookup"><span data-stu-id="26dda-157">Field name</span></span>|<span data-ttu-id="26dda-158">Datentyp</span><span class="sxs-lookup"><span data-stu-id="26dda-158">Data type</span></span>|<span data-ttu-id="26dda-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26dda-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="26dda-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="26dda-160">AppDomainID</span></span>|<span data-ttu-id="26dda-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-161">win:UInt64</span></span>|<span data-ttu-id="26dda-162">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="26dda-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="26dda-163">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="26dda-163">Allocated</span></span>|<span data-ttu-id="26dda-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-164">win:UInt64</span></span>|<span data-ttu-id="26dda-165">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="26dda-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="26dda-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26dda-166">ClrInstanceID</span></span>|<span data-ttu-id="26dda-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26dda-167">win:UInt16</span></span>|<span data-ttu-id="26dda-168">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26dda-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="26dda-169">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="26dda-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="26dda-170">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="26dda-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="26dda-171">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="26dda-171">Keyword for raising the event</span></span>|<span data-ttu-id="26dda-172">Level</span><span class="sxs-lookup"><span data-stu-id="26dda-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="26dda-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="26dda-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="26dda-174">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-174">Informational(4)</span></span>|

<span data-ttu-id="26dda-175">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="26dda-175">The following table shows the event information:</span></span>

|<span data-ttu-id="26dda-176">Event</span><span class="sxs-lookup"><span data-stu-id="26dda-176">Event</span></span>|<span data-ttu-id="26dda-177">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="26dda-177">Event ID</span></span>|<span data-ttu-id="26dda-178">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="26dda-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="26dda-179">84</span><span class="sxs-lookup"><span data-stu-id="26dda-179">84</span></span>|<span data-ttu-id="26dda-180">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="26dda-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="26dda-181">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="26dda-181">The following table shows the event data:</span></span>

|<span data-ttu-id="26dda-182">Feldname</span><span class="sxs-lookup"><span data-stu-id="26dda-182">Field name</span></span>|<span data-ttu-id="26dda-183">Datentyp</span><span class="sxs-lookup"><span data-stu-id="26dda-183">Data type</span></span>|<span data-ttu-id="26dda-184">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26dda-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="26dda-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="26dda-185">AppDomainID</span></span>|<span data-ttu-id="26dda-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-186">win:UInt64</span></span>|<span data-ttu-id="26dda-187">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="26dda-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="26dda-188">Noch vorhanden</span><span class="sxs-lookup"><span data-stu-id="26dda-188">Survived</span></span>|<span data-ttu-id="26dda-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-189">win:UInt64</span></span>|<span data-ttu-id="26dda-190">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="26dda-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="26dda-191">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="26dda-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="26dda-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="26dda-192">ProcessSurvived</span></span>|<span data-ttu-id="26dda-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-193">win:UInt64</span></span>|<span data-ttu-id="26dda-194">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="26dda-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="26dda-195">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="26dda-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="26dda-196">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="26dda-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="26dda-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26dda-197">ClrInstanceID</span></span>|<span data-ttu-id="26dda-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26dda-198">win:UInt16</span></span>|<span data-ttu-id="26dda-199">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26dda-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="26dda-200">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="26dda-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="26dda-201">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="26dda-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="26dda-202">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="26dda-202">Keyword for raising the event</span></span>|<span data-ttu-id="26dda-203">Level</span><span class="sxs-lookup"><span data-stu-id="26dda-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="26dda-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="26dda-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="26dda-205">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-205">Informational(4)</span></span>|
|<span data-ttu-id="26dda-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="26dda-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="26dda-207">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-207">Informational(4)</span></span>|

<span data-ttu-id="26dda-208">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="26dda-208">The following table shows the event information:</span></span>

|<span data-ttu-id="26dda-209">Event</span><span class="sxs-lookup"><span data-stu-id="26dda-209">Event</span></span>|<span data-ttu-id="26dda-210">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="26dda-210">Event ID</span></span>|<span data-ttu-id="26dda-211">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="26dda-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="26dda-212">87</span><span class="sxs-lookup"><span data-stu-id="26dda-212">87</span></span>|<span data-ttu-id="26dda-213">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="26dda-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="26dda-214">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="26dda-214">The following table shows the event data:</span></span>

|<span data-ttu-id="26dda-215">Feldname</span><span class="sxs-lookup"><span data-stu-id="26dda-215">Field name</span></span>|<span data-ttu-id="26dda-216">Datentyp</span><span class="sxs-lookup"><span data-stu-id="26dda-216">Data type</span></span>|<span data-ttu-id="26dda-217">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26dda-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="26dda-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="26dda-218">ThreadID</span></span>|<span data-ttu-id="26dda-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-219">win:UInt64</span></span>|<span data-ttu-id="26dda-220">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="26dda-220">The thread identifier.</span></span>|
|<span data-ttu-id="26dda-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="26dda-221">AppDomainID</span></span>|<span data-ttu-id="26dda-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-222">win:UInt64</span></span>|<span data-ttu-id="26dda-223">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="26dda-223">The application domain identifier.</span></span>|
|<span data-ttu-id="26dda-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26dda-224">ClrInstanceID</span></span>|<span data-ttu-id="26dda-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26dda-225">win:UInt16</span></span>|<span data-ttu-id="26dda-226">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26dda-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="26dda-227">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="26dda-227">ThreadTerminated Event</span></span>

<span data-ttu-id="26dda-228">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="26dda-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="26dda-229">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="26dda-229">Keyword for raising the event</span></span>|<span data-ttu-id="26dda-230">Level</span><span class="sxs-lookup"><span data-stu-id="26dda-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="26dda-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="26dda-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="26dda-232">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-232">Informational(4)</span></span>|
|<span data-ttu-id="26dda-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="26dda-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="26dda-234">Information (4)</span><span class="sxs-lookup"><span data-stu-id="26dda-234">Informational(4)</span></span>|

<span data-ttu-id="26dda-235">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="26dda-235">The following table shows the event information:</span></span>

|<span data-ttu-id="26dda-236">Event</span><span class="sxs-lookup"><span data-stu-id="26dda-236">Event</span></span>|<span data-ttu-id="26dda-237">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="26dda-237">Event ID</span></span>|<span data-ttu-id="26dda-238">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="26dda-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="26dda-239">86</span><span class="sxs-lookup"><span data-stu-id="26dda-239">86</span></span>|<span data-ttu-id="26dda-240">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="26dda-240">A thread terminates.</span></span>|

<span data-ttu-id="26dda-241">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="26dda-241">The following table shows the event data:</span></span>

|<span data-ttu-id="26dda-242">Feldname</span><span class="sxs-lookup"><span data-stu-id="26dda-242">Field name</span></span>|<span data-ttu-id="26dda-243">Datentyp</span><span class="sxs-lookup"><span data-stu-id="26dda-243">Data type</span></span>|<span data-ttu-id="26dda-244">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26dda-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="26dda-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="26dda-245">ThreadID</span></span>|<span data-ttu-id="26dda-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-246">win:UInt64</span></span>|<span data-ttu-id="26dda-247">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="26dda-247">The thread identifier.</span></span>|
|<span data-ttu-id="26dda-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="26dda-248">AppDomainID</span></span>|<span data-ttu-id="26dda-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26dda-249">win:UInt64</span></span>|<span data-ttu-id="26dda-250">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="26dda-250">The application domain identifier.</span></span>|
|<span data-ttu-id="26dda-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26dda-251">ClrInstanceID</span></span>|<span data-ttu-id="26dda-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26dda-252">win:UInt16</span></span>|<span data-ttu-id="26dda-253">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26dda-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="26dda-254">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26dda-254">See also</span></span>

- [<span data-ttu-id="26dda-255">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="26dda-255">CLR ETW Events</span></span>](clr-etw-events.md)
