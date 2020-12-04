---
title: Ausnahmen Lauf Zeit Ereignisse
description: Informationen zu den Ausnahmen und zur Ausnahmebehandlung finden Sie unter .net-Lauf Zeit Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- exception events (CoreCLR)
- exception handling events (CoreCLR)
- ETW, EventPipe, LTTng exception events (CoreCLR)
ms.openlocfilehash: f4f63c8469f9c734b872ddaec8d1d7f7f0427576
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96592101"
---
# <a name="net-runtime-exception-events"></a><span data-ttu-id="7f721-103">Ausnahmen Ereignisse der .NET-Runtime</span><span class="sxs-lookup"><span data-stu-id="7f721-103">.NET runtime exception events</span></span>

<span data-ttu-id="7f721-104">Diese Lauf Zeit Ereignisse erfassen Informationen zu Ausnahmen, die ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7f721-104">These runtime events capture information about exceptions that are thrown.</span></span> <span data-ttu-id="7f721-105">Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="7f721-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="exceptionthrown_v1-event"></a><span data-ttu-id="7f721-106">ExceptionThrown_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-106">ExceptionThrown_V1 event</span></span>

|<span data-ttu-id="7f721-107">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-107">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-108">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-109">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-109">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-110">Fehler (1)</span><span class="sxs-lookup"><span data-stu-id="7f721-110">Error (1)</span></span>|

 <span data-ttu-id="7f721-111">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-111">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-112">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-112">Event</span></span>|<span data-ttu-id="7f721-113">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-113">Event ID</span></span>|<span data-ttu-id="7f721-114">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-114">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrown_V1`|<span data-ttu-id="7f721-115">80</span><span class="sxs-lookup"><span data-stu-id="7f721-115">80</span></span>|<span data-ttu-id="7f721-116">Eine verwaltete Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7f721-116">A managed exception is thrown.</span></span>|

|<span data-ttu-id="7f721-117">Feldname</span><span class="sxs-lookup"><span data-stu-id="7f721-117">Field name</span></span>|<span data-ttu-id="7f721-118">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7f721-118">Data type</span></span>|<span data-ttu-id="7f721-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f721-119">Description</span></span>|
|----------------|---------------|-----------------|
|`ExceptionType`|`win:UnicodeString`|<span data-ttu-id="7f721-120">Typ der Ausnahme, z.B. `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="7f721-120">Type of the exception; for example, `System.NullReferenceException`.</span></span>|
|`ExceptionMessage`|`win:UnicodeString`|<span data-ttu-id="7f721-121">Tatsächliche Ausnahmemeldung.</span><span class="sxs-lookup"><span data-stu-id="7f721-121">Actual exception message.</span></span>|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="7f721-122">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-122">Instruction pointer where exception occurred.</span></span>|
|`ExceptionHR`|`win:UInt32`|<span data-ttu-id="7f721-123">Ausnahme [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="7f721-123">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|
|`ExceptionFlags`|`win:UInt16`|<span data-ttu-id="7f721-124">`0x01`: Hasinnerexception.</span><span class="sxs-lookup"><span data-stu-id="7f721-124">`0x01`: HasInnerException.</span></span><br /><br /> <span data-ttu-id="7f721-125">`0x02`: Isnetstedexception.</span><span class="sxs-lookup"><span data-stu-id="7f721-125">`0x02`: IsNestedException.</span></span><br /><br /> <span data-ttu-id="7f721-126">`0x04`: Isrethrownexception.</span><span class="sxs-lookup"><span data-stu-id="7f721-126">`0x04`: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="7f721-127">`0x08`: Isbeschätedstateexception (gibt an, dass der Prozessstatus beschädigt ist; weitere Informationen finden Sie unter [Behandeln von Ausnahmen für beschädigte](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)Zustände).</span><span class="sxs-lookup"><span data-stu-id="7f721-127">`0x08`: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="7f721-128">`0x10`: Isclscompliance (eine Ausnahme, die von abgeleitet <xref:System.Exception> ist, ist CLS-kompatibel, andernfalls ist Sie nicht CLS-kompatibel).</span><span class="sxs-lookup"><span data-stu-id="7f721-128">`0x10`: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="7f721-129">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7f721-129">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstart-event"></a><span data-ttu-id="7f721-130">Exceptionereignis starten</span><span class="sxs-lookup"><span data-stu-id="7f721-130">ExceptionCatchStart event</span></span>

<span data-ttu-id="7f721-131">Dieses Ereignis wird ausgegeben, wenn ein verwalteter Ausnahme catch-Handler beginnt.</span><span class="sxs-lookup"><span data-stu-id="7f721-131">This event is emitted when a managed exception catch handler begins.</span></span>

|<span data-ttu-id="7f721-132">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-132">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-133">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-133">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-134">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-134">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-135">Information (4)</span><span class="sxs-lookup"><span data-stu-id="7f721-135">Informational (4)</span></span>|

 <span data-ttu-id="7f721-136">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-136">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-137">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-137">Event</span></span>|<span data-ttu-id="7f721-138">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-138">Event ID</span></span>|<span data-ttu-id="7f721-139">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-139">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStart`|<span data-ttu-id="7f721-140">250</span><span class="sxs-lookup"><span data-stu-id="7f721-140">250</span></span>|<span data-ttu-id="7f721-141">Eine verwaltete Ausnahme wird von der Laufzeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="7f721-141">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="7f721-142">Feldname</span><span class="sxs-lookup"><span data-stu-id="7f721-142">Field name</span></span>|<span data-ttu-id="7f721-143">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7f721-143">Data type</span></span>|<span data-ttu-id="7f721-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f721-144">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="7f721-145">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-145">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="7f721-146">Zeiger auf den Methoden Deskriptor für die Methode, in der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-146">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="7f721-147">Der Name der Methode, in der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-147">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="7f721-148">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7f721-148">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstop-event"></a><span data-ttu-id="7f721-149">Exceptionskichstoppt-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-149">ExceptionCatchStop event</span></span>

