---
title: ICorDebugHeapSegmentEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138450"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="5d9ed-102">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d9ed-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="5d9ed-103">Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="5d9ed-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d9ed-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5d9ed-105">Methods</span></span>  
  
|<span data-ttu-id="5d9ed-106">Methode</span><span class="sxs-lookup"><span data-stu-id="5d9ed-106">Method</span></span>|<span data-ttu-id="5d9ed-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d9ed-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d9ed-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="5d9ed-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="5d9ed-109">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen ab, die Informationen zu Regionen des verwalteten Heaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d9ed-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d9ed-110">Remarks</span></span>  
 <span data-ttu-id="5d9ed-111">Die `ICorDebugHeapSegmentEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="5d9ed-112">Eine `ICorDebugHeapSegmentEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) -Methode mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="5d9ed-113">Die [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Objekte in der Auflistung können durch Aufrufen der [icordebugheapsegmenterum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="5d9ed-114">Ein `ICorDebugHeapSegmentEnum` Auflistungs Objekt listet alle Speicherbereiche auf, die verwaltete Objekte enthalten können, garantiert jedoch nicht, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="5d9ed-115">Sie kann Informationen über leere oder reservierte Speicherbereiche enthalten.</span><span class="sxs-lookup"><span data-stu-id="5d9ed-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d9ed-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d9ed-116">Requirements</span></span>  
 <span data-ttu-id="5d9ed-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d9ed-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d9ed-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d9ed-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d9ed-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d9ed-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d9ed-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d9ed-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9ed-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d9ed-121">See also</span></span>

- [<span data-ttu-id="5d9ed-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5d9ed-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
