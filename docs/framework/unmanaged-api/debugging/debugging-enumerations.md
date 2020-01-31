---
title: Debuggen von Enumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: a83b1aa0b2cc068ed2f73dca04083b1085d45201
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789163"
---
# <a name="debugging-enumerations"></a><span data-ttu-id="7ba39-102">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7ba39-102">Debugging Enumerations</span></span>
<span data-ttu-id="7ba39-103">In diesem Abschnitt werden die nicht verwalteten Enumerationen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ba39-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ba39-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7ba39-104">In This Section</span></span>  
 [<span data-ttu-id="7ba39-105">CLR_DEBUGGING_PROCESS_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="7ba39-106">Stellt Werte bereit, die von der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ba39-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="7ba39-107">CLRDataEnumMemoryFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-107">CLRDataEnumMemoryFlags Enumeration</span></span>](clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="7ba39-108">Gibt an, welche Speicherbereiche ein Aufrufe der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.</span><span class="sxs-lookup"><span data-stu-id="7ba39-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="7ba39-109">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="7ba39-110">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="7ba39-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="7ba39-111">CorDebugBlockingReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-111">CorDebugBlockingReason Enumeration</span></span>](cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="7ba39-112">Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="7ba39-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="7ba39-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="7ba39-114">Gibt den Grund oder die Gründe für die Initiierung einer Aufrufkette an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="7ba39-115">CorDebugCodeInvokeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-115">CorDebugCodeInvokeKind Enumeration</span></span>](cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="7ba39-116">Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7ba39-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="7ba39-117">CorDebugCodeInvokePurpose-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-117">CorDebugCodeInvokePurpose Enumeration</span></span>](cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="7ba39-118">Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7ba39-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="7ba39-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="7ba39-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="7ba39-120">Bietet zusätzliche Debugoptionen, die in einem Aufrufen der [ICorDebug:: deateprocess](icordebug-createprocess-method.md) -Methode verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7ba39-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="7ba39-121">CorDebugDebugEventKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="7ba39-121">CorDebugDebugEventKind Enumeration</span></span>](cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="7ba39-122">Gibt den Typ des Ereignisses an, dessen Informationen von der [decodeevent](icordebugprocess6-decodeevent-method.md) -Methode decodiert werden.</span><span class="sxs-lookup"><span data-stu-id="7ba39-122">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="7ba39-123">CorDebugDecodeEventFlagsWindows-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="7ba39-124">Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="7ba39-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="7ba39-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="7ba39-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="7ba39-126">Gibt den Typ des Rückrufs an, der von einem [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) -Ereignis stammt.</span><span class="sxs-lookup"><span data-stu-id="7ba39-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="7ba39-127">CorDebugExceptionFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-127">CorDebugExceptionFlags Enumeration</span></span>](cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="7ba39-128">Stellt zusätzliche Informationen über eine Ausnahme bereit.</span><span class="sxs-lookup"><span data-stu-id="7ba39-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="7ba39-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="7ba39-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="7ba39-130">Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7ba39-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="7ba39-131">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-131">CorDebugGCType Enumeration</span></span>](cordebuggctype-enumeration.md)  
 <span data-ttu-id="7ba39-132">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7ba39-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="7ba39-133">CorDebugGenerationTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-133">CorDebugGenerationTypes Enumeration</span></span>](cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="7ba39-134">Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="7ba39-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="7ba39-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="7ba39-136">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="7ba39-137">CorDebugIlToNativeMappingTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="7ba39-138">Gibt an, ob ein besonderer Bereich systemeigener Anweisungen einem besonderen Codebereich entspricht.</span><span class="sxs-lookup"><span data-stu-id="7ba39-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="7ba39-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="7ba39-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="7ba39-140">Gibt die Codetypen an, die schrittweise ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="7ba39-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="7ba39-141">CorDebugInterfaceVersion-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-141">CorDebugInterfaceVersion Enumeration</span></span>](cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="7ba39-142">Gibt entweder eine .NET Framework-Version oder die Version von .NET Framework an, in der eine Schnittstelle eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7ba39-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="7ba39-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="7ba39-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="7ba39-144">Identifiziert den Stapelrahmentyp.</span><span class="sxs-lookup"><span data-stu-id="7ba39-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="7ba39-145">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-145">CorDebugJITCompilerFlags Enumeration</span></span>](cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="7ba39-146">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="7ba39-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="7ba39-147">CorDebugJITCompilerFlagsDeprecated-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="7ba39-148">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="7ba39-148">Obsolete.</span></span> <span data-ttu-id="7ba39-149">Verwenden Sie stattdessen den `CORDEBUG_JIT_DEFAULT` Member der [Cordebug-Compilerflags](cordebugjitcompilerflags-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7ba39-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="7ba39-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="7ba39-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="7ba39-151">Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="7ba39-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="7ba39-152">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-152">CorDebugMDAFlags Enumeration</span></span>](cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="7ba39-153">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7ba39-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="7ba39-154">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-154">CorDebugNGenPolicy Enumeration</span></span>](cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="7ba39-155">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="7ba39-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="7ba39-156">CorDebugPlatform-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-156">CorDebugPlatform Enumeration</span></span>](cordebugplatform-enumeration.md)  
 <span data-ttu-id="7ba39-157">Stellt Ziel Platt Form Werte bereit, die von der [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ba39-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="7ba39-158">CorDebugRecordFormat-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-158">CorDebugRecordFormat Enumeration</span></span>](cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="7ba39-159">Beschreibt das Format der Daten in einem Byte-Array, das Informationen über ein systemeigenes Ausnahme-Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="7ba39-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="7ba39-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="7ba39-160">CorDebugRegister</span></span>  
 <span data-ttu-id="7ba39-161">Gibt die einer bestimmten Prozessorarchitektur zugeordneten Register an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="7ba39-162">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-162">CorDebugSetContextFlag Enumeration</span></span>](cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="7ba39-163">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="7ba39-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="7ba39-164">CorDebugStateChange-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-164">CorDebugStateChange Enumeration</span></span>](cordebugstatechange-enumeration.md)  
 <span data-ttu-id="7ba39-165">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7ba39-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="7ba39-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="7ba39-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="7ba39-167">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="7ba39-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="7ba39-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="7ba39-169">Gibt den Zustand eines Threads zum Debuggen an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="7ba39-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="7ba39-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="7ba39-171">Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="7ba39-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="7ba39-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="7ba39-172">CorDebugUserState</span></span>  
 <span data-ttu-id="7ba39-173">Gibt den Benutzerzustand eines Threads an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="7ba39-174">CorGCReferenceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-174">CorGCReferenceType Enumeration</span></span>](corgcreferencetype-enumeration.md)  
 <span data-ttu-id="7ba39-175">Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ba39-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="7ba39-176">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-176">ILCodeKind Enumeration</span></span>](ilcodekind-enumeration.md)  
 <span data-ttu-id="7ba39-177">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="7ba39-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="7ba39-178">LoggingLevelEnum-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-178">LoggingLevelEnum Enumeration</span></span>](logginglevelenum-enumeration.md)  
 <span data-ttu-id="7ba39-179">Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="7ba39-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="7ba39-180">LogSwitchCallReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-180">LogSwitchCallReason Enumeration</span></span>](logswitchcallreason-enumeration.md)  
 <span data-ttu-id="7ba39-181">Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7ba39-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="7ba39-182">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-182">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)  
 <span data-ttu-id="7ba39-183">Gibt den Typ des systemeigenen Standorts einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="7ba39-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="7ba39-184">WriteableMetadataUpdateMode-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7ba39-184">WriteableMetadataUpdateMode Enumeration</span></span>](writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="7ba39-185">Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="7ba39-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span> 

 <span data-ttu-id="7ba39-186">[Clrdatasourcetype-Enumeration](clrdatasourcetype-enumeration.md) Stellt Werte bereit, die von der CLRDATA_IL_ADDRESS_MAP Struktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ba39-186">[ClrDataSourceType Enumeration](clrdatasourcetype-enumeration.md) Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="7ba39-187">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7ba39-187">Related Sections</span></span>  
 [<span data-ttu-id="7ba39-188">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="7ba39-188">Debugging Coclasses</span></span>](debugging-coclasses.md)  
  
 [<span data-ttu-id="7ba39-189">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ba39-189">Debugging Interfaces</span></span>](debugging-interfaces.md)  
  
 [<span data-ttu-id="7ba39-190">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="7ba39-190">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)  
  
 [<span data-ttu-id="7ba39-191">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="7ba39-191">Debugging Structures</span></span>](debugging-structures.md)
