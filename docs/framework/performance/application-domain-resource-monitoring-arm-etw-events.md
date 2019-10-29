---
title: ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e1c2a38be6f2c15a118b35925570119b474f096
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040566"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="9bb9e-102">ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="9bb9e-103">Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="9bb9e-104">Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="9bb9e-105">ThreadCreated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9bb9e-105">ThreadCreated Event</span></span>

<span data-ttu-id="9bb9e-106">Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="9bb9e-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="9bb9e-107">Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="9bb9e-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="9bb9e-109">Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9bb9e-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="9bb9e-110">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9bb9e-110">Keyword for raising the event</span></span>|<span data-ttu-id="9bb9e-111">Ebene</span><span class="sxs-lookup"><span data-stu-id="9bb9e-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="9bb9e-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="9bb9e-113">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-113">Informational(4)</span></span>|
|<span data-ttu-id="9bb9e-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="9bb9e-115">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-115">Informational(4)</span></span>|

<span data-ttu-id="9bb9e-116">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-116">The following table shows the event information:</span></span>

|<span data-ttu-id="9bb9e-117">event</span><span class="sxs-lookup"><span data-stu-id="9bb9e-117">Event</span></span>|<span data-ttu-id="9bb9e-118">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-118">Event ID</span></span>|<span data-ttu-id="9bb9e-119">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="9bb9e-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="9bb9e-120">85</span><span class="sxs-lookup"><span data-stu-id="9bb9e-120">85</span></span>|<span data-ttu-id="9bb9e-121">Ein Thread wurde für die Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="9bb9e-122">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-122">The following table shows the event data:</span></span>

|<span data-ttu-id="9bb9e-123">Feldname</span><span class="sxs-lookup"><span data-stu-id="9bb9e-123">Field name</span></span>|<span data-ttu-id="9bb9e-124">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9bb9e-124">Data type</span></span>|<span data-ttu-id="9bb9e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bb9e-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="9bb9e-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-126">ThreadID</span></span>|<span data-ttu-id="9bb9e-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-127">win:UInt64</span></span>|<span data-ttu-id="9bb9e-128">Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="9bb9e-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-129">AppDomainID</span></span>|<span data-ttu-id="9bb9e-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-130">win:UInt64</span></span>|<span data-ttu-id="9bb9e-131">Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="9bb9e-132">Flags</span><span class="sxs-lookup"><span data-stu-id="9bb9e-132">Flags</span></span>|<span data-ttu-id="9bb9e-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9bb9e-133">win:UInt32</span></span>|<span data-ttu-id="9bb9e-134">Threaderstellungs-Flags.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-134">Thread creation flags.</span></span>|
|<span data-ttu-id="9bb9e-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="9bb9e-135">ManagedThreadIndex</span></span>|<span data-ttu-id="9bb9e-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9bb9e-136">win:UInt32</span></span>|<span data-ttu-id="9bb9e-137">Der verwaltete Index des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="9bb9e-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-138">OSThreadID</span></span>|<span data-ttu-id="9bb9e-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9bb9e-139">win:UInt32</span></span>|<span data-ttu-id="9bb9e-140">Die Betriebssystem-ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="9bb9e-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-141">ClrInstanceID</span></span>|<span data-ttu-id="9bb9e-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9bb9e-142">win:UInt16</span></span>|<span data-ttu-id="9bb9e-143">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="9bb9e-144">AppDomainMemAllocated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9bb9e-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="9bb9e-145">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="9bb9e-146">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9bb9e-146">Keyword for raising the event</span></span>|<span data-ttu-id="9bb9e-147">Ebene</span><span class="sxs-lookup"><span data-stu-id="9bb9e-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="9bb9e-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="9bb9e-149">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-149">Informational(4)</span></span>|

<span data-ttu-id="9bb9e-150">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-150">The following table shows the event information:</span></span>

|<span data-ttu-id="9bb9e-151">event</span><span class="sxs-lookup"><span data-stu-id="9bb9e-151">Event</span></span>|<span data-ttu-id="9bb9e-152">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-152">Event ID</span></span>|<span data-ttu-id="9bb9e-153">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="9bb9e-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="9bb9e-154">83</span><span class="sxs-lookup"><span data-stu-id="9bb9e-154">83</span></span>|<span data-ttu-id="9bb9e-155">Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="9bb9e-156">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-156">The following table shows the event data:</span></span>

