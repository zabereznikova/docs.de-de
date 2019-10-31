---
title: Debugenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: 7948b78da1db5267ce53364af1e4a26ff73801e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124332"
---
# <a name="debugging-enumerations"></a><span data-ttu-id="1b6d3-102">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="1b6d3-102">Debugging Enumerations</span></span>
<span data-ttu-id="1b6d3-103">In diesem Abschnitt werden die nicht verwalteten Enumerationen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b6d3-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1b6d3-104">In This Section</span></span>  
 [<span data-ttu-id="1b6d3-105">CLR_DEBUGGING_PROCESS_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="1b6d3-106">Stellt Werte bereit, die von der [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="1b6d3-107">CLRDataEnumMemoryFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-107">CLRDataEnumMemoryFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="1b6d3-108">Gibt an, welche Speicherbereiche ein Aufrufe der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="1b6d3-109">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="1b6d3-110">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="1b6d3-111">CorDebugBlockingReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-111">CorDebugBlockingReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="1b6d3-112">Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="1b6d3-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="1b6d3-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="1b6d3-114">Gibt den Grund oder die Gründe für die Initiierung einer Aufrufkette an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="1b6d3-115">CorDebugCodeInvokeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-115">CorDebugCodeInvokeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="1b6d3-116">Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="1b6d3-117">CorDebugCodeInvokePurpose-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-117">CorDebugCodeInvokePurpose Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="1b6d3-118">Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="1b6d3-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="1b6d3-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="1b6d3-120">Bietet zusätzliche Debugoptionen, die in einem Aufrufen der [ICorDebug:: deateprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) -Methode verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="1b6d3-121">CorDebugDebugEventKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="1b6d3-121">CorDebugDebugEventKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="1b6d3-122">Gibt den Typ des Ereignisses an, dessen Informationen von der [decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) -Methode decodiert werden.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-122">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="1b6d3-123">CorDebugDecodeEventFlagsWindows-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="1b6d3-124">Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="1b6d3-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="1b6d3-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="1b6d3-126">Gibt den Typ des Rückrufs an, der von einem [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) -Ereignis stammt.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="1b6d3-127">CorDebugExceptionFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-127">CorDebugExceptionFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="1b6d3-128">Stellt zusätzliche Informationen über eine Ausnahme bereit.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="1b6d3-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="1b6d3-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="1b6d3-130">Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="1b6d3-131">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-131">CorDebugGCType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 <span data-ttu-id="1b6d3-132">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="1b6d3-133">CorDebugGenerationTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-133">CorDebugGenerationTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="1b6d3-134">Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="1b6d3-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="1b6d3-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="1b6d3-136">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="1b6d3-137">CorDebugIlToNativeMappingTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="1b6d3-138">Gibt an, ob ein besonderer Bereich systemeigener Anweisungen einem besonderen Codebereich entspricht.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="1b6d3-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="1b6d3-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="1b6d3-140">Gibt die Codetypen an, die schrittweise ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="1b6d3-141">CorDebugInterfaceVersion-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-141">CorDebugInterfaceVersion Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="1b6d3-142">Gibt entweder eine .NET Framework-Version oder die Version von .NET Framework an, in der eine Schnittstelle eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="1b6d3-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="1b6d3-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="1b6d3-144">Identifiziert den Stapelrahmentyp.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="1b6d3-145">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-145">CorDebugJITCompilerFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="1b6d3-146">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="1b6d3-147">CorDebugJITCompilerFlagsDeprecated-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="1b6d3-148">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-148">Obsolete.</span></span> <span data-ttu-id="1b6d3-149">Verwenden Sie stattdessen den `CORDEBUG_JIT_DEFAULT` Member der [Cordebug-Compilerflags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="1b6d3-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="1b6d3-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="1b6d3-151">Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="1b6d3-152">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-152">CorDebugMDAFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="1b6d3-153">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="1b6d3-154">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-154">CorDebugNGenPolicy Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="1b6d3-155">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="1b6d3-156">CorDebugPlatform-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-156">CorDebugPlatform Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 <span data-ttu-id="1b6d3-157">Stellt Ziel Platt Form Werte bereit, die von der [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="1b6d3-158">CorDebugRecordFormat-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-158">CorDebugRecordFormat Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="1b6d3-159">Beschreibt das Format der Daten in einem Byte-Array, das Informationen über ein systemeigenes Ausnahme-Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="1b6d3-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="1b6d3-160">CorDebugRegister</span></span>  
 <span data-ttu-id="1b6d3-161">Gibt die einer bestimmten Prozessorarchitektur zugeordneten Register an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="1b6d3-162">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-162">CorDebugSetContextFlag Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="1b6d3-163">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="1b6d3-164">CorDebugStateChange-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-164">CorDebugStateChange Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 <span data-ttu-id="1b6d3-165">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="1b6d3-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="1b6d3-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="1b6d3-167">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="1b6d3-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="1b6d3-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="1b6d3-169">Gibt den Zustand eines Threads zum Debuggen an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="1b6d3-170">\>cordebugunmappedstoppt</span><span class="sxs-lookup"><span data-stu-id="1b6d3-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="1b6d3-171">Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="1b6d3-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="1b6d3-172">CorDebugUserState</span></span>  
 <span data-ttu-id="1b6d3-173">Gibt den Benutzerzustand eines Threads an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="1b6d3-174">CorGCReferenceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-174">CorGCReferenceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 <span data-ttu-id="1b6d3-175">Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="1b6d3-176">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-176">ILCodeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 <span data-ttu-id="1b6d3-177">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="1b6d3-178">LoggingLevelEnum-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-178">LoggingLevelEnum Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 <span data-ttu-id="1b6d3-179">Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="1b6d3-180">LogSwitchCallReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-180">LogSwitchCallReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 <span data-ttu-id="1b6d3-181">Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="1b6d3-182">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-182">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 <span data-ttu-id="1b6d3-183">Gibt den Typ des systemeigenen Standorts einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="1b6d3-184">WriteableMetadataUpdateMode-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b6d3-184">WriteableMetadataUpdateMode Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="1b6d3-185">Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span> 

 <span data-ttu-id="1b6d3-186">[Clrdatasourcetype-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) Stellt Werte bereit, die von der CLRDATA_IL_ADDRESS_MAP-Struktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b6d3-186">[ClrDataSourceType Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="1b6d3-187">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1b6d3-187">Related Sections</span></span>  
 [<span data-ttu-id="1b6d3-188">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="1b6d3-188">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="1b6d3-189">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b6d3-189">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="1b6d3-190">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="1b6d3-190">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="1b6d3-191">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="1b6d3-191">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
