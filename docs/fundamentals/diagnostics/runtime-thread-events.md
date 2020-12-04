---
title: Thread Pool-Lauf Zeit Ereignisse
description: Weitere Informationen finden Sie unter .NET-Runtime-Thread Pool Ereignisse, die Diagnoseinformationen zum Thread Pool in .net Core sammeln. Thread Pool Ereignisse sind Arbeits Thread Pool-Ereignisse oder e/a-Thread Pool Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96592107"
---
# <a name="net-runtime-thread-pool-events"></a><span data-ttu-id="48a3b-104">.NET-Runtime-Thread Pool Ereignisse</span><span class="sxs-lookup"><span data-stu-id="48a3b-104">.NET runtime thread pool events</span></span>

<span data-ttu-id="48a3b-105">Diese Ereignisse sammeln Informationen über Worker-und e/a-Threads im Thread Pool.</span><span class="sxs-lookup"><span data-stu-id="48a3b-105">These events collect information about worker and I/O threads in the threadpool.</span></span> <span data-ttu-id="48a3b-106">Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="48a3b-106">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="iothreadcreate_v1-event"></a><span data-ttu-id="48a3b-107">IOThreadCreate_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-107">IOThreadCreate_V1 event</span></span>

 <span data-ttu-id="48a3b-108">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-108">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-109">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-109">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-110">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-110">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-111">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-111">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-112">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-112">Informational (4)</span></span>|

 <span data-ttu-id="48a3b-113">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-113">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-114">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-114">Event</span></span>|<span data-ttu-id="48a3b-115">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-115">Event ID</span></span>|<span data-ttu-id="48a3b-116">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="48a3b-116">Raised when</span></span>|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|<span data-ttu-id="48a3b-117">44</span><span class="sxs-lookup"><span data-stu-id="48a3b-117">44</span></span>|<span data-ttu-id="48a3b-118">Ein E/A-Thread wird im Threadpool erstellt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-118">An I/O thread is created in the thread pool.</span></span>|

 <span data-ttu-id="48a3b-119">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-119">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-120">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-120">Field name</span></span>|<span data-ttu-id="48a3b-121">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-121">Data type</span></span>|<span data-ttu-id="48a3b-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-122">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="48a3b-123">Anzahl der E/A-Threads, einschließlich des neu erstellten Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-123">Number of I/O threads, including the newly created thread.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="48a3b-124">Anzahl deaktivierter Arbeitsthreads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-124">Number of retired worker threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-125">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-125">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadterminate_v1-event"></a><span data-ttu-id="48a3b-126">IOThreadTerminate_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-126">IOThreadTerminate_V1 event</span></span>

 <span data-ttu-id="48a3b-127">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene.</span><span class="sxs-lookup"><span data-stu-id="48a3b-127">The following table shows the keyword and level</span></span>

