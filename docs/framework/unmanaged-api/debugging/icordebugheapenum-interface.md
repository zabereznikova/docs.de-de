---
title: ICorDebugHeapEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapEnum
helpviewer_keywords: ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbc97aec2fc9758df17767188c6b4d044b5016fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="f21b1-102">ICorDebugHeapEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f21b1-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="f21b1-103">Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="f21b1-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="f21b1-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f21b1-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f21b1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f21b1-105">Methods</span></span>  
  
|<span data-ttu-id="f21b1-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f21b1-106">Method</span></span>|<span data-ttu-id="f21b1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f21b1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f21b1-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="f21b1-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="f21b1-109">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu Objekten im verwalteten Heap enthalten.</span><span class="sxs-lookup"><span data-stu-id="f21b1-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f21b1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f21b1-110">Remarks</span></span>  
 <span data-ttu-id="f21b1-111">Die `ICorDebugHeapEnum` Schnittstelle implementiert ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f21b1-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="f21b1-112">Ein `ICorDebugHeapEnum` Instanz wird mit aufgefüllt [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen durch Aufrufen der [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f21b1-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="f21b1-113">Jede [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen in der Auflistung darstellt, entweder ein aktives Objekt auf dem Heap oder ein Objekt, das ist keines Objekt als Stamm, aber noch nicht vom Garbage Collector erfasst.</span><span class="sxs-lookup"><span data-stu-id="f21b1-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="f21b1-114">Die [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte in der Auflistung aufgelistet werden können, durch Aufrufen der [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f21b1-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f21b1-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f21b1-115">Requirements</span></span>  
 <span data-ttu-id="f21b1-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f21b1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f21b1-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f21b1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f21b1-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f21b1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f21b1-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f21b1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21b1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f21b1-120">See Also</span></span>  
 [<span data-ttu-id="f21b1-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f21b1-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
