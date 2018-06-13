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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cac4ddc33bcaf07d615fd186a63d96b1f4f6464c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417731"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="02a93-102">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02a93-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="02a93-103">Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.</span><span class="sxs-lookup"><span data-stu-id="02a93-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="02a93-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="02a93-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02a93-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="02a93-105">Methods</span></span>  
  
|<span data-ttu-id="02a93-106">Methode</span><span class="sxs-lookup"><span data-stu-id="02a93-106">Method</span></span>|<span data-ttu-id="02a93-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02a93-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02a93-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="02a93-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="02a93-109">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu Regionen des verwalteten Heaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="02a93-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02a93-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02a93-110">Remarks</span></span>  
 <span data-ttu-id="02a93-111">Die `ICorDebugHeapSegmentEnum` Schnittstelle implementiert ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="02a93-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="02a93-112">Ein `ICorDebugHeapSegmentEnum` Instanz wird mit aufgefüllt [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen durch Aufrufen der [icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="02a93-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="02a93-113">Die [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte in der Auflistung aufgelistet werden können, durch Aufrufen der [icordebugheapsegmentenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="02a93-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="02a93-114">Ein `ICorDebugHeapSegmentEnum` Auflistungsobjekt Listet alle Speicherbereiche, die verwaltete Objekte enthalten können, aber es kann nicht garantiert, dass verwaltete Objekte eigentlich in dieser Regionen befinden.</span><span class="sxs-lookup"><span data-stu-id="02a93-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="02a93-115">Es kann Informationen zu Regionen leer oder reservierten Speicher enthalten.</span><span class="sxs-lookup"><span data-stu-id="02a93-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a93-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02a93-116">Requirements</span></span>  
 <span data-ttu-id="02a93-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02a93-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a93-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02a93-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02a93-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02a93-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02a93-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a93-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a93-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02a93-121">See Also</span></span>  
 [<span data-ttu-id="02a93-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="02a93-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