|<span data-ttu-id="48a3b-128">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-128">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-129">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-129">Level</span></span>
|-----------------------------------|-----------
|<span data-ttu-id="48a3b-130">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-130">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-131">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-131">Informational (4)</span></span>

 <span data-ttu-id="48a3b-132">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-132">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-133">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-133">Event</span></span>|<span data-ttu-id="48a3b-134">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-134">Event ID</span></span>|<span data-ttu-id="48a3b-135">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="48a3b-135">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|<span data-ttu-id="48a3b-136">45</span><span class="sxs-lookup"><span data-stu-id="48a3b-136">45</span></span>|<span data-ttu-id="48a3b-137">Ein e/a-Thread wird im Thread Pool beendet.</span><span class="sxs-lookup"><span data-stu-id="48a3b-137">An I/O thread is terminated in the thread pool.</span></span>|

 <span data-ttu-id="48a3b-138">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-138">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-139">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-139">Field name</span></span>|<span data-ttu-id="48a3b-140">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-140">Data type</span></span>|<span data-ttu-id="48a3b-141">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-141">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="48a3b-142">Anzahl der im Threadpool verbleibenden E/A-Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-142">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="48a3b-143">Anzahl deaktivierter E/A-Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-143">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-144">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadretire_v1-event"></a><span data-ttu-id="48a3b-145">IOThreadRetire_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-145">IOThreadRetire_V1 event</span></span>

 <span data-ttu-id="48a3b-146">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-146">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-147">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-147">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-148">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-149">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-149">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-150">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-150">Informational (4)</span></span>|

 <span data-ttu-id="48a3b-151">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-151">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-152">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-152">Event</span></span>|<span data-ttu-id="48a3b-153">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-153">Event ID</span></span>|<span data-ttu-id="48a3b-154">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="48a3b-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadRetire_V1`|<span data-ttu-id="48a3b-155">46</span><span class="sxs-lookup"><span data-stu-id="48a3b-155">46</span></span>|<span data-ttu-id="48a3b-156">Ein E/A-Thread wird zum Kandidaten für die Deaktivierung.</span><span class="sxs-lookup"><span data-stu-id="48a3b-156">An I/O thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="48a3b-157">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-157">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-158">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-158">Field name</span></span>|<span data-ttu-id="48a3b-159">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-159">Data type</span></span>|<span data-ttu-id="48a3b-160">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-160">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="48a3b-161">Anzahl der im Threadpool verbleibenden E/A-Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-161">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="48a3b-162">Anzahl deaktivierter E/A-Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-162">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-163">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadunretire_v1-event"></a><span data-ttu-id="48a3b-164">IOThreadUnretire_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-164">IOThreadUnretire_V1 event</span></span>

 <span data-ttu-id="48a3b-165">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-165">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-166">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-166">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-167">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-168">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-168">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-169">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-169">Informational (4)</span></span>|

 <span data-ttu-id="48a3b-170">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-170">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-171">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-171">Event</span></span>|<span data-ttu-id="48a3b-172">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-172">Event ID</span></span>|<span data-ttu-id="48a3b-173">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="48a3b-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadUnretire_V1`|<span data-ttu-id="48a3b-174">47</span><span class="sxs-lookup"><span data-stu-id="48a3b-174">47</span></span>|<span data-ttu-id="48a3b-175">Ein E/A-Threads wird aufgrund von E/A-Vorgängen erneut aktiviert, die während einer Wartefrist auftreten, nachdem der Thread zum Kandidaten für die Deaktivierung geworden ist.</span><span class="sxs-lookup"><span data-stu-id="48a3b-175">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="48a3b-176">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-176">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-177">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-177">Field name</span></span>|<span data-ttu-id="48a3b-178">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-178">Data type</span></span>|<span data-ttu-id="48a3b-179">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-179">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="48a3b-180">Anzahl der E/A-Threads im Threadpool, einschließlich dieses Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-180">Number of I/O threads in the thread pool, including this one.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="48a3b-181">Anzahl deaktivierter E/A-Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-181">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`Win:UInt16`|<span data-ttu-id="48a3b-182">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-182">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstart-event"></a><span data-ttu-id="48a3b-183">Threadpoolworkerthreadstart-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-183">ThreadPoolWorkerThreadStart event</span></span>

|<span data-ttu-id="48a3b-184">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-184">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-185">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-185">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="48a3b-186">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-186">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-187">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-187">Informational (4)</span></span>|

|<span data-ttu-id="48a3b-188">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-188">Event</span></span>|<span data-ttu-id="48a3b-189">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-189">Event ID</span></span>|<span data-ttu-id="48a3b-190">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-190">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="48a3b-191">50</span><span class="sxs-lookup"><span data-stu-id="48a3b-191">50</span></span>|<span data-ttu-id="48a3b-192">Ein Arbeitsthread wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-192">A worker thread is created.</span></span>|

