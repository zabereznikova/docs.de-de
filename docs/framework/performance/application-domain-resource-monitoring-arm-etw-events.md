---
title: ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)
description: Informieren Sie sich über die ETW-Ereignisse der Anwendungs Domänen Ressourcenüberwachung (Arm) in .net, wie z. b. ThreadCreated, appdomainmemreserviert, appdomainmemlag und mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309780"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="e8018-103">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="e8018-103">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="e8018-104">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="e8018-104">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="e8018-105">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e8018-105">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="e8018-106">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-106">ThreadCreated Event</span></span>

<span data-ttu-id="e8018-107">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="e8018-107">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="e8018-108">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e8018-108">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="e8018-109">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e8018-109">The following table shows the keyword and level.</span></span> <span data-ttu-id="e8018-110">Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e8018-110">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="e8018-111">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e8018-111">Keyword for raising the event</span></span>|<span data-ttu-id="e8018-112">Ebene</span><span class="sxs-lookup"><span data-stu-id="e8018-112">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e8018-113">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="e8018-113">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="e8018-114">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-114">Informational(4)</span></span>|
|<span data-ttu-id="e8018-115">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e8018-115">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e8018-116">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-116">Informational(4)</span></span>|

<span data-ttu-id="e8018-117">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="e8018-117">The following table shows the event information:</span></span>

|<span data-ttu-id="e8018-118">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-118">Event</span></span>|<span data-ttu-id="e8018-119">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e8018-119">Event ID</span></span>|<span data-ttu-id="e8018-120">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e8018-120">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="e8018-121">85</span><span class="sxs-lookup"><span data-stu-id="e8018-121">85</span></span>|<span data-ttu-id="e8018-122">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8018-122">A thread was created for the application domain.</span></span>|

<span data-ttu-id="e8018-123">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="e8018-123">The following table shows the event data:</span></span>

|<span data-ttu-id="e8018-124">Feldname</span><span class="sxs-lookup"><span data-stu-id="e8018-124">Field name</span></span>|<span data-ttu-id="e8018-125">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e8018-125">Data type</span></span>|<span data-ttu-id="e8018-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8018-126">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e8018-127">ThreadID</span><span class="sxs-lookup"><span data-stu-id="e8018-127">ThreadID</span></span>|<span data-ttu-id="e8018-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-128">win:UInt64</span></span>|<span data-ttu-id="e8018-129">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8018-129">ID of the thread that was created.</span></span>|
|<span data-ttu-id="e8018-130">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e8018-130">AppDomainID</span></span>|<span data-ttu-id="e8018-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-131">win:UInt64</span></span>|<span data-ttu-id="e8018-132">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="e8018-132">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="e8018-133">Flags</span><span class="sxs-lookup"><span data-stu-id="e8018-133">Flags</span></span>|<span data-ttu-id="e8018-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e8018-134">win:UInt32</span></span>|<span data-ttu-id="e8018-135">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="e8018-135">Thread creation flags.</span></span>|
|<span data-ttu-id="e8018-136">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="e8018-136">ManagedThreadIndex</span></span>|<span data-ttu-id="e8018-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e8018-137">win:UInt32</span></span>|<span data-ttu-id="e8018-138">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8018-138">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="e8018-139">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="e8018-139">OSThreadID</span></span>|<span data-ttu-id="e8018-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e8018-140">win:UInt32</span></span>|<span data-ttu-id="e8018-141">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8018-141">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="e8018-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e8018-142">ClrInstanceID</span></span>|<span data-ttu-id="e8018-143">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e8018-143">win:UInt16</span></span>|<span data-ttu-id="e8018-144">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e8018-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="e8018-145">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-145">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="e8018-146">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="e8018-146">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e8018-147">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e8018-147">Keyword for raising the event</span></span>|<span data-ttu-id="e8018-148">Ebene</span><span class="sxs-lookup"><span data-stu-id="e8018-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e8018-149">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="e8018-149">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="e8018-150">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-150">Informational(4)</span></span>|

<span data-ttu-id="e8018-151">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="e8018-151">The following table shows the event information:</span></span>

