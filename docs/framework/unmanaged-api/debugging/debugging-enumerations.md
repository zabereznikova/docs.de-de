---
title: Debugenumerationen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c24882f2bd9819043bbc786bd2e5f35129a92744
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-enumerations"></a><span data-ttu-id="5b4ae-102">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="5b4ae-102">Debugging Enumerations</span></span>
<span data-ttu-id="5b4ae-103">In diesem Abschnitt werden die nicht verwalteten Enumerationen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b4ae-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b4ae-104">In This Section</span></span>  
 [<span data-ttu-id="5b4ae-105">CLR_DEBUGGING_PROCESS_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="5b4ae-106">Enthält Werte, mit denen, die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="5b4ae-107">CLRDataEnumMemoryFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-107">CLRDataEnumMemoryFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="5b4ae-108">Zeigt an, welche Speicherbereiche ein Aufruf der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="5b4ae-109">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="5b4ae-110">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="5b4ae-111">CorDebugBlockingReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-111">CorDebugBlockingReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="5b4ae-112">Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="5b4ae-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="5b4ae-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="5b4ae-114">Gibt den Grund oder die Gründe für die Initiierung einer Aufrufkette an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="5b4ae-115">CorDebugCodeInvokeKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="5b4ae-115">CorDebugCodeInvokeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="5b4ae-116">Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="5b4ae-117">CorDebugCodeInvokePurpose-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="5b4ae-117">CorDebugCodeInvokePurpose Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="5b4ae-118">Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="5b4ae-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="5b4ae-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="5b4ae-120">Stellt zusätzliche Debuggingoptionen, die in einem Aufruf verwendet werden, können die [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="5b4ae-121">CorDebugDebugEventKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="5b4ae-121">CorDebugDebugEventKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="5b4ae-122">Gibt den Typ des Ereignisses, dessen Informationen mit der [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-122">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="5b4ae-123">CorDebugDecodeEventFlagsWindows-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="5b4ae-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="5b4ae-124">Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="5b4ae-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="5b4ae-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="5b4ae-126">Gibt den Typ des Rückrufs an, die aus wird ein [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="5b4ae-127">CorDebugExceptionFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-127">CorDebugExceptionFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="5b4ae-128">Stellt zusätzliche Informationen über eine Ausnahme bereit.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="5b4ae-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="5b4ae-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="5b4ae-130">Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="5b4ae-131">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-131">CorDebugGCType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 <span data-ttu-id="5b4ae-132">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="5b4ae-133">CorDebugGenerationTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-133">CorDebugGenerationTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="5b4ae-134">Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="5b4ae-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="5b4ae-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="5b4ae-136">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="5b4ae-137">CorDebugIlToNativeMappingTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="5b4ae-138">Gibt an, ob ein besonderer Bereich systemeigener Anweisungen einem besonderen Codebereich entspricht.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="5b4ae-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="5b4ae-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="5b4ae-140">Gibt die Codetypen an, die schrittweise ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="5b4ae-141">CorDebugInterfaceVersion-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-141">CorDebugInterfaceVersion Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="5b4ae-142">Gibt entweder eine .NET Framework-Version oder die Version von .NET Framework an, in der eine Schnittstelle eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="5b4ae-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="5b4ae-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="5b4ae-144">Identifiziert den Stapelrahmentyp.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="5b4ae-145">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-145">CorDebugJITCompilerFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="5b4ae-146">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="5b4ae-147">CorDebugJITCompilerFlagsDeprecated-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="5b4ae-148">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-148">Obsolete.</span></span> <span data-ttu-id="5b4ae-149">Verwenden der `CORDEBUG_JIT_DEFAULT` Mitglied der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumeration stattdessen.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="5b4ae-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="5b4ae-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="5b4ae-151">Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="5b4ae-152">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-152">CorDebugMDAFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="5b4ae-153">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="5b4ae-154">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-154">CorDebugNGenPolicy Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="5b4ae-155">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="5b4ae-156">CorDebugPlatform-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-156">CorDebugPlatform Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 <span data-ttu-id="5b4ae-157">Stellt Zielplattformwerte, mit denen, die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="5b4ae-158">CorDebugRecordFormat-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="5b4ae-158">CorDebugRecordFormat Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="5b4ae-159">Beschreibt das Format der Daten in einem Byte-Array, das Informationen über ein systemeigenes Ausnahme-Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="5b4ae-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="5b4ae-160">CorDebugRegister</span></span>  
 <span data-ttu-id="5b4ae-161">Gibt die einer bestimmten Prozessorarchitektur zugeordneten Register an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="5b4ae-162">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-162">CorDebugSetContextFlag Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="5b4ae-163">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="5b4ae-164">CorDebugStateChange-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="5b4ae-164">CorDebugStateChange Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 <span data-ttu-id="5b4ae-165">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="5b4ae-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="5b4ae-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="5b4ae-167">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="5b4ae-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="5b4ae-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="5b4ae-169">Gibt den Zustand eines Threads zum Debuggen an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="5b4ae-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="5b4ae-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="5b4ae-171">Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="5b4ae-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="5b4ae-172">CorDebugUserState</span></span>  
 <span data-ttu-id="5b4ae-173">Gibt den Benutzerzustand eines Threads an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="5b4ae-174">CorGCReferenceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-174">CorGCReferenceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 <span data-ttu-id="5b4ae-175">Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="5b4ae-176">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-176">ILCodeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 <span data-ttu-id="5b4ae-177">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="5b4ae-178">LoggingLevelEnum-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-178">LoggingLevelEnum Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 <span data-ttu-id="5b4ae-179">Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="5b4ae-180">LogSwitchCallReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-180">LogSwitchCallReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 <span data-ttu-id="5b4ae-181">Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="5b4ae-182">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-182">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 <span data-ttu-id="5b4ae-183">Gibt den systemeigenen Typ einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="5b4ae-184">WriteableMetadataUpdateMode-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b4ae-184">WriteableMetadataUpdateMode Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="5b4ae-185">Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="5b4ae-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5b4ae-186">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5b4ae-186">Related Sections</span></span>  
 [<span data-ttu-id="5b4ae-187">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="5b4ae-187">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="5b4ae-188">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5b4ae-188">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="5b4ae-189">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="5b4ae-189">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="5b4ae-190">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="5b4ae-190">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
