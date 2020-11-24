---
title: Debuggen von Strukturen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: bf84f8ddb1e86da3b9d0e4326584e61304640558
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676269"
---
# <a name="debugging-structures"></a><span data-ttu-id="cda41-102">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="cda41-102">Debugging Structures</span></span>

<span data-ttu-id="cda41-103">In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="cda41-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cda41-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cda41-104">In This Section</span></span>

 <span data-ttu-id="cda41-105">[CLRDATA_ADDRESS_RANGE Struktur](clrdata-address-range-structure.md) Definiert einen Adressbereich.</span><span class="sxs-lookup"><span data-stu-id="cda41-105">[CLRDATA_ADDRESS_RANGE Structure](clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="cda41-106">[CLRDATA_IL_ADDRESS_MAP Struktur](clrdata-il-address-map-structure.md) Definiert eine Zuordnung von Il zu Address.</span><span class="sxs-lookup"><span data-stu-id="cda41-106">[CLRDATA_IL_ADDRESS_MAP Structure](clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="cda41-107">[CLR_DEBUGGING_VERSION Struktur](clr-debugging-version-structure.md) Definiert die Produktversion des Common Language Runtime (CLR) zu Debuggingzwecken.</span><span class="sxs-lookup"><span data-stu-id="cda41-107">[CLR_DEBUGGING_VERSION Structure](clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="cda41-108">[CodeChunkInfo-Struktur](codechunkinfo-structure.md) Stellt einen einzelnen Code Abschnitt im Arbeitsspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="cda41-108">[CodeChunkInfo Structure](codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="cda41-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Enthält Informationen zu den Funktionen, die zurzeit in den Frames eines Threads aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="cda41-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="cda41-110">[COR_ARRAY_LAYOUT Struktur](cor-array-layout-structure.md) Stellt Informationen über das Layout eines Array Objekts im Arbeitsspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="cda41-110">[COR_ARRAY_LAYOUT Structure](cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="cda41-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Enthält die Offsets, die zum Zuordnen von MSIL-Code (Microsoft Intermediate Language) zu nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cda41-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="cda41-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Enthält die Offset Informationen für einen Code Bereich.</span><span class="sxs-lookup"><span data-stu-id="cda41-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="cda41-113">[COR_FIELD Struktur](cor-field-structure.md) Stellt Informationen zu einem Feld in einem-Objekt bereit.</span><span class="sxs-lookup"><span data-stu-id="cda41-113">[COR_FIELD Structure](cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="cda41-114">[COR_GC_REFERENCE Struktur](cor-gc-reference-structure.md) Enthält Informationen zu einem Objekt, für das eine Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cda41-114">[COR_GC_REFERENCE Structure](cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="cda41-115">[COR_HEAPINFO Struktur](cor-heapinfo-structure.md) Stellt allgemeine Informationen über den Garbage Collection Heap bereit, einschließlich der Aufzählung.</span><span class="sxs-lookup"><span data-stu-id="cda41-115">[COR_HEAPINFO Structure](cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="cda41-116">[COR_HEAPOBJECT Struktur](cor-heapobject-structure.md) Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="cda41-116">[COR_HEAPOBJECT Structure](cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="cda41-117">[COR_IL_MAP](cor-il-map-structure.md) Gibt Änderungen im relativen Offset einer Funktion an.</span><span class="sxs-lookup"><span data-stu-id="cda41-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="cda41-118">[COR_SEGMENT Struktur](cor-segment-structure.md) Enthält Informationen zu einem Speicherbereich im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="cda41-118">[COR_SEGMENT Structure](cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="cda41-119">[COR_TYPEID Struktur](cor-typeid-structure.md) Enthält einen Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="cda41-119">[COR_TYPEID Structure](cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="cda41-120">[COR_TYPE_LAYOUT Struktur](cor-type-layout-structure.md) Stellt Informationen über das Layout eines Objekts im Arbeitsspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="cda41-120">[COR_TYPE_LAYOUT Structure](cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="cda41-121">[COR_VERSION](cor-version-structure.md) Speichert die standardmäßige vierteilige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cda41-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="cda41-122">[Corentbugblockingobject-Struktur](cordebugblockingobject-structure.md) Definiert ein Objekt, das einen Thread blockiert, und den Grund, warum der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="cda41-122">[CorDebugBlockingObject Structure](cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="cda41-123">[Cordebugehclause-Struktur](cordebugehclause-structure.md) Stellt eine Ausnahmebehandlung (eh)-Klausel für einen angegebenen Teil der zwischen Sprache (IL) dar.</span><span class="sxs-lookup"><span data-stu-id="cda41-123">[CorDebugEHClause Structure](cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="cda41-124">[Cordebugexceptionobjectstackframe-Struktur](cordebugexceptionobjectstackframe-structure.md) Stellt Stapel Rahmen Informationen von einem Ausnahme Objekt dar.</span><span class="sxs-lookup"><span data-stu-id="cda41-124">[CorDebugExceptionObjectStackFrame Structure](cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="cda41-125">[Cordebug](cordebugguidtotypemapping-structure.md) Type-Struktur Ordnet eine Windows-Runtime GUID dem entsprechenden [ICorDebugType](icordebugtype-interface.md) -Objekt zu.</span><span class="sxs-lookup"><span data-stu-id="cda41-125">[CorDebugGuidToTypeMapping Structure](cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="cda41-126">[Dacpgetmoduleaddress-Struktur](dacpgetmoduleaddress-structure.md) Definiert den Container für eine Modul Adress Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cda41-126">[DacpGetModuleAddress Structure](dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="cda41-127">[Dacpmethoddescdata-Struktur](dacpmethoddescdata-structure.md) Definiert einen Transport Puffer für die Laufzeitinformationen einer Methode.</span><span class="sxs-lookup"><span data-stu-id="cda41-127">[DacpMethodDescData Structure](dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="cda41-128">[Dacpmoduledata-Struktur](dacpmoduledata-structure.md) Definiert einen Transport Puffer für die Laufzeitinformationen eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="cda41-128">[DacpModuleData Structure](dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="cda41-129">[Dacprejitdata-Struktur](dacprejitdata-structure.md) Definiert die grundlegenden Informationen zu einer bestimmten Profiler-instrumentierten Methode.</span><span class="sxs-lookup"><span data-stu-id="cda41-129">[DacpReJitData Structure](dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="cda41-130">[StackTrace_SimpleContext Struktur](stacktrace-simplecontext-structure.md) Stellt einen einfachen Kontext bereit, der anstelle einer vollständigen Struktur verwendet werden kann `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="cda41-130">[StackTrace_SimpleContext Structure](stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cda41-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cda41-131">Related Sections</span></span>

 [<span data-ttu-id="cda41-132">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="cda41-132">Debugging Coclasses</span></span>](debugging-coclasses.md)

 [<span data-ttu-id="cda41-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cda41-133">Debugging Interfaces</span></span>](debugging-interfaces.md)

 [<span data-ttu-id="cda41-134">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="cda41-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

 [<span data-ttu-id="cda41-135">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="cda41-135">Debugging Enumerations</span></span>](debugging-enumerations.md)

 [<span data-ttu-id="cda41-136">Debuggen</span><span class="sxs-lookup"><span data-stu-id="cda41-136">Debugging</span></span>](index.md)
