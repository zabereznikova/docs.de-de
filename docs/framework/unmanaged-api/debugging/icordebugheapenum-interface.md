---
title: ICorDebugHeapEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e317cb24e0eeaeaa38833433791eb546ee3c0478
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="93d92-102">ICorDebugHeapEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93d92-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="93d92-103">Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="93d92-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="93d92-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="93d92-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93d92-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="93d92-105">Methods</span></span>  
  
|<span data-ttu-id="93d92-106">Methode</span><span class="sxs-lookup"><span data-stu-id="93d92-106">Method</span></span>|<span data-ttu-id="93d92-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93d92-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93d92-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="93d92-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="93d92-109">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu Objekten im verwalteten Heap enthalten.</span><span class="sxs-lookup"><span data-stu-id="93d92-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93d92-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93d92-110">Remarks</span></span>  
 <span data-ttu-id="93d92-111">Die `ICorDebugHeapEnum` Schnittstelle implementiert ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="93d92-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="93d92-112">Ein `ICorDebugHeapEnum` Instanz wird mit aufgefüllt [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen durch Aufrufen der [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="93d92-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="93d92-113">Jede [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen in der Auflistung darstellt, entweder ein aktives Objekt auf dem Heap oder ein Objekt, das ist keines Objekt als Stamm, aber noch nicht vom Garbage Collector erfasst.</span><span class="sxs-lookup"><span data-stu-id="93d92-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="93d92-114">Die [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte in der Auflistung aufgelistet werden können, durch Aufrufen der [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="93d92-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93d92-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="93d92-115">Requirements</span></span>  
 <span data-ttu-id="93d92-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93d92-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93d92-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93d92-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93d92-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93d92-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93d92-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93d92-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d92-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93d92-120">See Also</span></span>  
 [<span data-ttu-id="93d92-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="93d92-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