|<span data-ttu-id="9bb9e-157">Feldname</span><span class="sxs-lookup"><span data-stu-id="9bb9e-157">Field name</span></span>|<span data-ttu-id="9bb9e-158">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9bb9e-158">Data type</span></span>|<span data-ttu-id="9bb9e-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bb9e-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="9bb9e-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-160">AppDomainID</span></span>|<span data-ttu-id="9bb9e-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-161">win:UInt64</span></span>|<span data-ttu-id="9bb9e-162">Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="9bb9e-163">Zugeordnet</span><span class="sxs-lookup"><span data-stu-id="9bb9e-163">Allocated</span></span>|<span data-ttu-id="9bb9e-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-164">win:UInt64</span></span>|<span data-ttu-id="9bb9e-165">Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).</span><span class="sxs-lookup"><span data-stu-id="9bb9e-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="9bb9e-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-166">ClrInstanceID</span></span>|<span data-ttu-id="9bb9e-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9bb9e-167">win:UInt16</span></span>|<span data-ttu-id="9bb9e-168">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="9bb9e-169">AppDomainMemSurvived-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9bb9e-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="9bb9e-170">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="9bb9e-171">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9bb9e-171">Keyword for raising the event</span></span>|<span data-ttu-id="9bb9e-172">Ebene</span><span class="sxs-lookup"><span data-stu-id="9bb9e-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="9bb9e-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="9bb9e-174">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-174">Informational(4)</span></span>|

<span data-ttu-id="9bb9e-175">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-175">The following table shows the event information:</span></span>

|<span data-ttu-id="9bb9e-176">event</span><span class="sxs-lookup"><span data-stu-id="9bb9e-176">Event</span></span>|<span data-ttu-id="9bb9e-177">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-177">Event ID</span></span>|<span data-ttu-id="9bb9e-178">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="9bb9e-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="9bb9e-179">84</span><span class="sxs-lookup"><span data-stu-id="9bb9e-179">84</span></span>|<span data-ttu-id="9bb9e-180">Jede Garbage Collection wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="9bb9e-181">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-181">The following table shows the event data:</span></span>

|<span data-ttu-id="9bb9e-182">Feldname</span><span class="sxs-lookup"><span data-stu-id="9bb9e-182">Field name</span></span>|<span data-ttu-id="9bb9e-183">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9bb9e-183">Data type</span></span>|<span data-ttu-id="9bb9e-184">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bb9e-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="9bb9e-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-185">AppDomainID</span></span>|<span data-ttu-id="9bb9e-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-186">win:UInt64</span></span>|<span data-ttu-id="9bb9e-187">Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="9bb9e-188">Noch vorhanden</span><span class="sxs-lookup"><span data-stu-id="9bb9e-188">Survived</span></span>|<span data-ttu-id="9bb9e-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-189">win:UInt64</span></span>|<span data-ttu-id="9bb9e-190">Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="9bb9e-191">Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="9bb9e-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="9bb9e-192">ProcessSurvived</span></span>|<span data-ttu-id="9bb9e-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-193">win:UInt64</span></span>|<span data-ttu-id="9bb9e-194">Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="9bb9e-195">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="9bb9e-196">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="9bb9e-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-197">ClrInstanceID</span></span>|<span data-ttu-id="9bb9e-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9bb9e-198">win:UInt16</span></span>|<span data-ttu-id="9bb9e-199">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="9bb9e-200">ThreadAppDomainEnter-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9bb9e-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="9bb9e-201">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="9bb9e-202">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9bb9e-202">Keyword for raising the event</span></span>|<span data-ttu-id="9bb9e-203">Ebene</span><span class="sxs-lookup"><span data-stu-id="9bb9e-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="9bb9e-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="9bb9e-205">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-205">Informational(4)</span></span>|
|<span data-ttu-id="9bb9e-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="9bb9e-207">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-207">Informational(4)</span></span>|

<span data-ttu-id="9bb9e-208">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-208">The following table shows the event information:</span></span>

