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
ms.openlocfilehash: 0a5a87c71bea603073c35dd851e443ca8c497523
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210435"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="502de-102">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="502de-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="502de-103">Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.</span><span class="sxs-lookup"><span data-stu-id="502de-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="502de-104">Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="502de-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="502de-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="502de-105">Methods</span></span>  
  
|<span data-ttu-id="502de-106">Methode</span><span class="sxs-lookup"><span data-stu-id="502de-106">Method</span></span>|<span data-ttu-id="502de-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="502de-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="502de-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="502de-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="502de-109">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen ab, die Informationen zu Regionen des verwalteten Heaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="502de-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="502de-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="502de-110">Remarks</span></span>  
 <span data-ttu-id="502de-111">Die `ICorDebugHeapSegmentEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="502de-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="502de-112">Eine `ICorDebugHeapSegmentEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheapregions](icordebugprocess5-enumerateheapregions-method.md) -Methode mit [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="502de-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="502de-113">Die [COR_HEAPOBJECT](cor-heapobject-structure.md) -Objekte in der-Auflistung können durch Aufrufen der [icordebugheapsegmenterum:: Next](icordebugheapsegmentenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="502de-113">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="502de-114">Ein `ICorDebugHeapSegmentEnum` Auflistungs Objekt listet alle Speicherbereiche auf, die verwaltete Objekte enthalten können, garantiert jedoch nicht, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden.</span><span class="sxs-lookup"><span data-stu-id="502de-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="502de-115">Sie kann Informationen über leere oder reservierte Speicherbereiche enthalten.</span><span class="sxs-lookup"><span data-stu-id="502de-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="502de-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="502de-116">Requirements</span></span>  
 <span data-ttu-id="502de-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="502de-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="502de-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="502de-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="502de-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="502de-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="502de-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="502de-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="502de-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="502de-121">See also</span></span>

- [<span data-ttu-id="502de-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="502de-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
