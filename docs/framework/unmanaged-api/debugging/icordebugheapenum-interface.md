---
title: ICorDebugHeapEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: bed2871c46712490bc4b0520fa1ab8023dbab5cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794425"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="31d2c-102">ICorDebugHeapEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31d2c-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="31d2c-103">Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="31d2c-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="31d2c-104">Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="31d2c-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31d2c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="31d2c-105">Methods</span></span>  
  
|<span data-ttu-id="31d2c-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="31d2c-106">Method</span></span>|<span data-ttu-id="31d2c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31d2c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31d2c-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="31d2c-108">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="31d2c-109">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen ab, die Informationen zu Objekten im verwalteten Heap enthalten.</span><span class="sxs-lookup"><span data-stu-id="31d2c-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31d2c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31d2c-110">Remarks</span></span>  
 <span data-ttu-id="31d2c-111">Die `ICorDebugHeapEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="31d2c-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="31d2c-112">Eine `ICorDebugHeapEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheap](icordebugprocess5-enumerateheap-method.md) -Methode mit [COR_HEAPOBJECT](cor-heapobject-structure.md) -Instanzen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="31d2c-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="31d2c-113">Jede [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanz in der Auflistung stellt entweder ein Live Objekt auf dem Heap oder ein Objekt dar, das nicht von einem Objekt betroffen ist, aber noch nicht vom Garbage Collector erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="31d2c-113">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="31d2c-114">Die [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekte in der Auflistung können durch Aufrufen der [icordebugheapenumum:: Next](icordebugheapenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="31d2c-114">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d2c-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31d2c-115">Requirements</span></span>  
 <span data-ttu-id="31d2c-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31d2c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d2c-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31d2c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31d2c-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31d2c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31d2c-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d2c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d2c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31d2c-120">See also</span></span>

- [<span data-ttu-id="31d2c-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="31d2c-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