|<span data-ttu-id="9bb9e-209">event</span><span class="sxs-lookup"><span data-stu-id="9bb9e-209">Event</span></span>|<span data-ttu-id="9bb9e-210">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-210">Event ID</span></span>|<span data-ttu-id="9bb9e-211">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="9bb9e-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="9bb9e-212">87</span><span class="sxs-lookup"><span data-stu-id="9bb9e-212">87</span></span>|<span data-ttu-id="9bb9e-213">Ein Thread wechselt in eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="9bb9e-214">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-214">The following table shows the event data:</span></span>

|<span data-ttu-id="9bb9e-215">Feldname</span><span class="sxs-lookup"><span data-stu-id="9bb9e-215">Field name</span></span>|<span data-ttu-id="9bb9e-216">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9bb9e-216">Data type</span></span>|<span data-ttu-id="9bb9e-217">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bb9e-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="9bb9e-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-218">ThreadID</span></span>|<span data-ttu-id="9bb9e-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-219">win:UInt64</span></span>|<span data-ttu-id="9bb9e-220">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-220">The thread identifier.</span></span>|
|<span data-ttu-id="9bb9e-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-221">AppDomainID</span></span>|<span data-ttu-id="9bb9e-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-222">win:UInt64</span></span>|<span data-ttu-id="9bb9e-223">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-223">The application domain identifier.</span></span>|
|<span data-ttu-id="9bb9e-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-224">ClrInstanceID</span></span>|<span data-ttu-id="9bb9e-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9bb9e-225">win:UInt16</span></span>|<span data-ttu-id="9bb9e-226">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="9bb9e-227">ThreadTerminated-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9bb9e-227">ThreadTerminated Event</span></span>

<span data-ttu-id="9bb9e-228">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="9bb9e-229">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9bb9e-229">Keyword for raising the event</span></span>|<span data-ttu-id="9bb9e-230">Ebene</span><span class="sxs-lookup"><span data-stu-id="9bb9e-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="9bb9e-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="9bb9e-232">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-232">Informational(4)</span></span>|
|<span data-ttu-id="9bb9e-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="9bb9e-234">Information (4)</span><span class="sxs-lookup"><span data-stu-id="9bb9e-234">Informational(4)</span></span>|

<span data-ttu-id="9bb9e-235">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-235">The following table shows the event information:</span></span>

|<span data-ttu-id="9bb9e-236">event</span><span class="sxs-lookup"><span data-stu-id="9bb9e-236">Event</span></span>|<span data-ttu-id="9bb9e-237">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-237">Event ID</span></span>|<span data-ttu-id="9bb9e-238">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="9bb9e-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="9bb9e-239">86</span><span class="sxs-lookup"><span data-stu-id="9bb9e-239">86</span></span>|<span data-ttu-id="9bb9e-240">Ein Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-240">A thread terminates.</span></span>|

<span data-ttu-id="9bb9e-241">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="9bb9e-241">The following table shows the event data:</span></span>

|<span data-ttu-id="9bb9e-242">Feldname</span><span class="sxs-lookup"><span data-stu-id="9bb9e-242">Field name</span></span>|<span data-ttu-id="9bb9e-243">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9bb9e-243">Data type</span></span>|<span data-ttu-id="9bb9e-244">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bb9e-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="9bb9e-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-245">ThreadID</span></span>|<span data-ttu-id="9bb9e-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-246">win:UInt64</span></span>|<span data-ttu-id="9bb9e-247">Der Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-247">The thread identifier.</span></span>|
|<span data-ttu-id="9bb9e-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-248">AppDomainID</span></span>|<span data-ttu-id="9bb9e-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9bb9e-249">win:UInt64</span></span>|<span data-ttu-id="9bb9e-250">Der Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-250">The application domain identifier.</span></span>|
|<span data-ttu-id="9bb9e-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9bb9e-251">ClrInstanceID</span></span>|<span data-ttu-id="9bb9e-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9bb9e-252">win:UInt16</span></span>|<span data-ttu-id="9bb9e-253">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9bb9e-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9bb9e-254">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bb9e-254">See also</span></span>

- [<span data-ttu-id="9bb9e-255">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9bb9e-255">CLR ETW Events</span></span>](clr-etw-events.md)