|<span data-ttu-id="48a3b-193">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-193">Field name</span></span>|<span data-ttu-id="48a3b-194">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-194">Data type</span></span>|<span data-ttu-id="48a3b-195">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-195">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-196">Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="48a3b-196">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-197">Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="48a3b-197">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-198">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-198">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstop-event"></a><span data-ttu-id="48a3b-199">Threadpoolworkerthreadstoppt-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-199">ThreadPoolWorkerThreadStop event</span></span>

|<span data-ttu-id="48a3b-200">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-200">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-201">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-201">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="48a3b-202">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-202">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-203">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-203">Informational (4)</span></span>|

|<span data-ttu-id="48a3b-204">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-204">Event</span></span>|<span data-ttu-id="48a3b-205">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-205">Event ID</span></span>|<span data-ttu-id="48a3b-206">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-206">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="48a3b-207">51</span><span class="sxs-lookup"><span data-stu-id="48a3b-207">51</span></span>|<span data-ttu-id="48a3b-208">Ein Arbeitsthread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="48a3b-208">A worker thread is stopped.</span></span>|

|<span data-ttu-id="48a3b-209">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-209">Field name</span></span>|<span data-ttu-id="48a3b-210">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-210">Data type</span></span>|<span data-ttu-id="48a3b-211">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-211">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-212">Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="48a3b-212">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-213">Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="48a3b-213">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-214">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-214">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadwait-event"></a><span data-ttu-id="48a3b-215">Threadpoolworkerthreadwait-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-215">ThreadPoolWorkerThreadWait event</span></span>

|<span data-ttu-id="48a3b-216">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-216">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-217">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-217">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="48a3b-218">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-218">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-219">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-219">Informational (4)</span></span>|

|<span data-ttu-id="48a3b-220">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-220">Event</span></span>|<span data-ttu-id="48a3b-221">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-221">Event ID</span></span>|<span data-ttu-id="48a3b-222">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-222">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|<span data-ttu-id="48a3b-223">57</span><span class="sxs-lookup"><span data-stu-id="48a3b-223">57</span></span>|<span data-ttu-id="48a3b-224">Ein Arbeits Thread wartet auf die Arbeit.</span><span class="sxs-lookup"><span data-stu-id="48a3b-224">A worker thread starts waiting for work.</span></span>|

|<span data-ttu-id="48a3b-225">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-225">Field name</span></span>|<span data-ttu-id="48a3b-226">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-226">Data type</span></span>|<span data-ttu-id="48a3b-227">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-227">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-228">Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="48a3b-228">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-229">Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="48a3b-229">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-230">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-230">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstart-event"></a><span data-ttu-id="48a3b-231">Threadpoolworkerthreadretirementstart-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-231">ThreadPoolWorkerThreadRetirementStart event</span></span>

|<span data-ttu-id="48a3b-232">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-232">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-233">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-233">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="48a3b-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-235">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-235">Informational (4)</span></span>|

|<span data-ttu-id="48a3b-236">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-236">Event</span></span>|<span data-ttu-id="48a3b-237">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-237">Event ID</span></span>|<span data-ttu-id="48a3b-238">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-238">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="48a3b-239">52</span><span class="sxs-lookup"><span data-stu-id="48a3b-239">52</span></span>|<span data-ttu-id="48a3b-240">Ein Arbeitsthread wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-240">A worker thread retires.</span></span>|

|<span data-ttu-id="48a3b-241">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-241">Field name</span></span>|<span data-ttu-id="48a3b-242">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-242">Data type</span></span>|<span data-ttu-id="48a3b-243">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-243">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-244">Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="48a3b-244">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-245">Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="48a3b-245">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-246">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstop-event"></a><span data-ttu-id="48a3b-247">Threadpoolworkerthreadretirementend-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-247">ThreadPoolWorkerThreadRetirementStop event</span></span>

|<span data-ttu-id="48a3b-248">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-248">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-249">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-249">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="48a3b-250">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-250">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-251">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-251">Informational (4)</span></span>|