|<span data-ttu-id="e8018-152">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-152">Event</span></span>|<span data-ttu-id="e8018-153">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e8018-153">Event ID</span></span>|<span data-ttu-id="e8018-154">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e8018-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="e8018-155">83</span><span class="sxs-lookup"><span data-stu-id="e8018-155">83</span></span>|<span data-ttu-id="e8018-156">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e8018-156">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="e8018-157">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="e8018-157">The following table shows the event data:</span></span>

|<span data-ttu-id="e8018-158">Feldname</span><span class="sxs-lookup"><span data-stu-id="e8018-158">Field name</span></span>|<span data-ttu-id="e8018-159">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e8018-159">Data type</span></span>|<span data-ttu-id="e8018-160">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8018-160">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e8018-161">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e8018-161">AppDomainID</span></span>|<span data-ttu-id="e8018-162">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-162">win:UInt64</span></span>|<span data-ttu-id="e8018-163">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="e8018-163">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="e8018-164">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="e8018-164">Allocated</span></span>|<span data-ttu-id="e8018-165">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-165">win:UInt64</span></span>|<span data-ttu-id="e8018-166">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="e8018-166">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="e8018-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e8018-167">ClrInstanceID</span></span>|<span data-ttu-id="e8018-168">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e8018-168">win:UInt16</span></span>|<span data-ttu-id="e8018-169">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e8018-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="e8018-170">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-170">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="e8018-171">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="e8018-171">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e8018-172">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e8018-172">Keyword for raising the event</span></span>|<span data-ttu-id="e8018-173">Ebene</span><span class="sxs-lookup"><span data-stu-id="e8018-173">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e8018-174">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="e8018-174">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="e8018-175">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-175">Informational(4)</span></span>|

<span data-ttu-id="e8018-176">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="e8018-176">The following table shows the event information:</span></span>

|<span data-ttu-id="e8018-177">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-177">Event</span></span>|<span data-ttu-id="e8018-178">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e8018-178">Event ID</span></span>|<span data-ttu-id="e8018-179">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e8018-179">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="e8018-180">84</span><span class="sxs-lookup"><span data-stu-id="e8018-180">84</span></span>|<span data-ttu-id="e8018-181">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="e8018-181">Each garbage collection has ended.</span></span>|

<span data-ttu-id="e8018-182">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="e8018-182">The following table shows the event data:</span></span>

|<span data-ttu-id="e8018-183">Feldname</span><span class="sxs-lookup"><span data-stu-id="e8018-183">Field name</span></span>|<span data-ttu-id="e8018-184">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e8018-184">Data type</span></span>|<span data-ttu-id="e8018-185">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8018-185">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e8018-186">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e8018-186">AppDomainID</span></span>|<span data-ttu-id="e8018-187">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-187">win:UInt64</span></span>|<span data-ttu-id="e8018-188">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="e8018-188">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="e8018-189">Survived</span><span class="sxs-lookup"><span data-stu-id="e8018-189">Survived</span></span>|<span data-ttu-id="e8018-190">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-190">win:UInt64</span></span>|<span data-ttu-id="e8018-191">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e8018-191">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="e8018-192">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="e8018-192">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="e8018-193">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="e8018-193">ProcessSurvived</span></span>|<span data-ttu-id="e8018-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-194">win:UInt64</span></span>|<span data-ttu-id="e8018-195">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e8018-195">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="e8018-196">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e8018-196">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="e8018-197">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e8018-197">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="e8018-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e8018-198">ClrInstanceID</span></span>|<span data-ttu-id="e8018-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e8018-199">win:UInt16</span></span>|<span data-ttu-id="e8018-200">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e8018-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="e8018-201">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-201">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="e8018-202">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="e8018-202">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e8018-203">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e8018-203">Keyword for raising the event</span></span>|<span data-ttu-id="e8018-204">Ebene</span><span class="sxs-lookup"><span data-stu-id="e8018-204">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e8018-205">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="e8018-205">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="e8018-206">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-206">Informational(4)</span></span>|
|<span data-ttu-id="e8018-207">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e8018-207">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e8018-208">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-208">Informational(4)</span></span>|

