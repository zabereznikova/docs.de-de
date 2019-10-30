---
title: Debuggen von Strukturen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: 05a321d5025f03d6a0378b462178bf06c0291f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123032"
---
# <a name="debugging-structures"></a><span data-ttu-id="9f8a3-102">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="9f8a3-102">Debugging Structures</span></span>

<span data-ttu-id="9f8a3-103">In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9f8a3-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9f8a3-104">In This Section</span></span>
 <span data-ttu-id="9f8a3-105">[CLRDATA_ADDRESS_RANGE-Struktur](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Definiert einen Adressbereich.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="9f8a3-106">[CLRDATA_IL_ADDRESS_MAP-Struktur](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Definiert eine Zuordnung von Il zu Address.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="9f8a3-107">[CLR_DEBUGGING_VERSION-Struktur](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Definiert die Produktversion des Common Language Runtime (CLR) zu Debuggingzwecken.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="9f8a3-108">[CodeChunkInfo-Struktur](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Stellt einen einzelnen Code Abschnitt im Arbeitsspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="9f8a3-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Enthält Informationen zu den Funktionen, die zurzeit in den Frames eines Threads aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="9f8a3-110">[COR_ARRAY_LAYOUT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Stellt Informationen über das Layout eines Array Objekts im Arbeitsspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="9f8a3-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Enthält die Offsets, die zum Zuordnen von MSIL-Code (Microsoft Intermediate Language) zu nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="9f8a3-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Enthält die Offset Informationen für einen Code Bereich.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="9f8a3-113">[COR_FIELD-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Stellt Informationen zu einem Feld in einem-Objekt bereit.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="9f8a3-114">[COR_GC_REFERENCE-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Enthält Informationen zu einem Objekt, für das eine Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="9f8a3-115">[COR_HEAPINFO-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Stellt allgemeine Informationen über den Garbage Collection Heap bereit, einschließlich der Aufzählung.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="9f8a3-116">[COR_HEAPOBJECT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="9f8a3-117">[COR_IL_MAP](cor-il-map-structure.md) Gibt Änderungen im relativen Offset einer Funktion an.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="9f8a3-118">[COR_SEGMENT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Enthält Informationen zu einem Speicherbereich im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="9f8a3-119">[COR_TYPEID-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Enthält einen Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="9f8a3-120">[COR_TYPE_LAYOUT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Stellt Informationen über das Layout eines Objekts im Arbeitsspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="9f8a3-121">[COR_VERSION](cor-version-structure.md) Speichert die standardmäßige vierteilige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="9f8a3-122">[Corentbugblockingobject-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Definiert ein Objekt, das einen Thread blockiert, und den Grund, warum der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="9f8a3-123">[Cordebugehclause-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Stellt eine Ausnahmebehandlung (eh)-Klausel für einen angegebenen Teil der zwischen Sprache (IL) dar.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="9f8a3-124">[Cordebugexceptionobjectstackframe-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Stellt Stapel Rahmen Informationen von einem Ausnahme Objekt dar.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="9f8a3-125">[Cordebug](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Type-Struktur Ordnet eine Windows-Runtime GUID dem entsprechenden [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) -Objekt zu.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="9f8a3-126">[Dacpgetmoduleaddress-Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Definiert den Container für eine Modul Adress Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="9f8a3-127">[Dacpmethoddescdata-Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Definiert einen Transport Puffer für die Laufzeitinformationen einer Methode.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="9f8a3-128">[Dacpmoduledata-Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Definiert einen Transport Puffer für die Laufzeitinformationen eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="9f8a3-129">[Dacprejitdata-Struktur](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Definiert die grundlegenden Informationen zu einer bestimmten Profiler-instrumentierten Methode.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="9f8a3-130">[StackTrace_SimpleContext-Struktur](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Stellt einen einfachen Kontext bereit, der anstelle einer vollständigen `CONTEXT` Struktur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f8a3-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="9f8a3-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9f8a3-131">Related Sections</span></span>

 [<span data-ttu-id="9f8a3-132">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="9f8a3-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="9f8a3-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9f8a3-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="9f8a3-134">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="9f8a3-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="9f8a3-135">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9f8a3-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="9f8a3-136">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9f8a3-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