|<span data-ttu-id="48a3b-252">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-252">Event</span></span>|<span data-ttu-id="48a3b-253">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-253">Event ID</span></span>|<span data-ttu-id="48a3b-254">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-254">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="48a3b-255">53</span><span class="sxs-lookup"><span data-stu-id="48a3b-255">53</span></span>|<span data-ttu-id="48a3b-256">Ein deaktivierter Arbeitsthread wird wieder aktiviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-256">A retired worker thread becomes active again.</span></span>|

|<span data-ttu-id="48a3b-257">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-257">Field name</span></span>|<span data-ttu-id="48a3b-258">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-258">Data type</span></span>|<span data-ttu-id="48a3b-259">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-259">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-260">Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="48a3b-260">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-261">Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="48a3b-261">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-262">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-262">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a><span data-ttu-id="48a3b-263">Threadpoolworkerthreadaccessmentsample-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-263">ThreadPoolWorkerThreadAdjustmentSample event</span></span>

 <span data-ttu-id="48a3b-264">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-264">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-265">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-265">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-266">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-266">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-267">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-267">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-268">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-268">Informational (4)</span></span>|

 <span data-ttu-id="48a3b-269">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-269">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-270">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-270">Event</span></span>|<span data-ttu-id="48a3b-271">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-271">Event ID</span></span>|<span data-ttu-id="48a3b-272">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-272">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="48a3b-273">54</span><span class="sxs-lookup"><span data-stu-id="48a3b-273">54</span></span>|<span data-ttu-id="48a3b-274">Bezieht sich auf die Auflistung von Informationen für ein Beispiel, d. h. eine Messung des Durchsatzes mit einer bestimmten Parallelitätsebene zu einem bestimmten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-274">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|

 <span data-ttu-id="48a3b-275">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-275">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-276">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-276">Field name</span></span>|<span data-ttu-id="48a3b-277">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-277">Data type</span></span>|<span data-ttu-id="48a3b-278">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-278">Description</span></span>|
|----------------|---------------|-----------------|
|`Throughput`|`win:Double`|<span data-ttu-id="48a3b-279">Anzahl von Abschlüssen pro Zeiteinheit.</span><span class="sxs-lookup"><span data-stu-id="48a3b-279">Number of completions per unit of time.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-280">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a><span data-ttu-id="48a3b-281">Threadpoolworkerthreadanpassmentadjustment-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-281">ThreadPoolWorkerThreadAdjustmentAdjustment event</span></span>

 <span data-ttu-id="48a3b-282">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-282">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-283">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-283">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-284">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-284">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-286">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-286">Informational (4)</span></span>|

 <span data-ttu-id="48a3b-287">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-287">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-288">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-288">Event</span></span>|<span data-ttu-id="48a3b-289">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-289">Event ID</span></span>|<span data-ttu-id="48a3b-290">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-290">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="48a3b-291">55</span><span class="sxs-lookup"><span data-stu-id="48a3b-291">55</span></span>|<span data-ttu-id="48a3b-292">Zeichnet eine Änderung der Steuerung auf, wenn der Algorithmus zur Threadinjektion (Hill-Climbing) ermittelt, dass auf der Parallelitätsebene eine Änderung vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="48a3b-292">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|

 <span data-ttu-id="48a3b-293">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-293">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-294">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-294">Field name</span></span>|<span data-ttu-id="48a3b-295">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-295">Data type</span></span>|<span data-ttu-id="48a3b-296">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-296">Description</span></span>|