<span data-ttu-id="e8018-209">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="e8018-209">The following table shows the event information:</span></span>

|<span data-ttu-id="e8018-210">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-210">Event</span></span>|<span data-ttu-id="e8018-211">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e8018-211">Event ID</span></span>|<span data-ttu-id="e8018-212">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e8018-212">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="e8018-213">87</span><span class="sxs-lookup"><span data-stu-id="e8018-213">87</span></span>|<span data-ttu-id="e8018-214">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="e8018-214">A thread enters an application domain.</span></span>|

<span data-ttu-id="e8018-215">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="e8018-215">The following table shows the event data:</span></span>

|<span data-ttu-id="e8018-216">Feldname</span><span class="sxs-lookup"><span data-stu-id="e8018-216">Field name</span></span>|<span data-ttu-id="e8018-217">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e8018-217">Data type</span></span>|<span data-ttu-id="e8018-218">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8018-218">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e8018-219">ThreadID</span><span class="sxs-lookup"><span data-stu-id="e8018-219">ThreadID</span></span>|<span data-ttu-id="e8018-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-220">win:UInt64</span></span>|<span data-ttu-id="e8018-221">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="e8018-221">The thread identifier.</span></span>|
|<span data-ttu-id="e8018-222">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e8018-222">AppDomainID</span></span>|<span data-ttu-id="e8018-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-223">win:UInt64</span></span>|<span data-ttu-id="e8018-224">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="e8018-224">The application domain identifier.</span></span>|
|<span data-ttu-id="e8018-225">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e8018-225">ClrInstanceID</span></span>|<span data-ttu-id="e8018-226">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e8018-226">win:UInt16</span></span>|<span data-ttu-id="e8018-227">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e8018-227">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="e8018-228">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-228">ThreadTerminated Event</span></span>

<span data-ttu-id="e8018-229">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="e8018-229">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="e8018-230">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e8018-230">Keyword for raising the event</span></span>|<span data-ttu-id="e8018-231">Ebene</span><span class="sxs-lookup"><span data-stu-id="e8018-231">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="e8018-232">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="e8018-232">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="e8018-233">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-233">Informational(4)</span></span>|
|<span data-ttu-id="e8018-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e8018-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e8018-235">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e8018-235">Informational(4)</span></span>|

<span data-ttu-id="e8018-236">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="e8018-236">The following table shows the event information:</span></span>

|<span data-ttu-id="e8018-237">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e8018-237">Event</span></span>|<span data-ttu-id="e8018-238">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e8018-238">Event ID</span></span>|<span data-ttu-id="e8018-239">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e8018-239">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="e8018-240">86</span><span class="sxs-lookup"><span data-stu-id="e8018-240">86</span></span>|<span data-ttu-id="e8018-241">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="e8018-241">A thread terminates.</span></span>|

<span data-ttu-id="e8018-242">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="e8018-242">The following table shows the event data:</span></span>

|<span data-ttu-id="e8018-243">Feldname</span><span class="sxs-lookup"><span data-stu-id="e8018-243">Field name</span></span>|<span data-ttu-id="e8018-244">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e8018-244">Data type</span></span>|<span data-ttu-id="e8018-245">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8018-245">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="e8018-246">ThreadID</span><span class="sxs-lookup"><span data-stu-id="e8018-246">ThreadID</span></span>|<span data-ttu-id="e8018-247">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-247">win:UInt64</span></span>|<span data-ttu-id="e8018-248">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="e8018-248">The thread identifier.</span></span>|
|<span data-ttu-id="e8018-249">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e8018-249">AppDomainID</span></span>|<span data-ttu-id="e8018-250">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e8018-250">win:UInt64</span></span>|<span data-ttu-id="e8018-251">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="e8018-251">The application domain identifier.</span></span>|
|<span data-ttu-id="e8018-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e8018-252">ClrInstanceID</span></span>|<span data-ttu-id="e8018-253">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e8018-253">win:UInt16</span></span>|<span data-ttu-id="e8018-254">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e8018-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e8018-255">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8018-255">See also</span></span>

- [<span data-ttu-id="e8018-256">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e8018-256">CLR ETW Events</span></span>](clr-etw-events.md)