<span data-ttu-id="7f721-150">Dieses Ereignis wird ausgegeben, wenn ein verwalteter Ausnahme-catch-Handler beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f721-150">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="7f721-151">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-151">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-152">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-152">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-153">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-153">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-154">Information (4)</span><span class="sxs-lookup"><span data-stu-id="7f721-154">Informational (4)</span></span>|

 <span data-ttu-id="7f721-155">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-155">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-156">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-156">Event</span></span>|<span data-ttu-id="7f721-157">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-157">Event ID</span></span>|<span data-ttu-id="7f721-158">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-158">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStop`|<span data-ttu-id="7f721-159">251</span><span class="sxs-lookup"><span data-stu-id="7f721-159">251</span></span>|<span data-ttu-id="7f721-160">Ein verwalteter Ausnahme-catch-Handler ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7f721-160">A managed exception catch handler is done.</span></span>|

## <a name="exceptionfinallystart-event"></a><span data-ttu-id="7f721-161">Exceptionfinallystart-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-161">ExceptionFinallyStart event</span></span>

<span data-ttu-id="7f721-162">Dieses Ereignis wird ausgegeben, wenn eine verwaltete Ausnahme zuletzt mit dem Handler beginnt.</span><span class="sxs-lookup"><span data-stu-id="7f721-162">This event is emitted when a managed exception finally handler begins.</span></span>

|<span data-ttu-id="7f721-163">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-163">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-164">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-164">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-165">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-165">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-166">Information (4)</span><span class="sxs-lookup"><span data-stu-id="7f721-166">Informational (4)</span></span>|

 <span data-ttu-id="7f721-167">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-167">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-168">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-168">Event</span></span>|<span data-ttu-id="7f721-169">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-169">Event ID</span></span>|<span data-ttu-id="7f721-170">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-170">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStart`|<span data-ttu-id="7f721-171">252</span><span class="sxs-lookup"><span data-stu-id="7f721-171">252</span></span>|<span data-ttu-id="7f721-172">Eine verwaltete Ausnahme wird von der Laufzeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="7f721-172">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="7f721-173">Feldname</span><span class="sxs-lookup"><span data-stu-id="7f721-173">Field name</span></span>|<span data-ttu-id="7f721-174">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7f721-174">Data type</span></span>|<span data-ttu-id="7f721-175">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f721-175">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="7f721-176">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-176">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="7f721-177">Zeiger auf den Methoden Deskriptor für die Methode, in der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-177">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="7f721-178">Der Name der Methode, in der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-178">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="7f721-179">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7f721-179">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptionfinallystop-event"></a><span data-ttu-id="7f721-180">Exceptionfinallybeenden-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-180">ExceptionFinallyStop event</span></span>

<span data-ttu-id="7f721-181">Dieses Ereignis wird ausgegeben, wenn ein verwalteter Ausnahme-catch-Handler beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f721-181">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="7f721-182">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-182">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-183">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-183">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-184">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-184">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-185">Information (4)</span><span class="sxs-lookup"><span data-stu-id="7f721-185">Informational (4)</span></span>|

 <span data-ttu-id="7f721-186">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-186">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-187">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-187">Event</span></span>|<span data-ttu-id="7f721-188">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-188">Event ID</span></span>|<span data-ttu-id="7f721-189">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-189">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStop`|<span data-ttu-id="7f721-190">253</span><span class="sxs-lookup"><span data-stu-id="7f721-190">253</span></span>|<span data-ttu-id="7f721-191">Eine verwaltete Ausnahme ist schließlich der Handler.</span><span class="sxs-lookup"><span data-stu-id="7f721-191">A managed exception finally handler is done.</span></span>|

