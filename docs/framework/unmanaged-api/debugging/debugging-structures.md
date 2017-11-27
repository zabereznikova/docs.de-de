---
title: Debuggen von Strukturen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0293a20f5f735dd38b1d167ebc5057f645fa011a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-structures"></a><span data-ttu-id="4aef3-102">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="4aef3-102">Debugging Structures</span></span>
<span data-ttu-id="4aef3-103">In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="4aef3-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4aef3-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4aef3-104">In This Section</span></span>  
 [<span data-ttu-id="4aef3-105">CLR_DEBUGGING_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="4aef3-106">Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.</span><span class="sxs-lookup"><span data-stu-id="4aef3-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="4aef3-107">CodeChunkInfo Structure1</span><span class="sxs-lookup"><span data-stu-id="4aef3-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="4aef3-108">Stellt einen einzelnen Codeabschnitt im Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="4aef3-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="4aef3-109">CorDebugBlockingObject-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="4aef3-110">Definiert ein Objekt, das einen Thread blockiert, sowie die Ursache, weshalb der Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="4aef3-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="4aef3-111">CorDebugEHClause-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="4aef3-112">Stellt eine Ausnahmebehandlung (Exception Handling, EH)-Klausel für einen bestimmten Intermediate Language (IL)-Codeabschnitt dar.</span><span class="sxs-lookup"><span data-stu-id="4aef3-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="4aef3-113">CorDebugExceptionObjectStackFrame-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="4aef3-114">Stellt Stapelrahmeninformationen von einem Ausnahmeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="4aef3-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="4aef3-115">CorDebugExceptionObjectStackFrame-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="4aef3-116">Ordnet eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID dem entsprechenden [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="4aef3-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="4aef3-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="4aef3-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="4aef3-118">Enthält Informationen zu den Funktionen, die aktuell in den Rahmen eines Threads aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="4aef3-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="4aef3-119">COR_ARRAY_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="4aef3-120">Bietet Informationen zum Layout eines Arrayobjekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="4aef3-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="4aef3-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="4aef3-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="4aef3-122">Enthält die Offsets, die genutzt werden, um Microsoft Intermediate Language (MSIL)-Code nativem Code zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="4aef3-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="4aef3-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="4aef3-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="4aef3-124">Enthält die Offsetinformationen für einen Codebereich.</span><span class="sxs-lookup"><span data-stu-id="4aef3-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="4aef3-125">COR_FIELD-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="4aef3-126">Bietet Informationen zu einem Feld in einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="4aef3-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="4aef3-127">COR_GC_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="4aef3-128">Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4aef3-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="4aef3-129">COR_HEAPINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="4aef3-130">Liefert allgemeine Informationen zum Garbage Collection-Heap, auch zu dessen Aufzählbarkeit.</span><span class="sxs-lookup"><span data-stu-id="4aef3-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="4aef3-131">COR_HEAPOBJECT-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="4aef3-132">Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="4aef3-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="4aef3-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="4aef3-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="4aef3-134">Gibt Änderungen im relativen Offset einer Funktion an.</span><span class="sxs-lookup"><span data-stu-id="4aef3-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="4aef3-135">COR_SEGMENT-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="4aef3-136">Enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="4aef3-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="4aef3-137">COR_TYPEID-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="4aef3-138">Enthält einen Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="4aef3-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="4aef3-139">COR_TYPE_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="4aef3-140">Bietet Informationen zum Layout eines Objekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="4aef3-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="4aef3-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="4aef3-141">COR_VERSION</span></span>  
 <span data-ttu-id="4aef3-142">Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4aef3-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="4aef3-143">StackTrace_SimpleContext-Struktur</span><span class="sxs-lookup"><span data-stu-id="4aef3-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="4aef3-144">Stellt einen einfachen Kontext bereit, der statt einer vollständigen `CONTEXT`-Struktur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4aef3-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4aef3-145">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4aef3-145">Related Sections</span></span>  
 [<span data-ttu-id="4aef3-146">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="4aef3-146">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="4aef3-147">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4aef3-147">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="4aef3-148">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="4aef3-148">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="4aef3-149">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="4aef3-149">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="4aef3-150">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4aef3-150">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
