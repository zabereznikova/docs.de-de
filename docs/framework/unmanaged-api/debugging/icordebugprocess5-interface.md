---
title: ICorDebugProcess5-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
ms.openlocfilehash: 64fb60abf4f5730dbc15204dbc034b08cacefab9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121252"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="bf69c-102">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf69c-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="bf69c-103">Erweitert die ICorDebugProcess-Schnittstelle, um den Zugriff auf den verwalteten Heap zu unterstützen, um Informationen über Garbage Collection verwalteter Objekte bereitzustellen und um zu bestimmen, ob ein Debugger Bilder aus dem lokalen Anwendungssystem eigenen Image Cache lädt.</span><span class="sxs-lookup"><span data-stu-id="bf69c-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf69c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bf69c-104">Methods</span></span>  
  
|<span data-ttu-id="bf69c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-105">Method</span></span>|<span data-ttu-id="bf69c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf69c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf69c-107">EnableNGENPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="bf69c-108">Legt einen Wert fest, der bestimmt, wie eine Anwendung systemeigene Images lädt, während Sie unter einem verwalteten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bf69c-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="bf69c-109">EnumerateGCReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="bf69c-110">Ruft einen Enumerator für alle Objekte ab, die in einem Prozess in eine Garbage Collection aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bf69c-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="bf69c-111">EnumerateHandles-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="bf69c-112">Ruft einen Enumerator für Objekt Handles in einem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="bf69c-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="bf69c-113">EnumerateHeap-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="bf69c-114">Ruft einen Enumerator für Objekte im verwalteten Heap ab.</span><span class="sxs-lookup"><span data-stu-id="bf69c-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="bf69c-115">EnumerateHeapRegions-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="bf69c-116">Ruft einen Enumerator für Bereiche des verwalteten Heaps ab.</span><span class="sxs-lookup"><span data-stu-id="bf69c-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="bf69c-117">GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="bf69c-118">Ruft Informationen über das Layout eines Arrays im Arbeitsspeicher ab.</span><span class="sxs-lookup"><span data-stu-id="bf69c-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="bf69c-119">GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="bf69c-120">Ruft einen Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) -Struktur ab, die Informationen zu Objekten enthält, die auf dem verwalteten Heap Garbage Collection ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bf69c-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="bf69c-121">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="bf69c-122">Ruft einen Zeiger auf ein Objekt auf dem verwalteten Heap ab.</span><span class="sxs-lookup"><span data-stu-id="bf69c-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="bf69c-123">GetTypeFields-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="bf69c-124">Ruft einen Zeiger auf ein Array ab, das Feldinformationen für einen Typ auf Grundlage des Typbezeichners enthält.</span><span class="sxs-lookup"><span data-stu-id="bf69c-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="bf69c-125">GetTypeForTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="bf69c-126">Ruft ein Type-Objekt ab, das Informationen zu einem-Objekt auf der Grundlage seiner Typbezeichner bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="bf69c-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="bf69c-127">GetTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="bf69c-128">Ruft den Typbezeichner für das-Objekt an einer angegebenen Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="bf69c-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="bf69c-129">GetTypeLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="bf69c-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="bf69c-130">Ruft Informationen über das Layout eines Objekts im Arbeitsspeicher auf Grundlage des Typbezeichners ab.</span><span class="sxs-lookup"><span data-stu-id="bf69c-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf69c-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf69c-131">Remarks</span></span>  
 <span data-ttu-id="bf69c-132">Diese Schnittstelle erweitert logisch die ICorDebugProcess-, ICorDebugProcess2-und [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) -Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="bf69c-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf69c-133">Diese Schnittstelle bietet keine Unterstützung für das Remote Aufrufen von einem anderen Computer oder von einem anderen Prozess.</span><span class="sxs-lookup"><span data-stu-id="bf69c-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf69c-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf69c-134">Requirements</span></span>  
 <span data-ttu-id="bf69c-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf69c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf69c-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf69c-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf69c-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf69c-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf69c-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf69c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf69c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf69c-139">See also</span></span>

- [<span data-ttu-id="bf69c-140">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bf69c-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bf69c-141">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bf69c-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