## <a name="exceptionfilterstart-event"></a><span data-ttu-id="7f721-192">Exceptionfilterstart-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-192">ExceptionFilterStart event</span></span>

<span data-ttu-id="7f721-193">Dieses Ereignis wird ausgegeben, wenn eine verwaltete Ausnahme Filterung beginnt.</span><span class="sxs-lookup"><span data-stu-id="7f721-193">This event is emitted when a managed exception filtering begins.</span></span>

|<span data-ttu-id="7f721-194">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-194">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-195">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-195">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-196">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-196">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-197">Information (4)</span><span class="sxs-lookup"><span data-stu-id="7f721-197">Informational (4)</span></span>|

 <span data-ttu-id="7f721-198">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-198">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-199">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-199">Event</span></span>|<span data-ttu-id="7f721-200">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-200">Event ID</span></span>|<span data-ttu-id="7f721-201">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-201">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilterStart`|<span data-ttu-id="7f721-202">254</span><span class="sxs-lookup"><span data-stu-id="7f721-202">254</span></span>|<span data-ttu-id="7f721-203">Eine verwaltete Ausnahme Filterung beginnt.</span><span class="sxs-lookup"><span data-stu-id="7f721-203">A managed exception filtering begins.</span></span>|

|<span data-ttu-id="7f721-204">Feldname</span><span class="sxs-lookup"><span data-stu-id="7f721-204">Field name</span></span>|<span data-ttu-id="7f721-205">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7f721-205">Data type</span></span>|<span data-ttu-id="7f721-206">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f721-206">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="7f721-207">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-207">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="7f721-208">Zeiger auf den Methoden Deskriptor für die Methode, in der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-208">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="7f721-209">Der Name der Methode, in der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f721-209">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="7f721-210">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="7f721-210">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="exceptionfilterstop-event"></a><span data-ttu-id="7f721-211">Exceptionfilterstoppt-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-211">ExceptionFilterStop event</span></span>

<span data-ttu-id="7f721-212">Dieses Ereignis wird ausgegeben, wenn eine verwaltete Ausnahme Filterung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f721-212">This event is emitted when a managed exception filtering ends.</span></span>

|<span data-ttu-id="7f721-213">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-213">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-214">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-214">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-215">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-215">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-216">Information (4)</span><span class="sxs-lookup"><span data-stu-id="7f721-216">Informational (4)</span></span>|

 <span data-ttu-id="7f721-217">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-217">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-218">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-218">Event</span></span>|<span data-ttu-id="7f721-219">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-219">Event ID</span></span>|<span data-ttu-id="7f721-220">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-220">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilteringStart`|<span data-ttu-id="7f721-221">255</span><span class="sxs-lookup"><span data-stu-id="7f721-221">255</span></span>|<span data-ttu-id="7f721-222">Eine verwaltete Ausnahme Filterung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="7f721-222">A managed exception filtering ends.</span></span>|

## <a name="exceptionthrownstop-event"></a><span data-ttu-id="7f721-223">Exceptionthrownstoppt-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-223">ExceptionThrownStop event</span></span>

<span data-ttu-id="7f721-224">Dieses Ereignis wird ausgegeben, wenn die Laufzeit eine verwaltete Ausnahme verarbeitet hat, die ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="7f721-224">This event is emitted when the runtime is done handling a managed exception that was thrown.</span></span>

|<span data-ttu-id="7f721-225">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7f721-225">Keyword for raising the event</span></span>|<span data-ttu-id="7f721-226">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f721-226">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7f721-227">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="7f721-227">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="7f721-228">Information (4)</span><span class="sxs-lookup"><span data-stu-id="7f721-228">Informational (4)</span></span>|
  
 <span data-ttu-id="7f721-229">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7f721-229">The following table shows event information.</span></span>

|<span data-ttu-id="7f721-230">Ereignis</span><span class="sxs-lookup"><span data-stu-id="7f721-230">Event</span></span>|<span data-ttu-id="7f721-231">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f721-231">Event ID</span></span>|<span data-ttu-id="7f721-232">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="7f721-232">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrownStop`|<span data-ttu-id="7f721-233">256</span><span class="sxs-lookup"><span data-stu-id="7f721-233">256</span></span>|<span data-ttu-id="7f721-234">Eine verwaltete Ausnahme Filterung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="7f721-234">A managed exception filtering ends.</span></span>|