|----------------|---------------|-----------------|
|`AverageThroughput`|`win:Double`|<span data-ttu-id="48a3b-297">Durchschnittlicher Durchsatz für eine Stichprobe von Messungen.</span><span class="sxs-lookup"><span data-stu-id="48a3b-297">Average throughput of a sample of measurements.</span></span>|
|`NewWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="48a3b-298">Neue Anzahl aktiver Arbeitsthreads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-298">New number of active worker threads.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="48a3b-299">Grund für die Anpassung.</span><span class="sxs-lookup"><span data-stu-id="48a3b-299">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="48a3b-300">`0x0` Aufwärm Dauer.</span><span class="sxs-lookup"><span data-stu-id="48a3b-300">`0x0` - Warmup.</span></span><br /><br /> <span data-ttu-id="48a3b-301">`0x1` Initialisieren.</span><span class="sxs-lookup"><span data-stu-id="48a3b-301">`0x1` - Initializing.</span></span><br /><br /> <span data-ttu-id="48a3b-302">`0x2` -Zufällige Verschiebung.</span><span class="sxs-lookup"><span data-stu-id="48a3b-302">`0x2` - Random move.</span></span><br /><br /> <span data-ttu-id="48a3b-303">`0x3` -Klettern verschieben.</span><span class="sxs-lookup"><span data-stu-id="48a3b-303">`0x3` - Climbing move.</span></span><br /><br /> <span data-ttu-id="48a3b-304">`0x4` -Punkt ändern.</span><span class="sxs-lookup"><span data-stu-id="48a3b-304">`0x4` - Change point.</span></span><br /><br /> <span data-ttu-id="48a3b-305">`0x5` Stabilisierungs.</span><span class="sxs-lookup"><span data-stu-id="48a3b-305">`0x5` - Stabilizing.</span></span><br /><br /> <span data-ttu-id="48a3b-306">`0x6` Nöten.</span><span class="sxs-lookup"><span data-stu-id="48a3b-306">`0x6` - Starvation.</span></span><br /><br /> <span data-ttu-id="48a3b-307">`0x7` -Beim Thread ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48a3b-307">`0x7` - Thread timed out.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-308">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-308">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a><span data-ttu-id="48a3b-309">Threadpoolworkerthreadaccessmentstats-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-309">ThreadPoolWorkerThreadAdjustmentStats event</span></span>

 <span data-ttu-id="48a3b-310">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-310">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-311">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-311">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-312">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-312">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-313">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-313">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-314">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="48a3b-314">Verbose (5)</span></span>

 <span data-ttu-id="48a3b-315">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-315">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-316">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-316">Event</span></span>|<span data-ttu-id="48a3b-317">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-317">Event ID</span></span>|<span data-ttu-id="48a3b-318">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-318">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="48a3b-319">56</span><span class="sxs-lookup"><span data-stu-id="48a3b-319">56</span></span>|<span data-ttu-id="48a3b-320">Erfasst Daten zum Threadpool.</span><span class="sxs-lookup"><span data-stu-id="48a3b-320">Gathers data on the thread pool.</span></span>|

 <span data-ttu-id="48a3b-321">In der folgenden Tabelle werden die Ereignisdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-321">The following table shows the event data</span></span>

|<span data-ttu-id="48a3b-322">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-322">Field name</span></span>|<span data-ttu-id="48a3b-323">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-323">Data type</span></span>|<span data-ttu-id="48a3b-324">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-324">Description</span></span>|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|<span data-ttu-id="48a3b-325">Zeitdauer in Sekunden, in der diese statistischen Daten erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="48a3b-325">Amount of time, in seconds, during which these statistics were collected.</span></span>|
|`Throughput`|`win:Double`|<span data-ttu-id="48a3b-326">Durchschnittliche Anzahl von Abschlüssen pro Sekunde während dieses Intervalls.</span><span class="sxs-lookup"><span data-stu-id="48a3b-326">Average number of completions per second during this interval.</span></span>|
|`ThreadWave`|`win:Double`|<span data-ttu-id="48a3b-327">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-327">Reserved for internal use.</span></span>|
|`ThroughputWave`|`win:Double`|<span data-ttu-id="48a3b-328">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-328">Reserved for internal use.</span></span>|
|`ThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="48a3b-329">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-329">Reserved for internal use.</span></span>|
|`AverageThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="48a3b-330">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-330">Reserved for internal use.</span></span>|
|`ThroughputRatio`|`win:Double`|<span data-ttu-id="48a3b-331">Die relative Verbesserung beim Durchsatz, die durch Abweichungen bei der aktiven Arbeitsthreadanzahl während dieses Intervalls verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="48a3b-331">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|
|`Confidence`|`win:Double`|<span data-ttu-id="48a3b-332">Ein Maß für die Gültigkeit des „ThroughputRatio“-Felds.</span><span class="sxs-lookup"><span data-stu-id="48a3b-332">A measure of the validity of the ThroughputRatio field.</span></span>|
|`NewcontrolSetting`|`win:Double`|<span data-ttu-id="48a3b-333">Die Anzahl der aktiven Arbeitsthreads, die als Grundlage für zukünftige Abweichungen bei der Anzahl aktiver Threads dienen werden.</span><span class="sxs-lookup"><span data-stu-id="48a3b-333">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|
|`NewThreadWaveMagnitude`|`win:UInt16`|<span data-ttu-id="48a3b-334">Das Ausmaß zukünftiger Abweichungen bei der Anzahl aktiver Threads.</span><span class="sxs-lookup"><span data-stu-id="48a3b-334">The magnitude of future variations in active thread count.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-335">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="48a3b-335">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolenqueue-event"></a><span data-ttu-id="48a3b-336">Thread pooleinqueue-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-336">ThreadPoolEnqueue event</span></span>

 <span data-ttu-id="48a3b-337">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-337">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-338">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-338">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-339">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-339">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-340">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-340">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-341">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="48a3b-341">Verbose (5)</span></span>

 <span data-ttu-id="48a3b-342">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-342">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-343">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-343">Event</span></span>|<span data-ttu-id="48a3b-344">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-344">Event ID</span></span>|<span data-ttu-id="48a3b-345">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-345">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|<span data-ttu-id="48a3b-346">61</span><span class="sxs-lookup"><span data-stu-id="48a3b-346">61</span></span>|<span data-ttu-id="48a3b-347">Ein Arbeits Element wurde in die Warteschlange des Thread Pools eingereiht.</span><span class="sxs-lookup"><span data-stu-id="48a3b-347">A work item was enqueued in the thread pool queue.</span></span>|

 <span data-ttu-id="48a3b-348">In der folgenden Tabelle werden die Ereignisdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-348">The following table shows the event data</span></span>

|<span data-ttu-id="48a3b-349">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-349">Field name</span></span>|<span data-ttu-id="48a3b-350">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-350">Data type</span></span>|<span data-ttu-id="48a3b-351">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-351">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="48a3b-352">Zeiger auf die Arbeits Anforderung.</span><span class="sxs-lookup"><span data-stu-id="48a3b-352">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-353">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="48a3b-353">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooldequeue-event"></a><span data-ttu-id="48a3b-354">Threadpoolentqueue-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-354">ThreadPoolDequeue event</span></span>

 <span data-ttu-id="48a3b-355">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-355">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-356">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-356">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-357">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-357">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-358">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-358">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-359">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="48a3b-359">Verbose (5)</span></span>

 <span data-ttu-id="48a3b-360">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-360">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-361">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-361">Event</span></span>|<span data-ttu-id="48a3b-362">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-362">Event ID</span></span>|<span data-ttu-id="48a3b-363">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-363">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|<span data-ttu-id="48a3b-364">62</span><span class="sxs-lookup"><span data-stu-id="48a3b-364">62</span></span>|<span data-ttu-id="48a3b-365">Eine Arbeitsaufgabe wurde aus der Warteschlange des Thread Pools entfernt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-365">A work item was dequeued from the thread pool queue.</span></span>|

 <span data-ttu-id="48a3b-366">In der folgenden Tabelle werden die Ereignisdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-366">The following table shows the event data</span></span>

|<span data-ttu-id="48a3b-367">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-367">Field name</span></span>|<span data-ttu-id="48a3b-368">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-368">Data type</span></span>|<span data-ttu-id="48a3b-369">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-369">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="48a3b-370">Zeiger auf die Arbeits Anforderung.</span><span class="sxs-lookup"><span data-stu-id="48a3b-370">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-371">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="48a3b-371">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpoolioenqueue-event"></a><span data-ttu-id="48a3b-372">Threadpoolioenqueue-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-372">ThreadPoolIOEnqueue event</span></span>

 <span data-ttu-id="48a3b-373">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-373">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-374">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-374">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-375">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-376">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-376">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-377">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="48a3b-377">Verbose (5)</span></span>

 <span data-ttu-id="48a3b-378">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-378">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-379">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-379">Event</span></span>|<span data-ttu-id="48a3b-380">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-380">Event ID</span></span>|<span data-ttu-id="48a3b-381">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-381">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|<span data-ttu-id="48a3b-382">63</span><span class="sxs-lookup"><span data-stu-id="48a3b-382">63</span></span>|<span data-ttu-id="48a3b-383">Ein Thread fügt eine e/A-Abschluss Benachrichtigung nach einem asynchronen e/A-Abschluss ein.</span><span class="sxs-lookup"><span data-stu-id="48a3b-383">A thread enqueues an IO completion notification after an async IO completion occurs.</span></span>|

 <span data-ttu-id="48a3b-384">In der folgenden Tabelle werden die Ereignisdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-384">The following table shows the event data</span></span>

|<span data-ttu-id="48a3b-385">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-385">Field name</span></span>|<span data-ttu-id="48a3b-386">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-386">Data type</span></span>|<span data-ttu-id="48a3b-387">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-387">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="48a3b-388">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-388">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="48a3b-389">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-389">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="48a3b-390">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-390">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-391">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="48a3b-391">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliodequeue-event"></a><span data-ttu-id="48a3b-392">Threadpooliodequeue-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-392">ThreadPoolIODequeue event</span></span>

 <span data-ttu-id="48a3b-393">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-393">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-394">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-394">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-395">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-395">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-396">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-396">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-397">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="48a3b-397">Verbose (5)</span></span>

 <span data-ttu-id="48a3b-398">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-398">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-399">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-399">Event</span></span>|<span data-ttu-id="48a3b-400">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-400">Event ID</span></span>|<span data-ttu-id="48a3b-401">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-401">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|<span data-ttu-id="48a3b-402">64</span><span class="sxs-lookup"><span data-stu-id="48a3b-402">64</span></span>|<span data-ttu-id="48a3b-403">Ein Thread entfernt die e/A-Abschluss Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="48a3b-403">A thread dequeues the IO completion notification.</span></span>|

 <span data-ttu-id="48a3b-404">In der folgenden Tabelle werden die Ereignisdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-404">The following table shows the event data</span></span>

|<span data-ttu-id="48a3b-405">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-405">Field name</span></span>|<span data-ttu-id="48a3b-406">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-406">Data type</span></span>|<span data-ttu-id="48a3b-407">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-407">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="48a3b-408">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-408">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="48a3b-409">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-409">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="48a3b-410">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-410">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-411">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="48a3b-411">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliopack-event"></a><span data-ttu-id="48a3b-412">Threadpooliopack-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-412">ThreadPoolIOPack event</span></span>

 <span data-ttu-id="48a3b-413">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-413">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="48a3b-414">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-414">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-415">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-415">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-416">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-416">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-417">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="48a3b-417">Verbose (5)</span></span>|

 <span data-ttu-id="48a3b-418">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-418">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-419">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-419">Event</span></span>|<span data-ttu-id="48a3b-420">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-420">Event ID</span></span>|<span data-ttu-id="48a3b-421">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-421">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|<span data-ttu-id="48a3b-422">65</span><span class="sxs-lookup"><span data-stu-id="48a3b-422">65</span></span>|<span data-ttu-id="48a3b-423">Das überlappende Thread Pool-e/a-Paket wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="48a3b-423">ThreadPool overlapped IO pack is called.</span></span>|

 <span data-ttu-id="48a3b-424">In der folgenden Tabelle werden die Ereignisdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-424">The following table shows the event data</span></span>

|<span data-ttu-id="48a3b-425">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-425">Field name</span></span>|<span data-ttu-id="48a3b-426">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-426">Data type</span></span>|<span data-ttu-id="48a3b-427">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-427">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="48a3b-428">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-428">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="48a3b-429">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="48a3b-429">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-430">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="48a3b-430">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadcreating-event"></a><span data-ttu-id="48a3b-431">Thread Creating-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-431">ThreadCreating event</span></span>

 <span data-ttu-id="48a3b-432">In der folgenden Tabelle sind die Schlüsselwörter und die Ebene aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-432">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="48a3b-433">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-433">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-434">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-435">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-435">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-436">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-436">Informational (4)</span></span>|

 <span data-ttu-id="48a3b-437">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-437">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-438">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-438">Event</span></span>|<span data-ttu-id="48a3b-439">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-439">Event ID</span></span>|<span data-ttu-id="48a3b-440">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-440">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadCreating`|<span data-ttu-id="48a3b-441">70</span><span class="sxs-lookup"><span data-stu-id="48a3b-441">70</span></span>|<span data-ttu-id="48a3b-442">Der Thread wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-442">Thread has been created.</span></span>|

 <span data-ttu-id="48a3b-443">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-443">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-444">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-444">Field name</span></span>|<span data-ttu-id="48a3b-445">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-445">Data type</span></span>|<span data-ttu-id="48a3b-446">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-446">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="48a3b-447">Thread-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-447">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-448">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="48a3b-448">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadrunning-event"></a><span data-ttu-id="48a3b-449">Thread Running-Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-449">ThreadRunning event</span></span>

 <span data-ttu-id="48a3b-450">In der folgenden Tabelle sind die Schlüsselwörter und die Ebene aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="48a3b-450">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="48a3b-451">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="48a3b-451">Keyword for raising the event</span></span>|<span data-ttu-id="48a3b-452">Ebene</span><span class="sxs-lookup"><span data-stu-id="48a3b-452">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48a3b-453">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48a3b-453">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48a3b-454">Information (4)</span><span class="sxs-lookup"><span data-stu-id="48a3b-454">Informational (4)</span></span>|

 <span data-ttu-id="48a3b-455">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-455">The following table shows the event information.</span></span>

|<span data-ttu-id="48a3b-456">Ereignis</span><span class="sxs-lookup"><span data-stu-id="48a3b-456">Event</span></span>|<span data-ttu-id="48a3b-457">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-457">Event ID</span></span>|<span data-ttu-id="48a3b-458">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-458">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadRunning`|<span data-ttu-id="48a3b-459">71</span><span class="sxs-lookup"><span data-stu-id="48a3b-459">71</span></span>|<span data-ttu-id="48a3b-460">Die Ausführung des Threads wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="48a3b-460">Thread has started running.</span></span>|

 <span data-ttu-id="48a3b-461">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="48a3b-461">The following table shows the event data.</span></span>

|<span data-ttu-id="48a3b-462">Feldname</span><span class="sxs-lookup"><span data-stu-id="48a3b-462">Field name</span></span>|<span data-ttu-id="48a3b-463">Datentyp</span><span class="sxs-lookup"><span data-stu-id="48a3b-463">Data type</span></span>|<span data-ttu-id="48a3b-464">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48a3b-464">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="48a3b-465">Thread-ID</span><span class="sxs-lookup"><span data-stu-id="48a3b-465">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="48a3b-466">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="48a3b-466">Unique ID for the instance of CoreCLR.</span></span>|
