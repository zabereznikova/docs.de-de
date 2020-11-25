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
ms.openlocfilehash: 42126d15c64175f35bba89a1ab6abacc64128012
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704629"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="6a183-102">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a183-102">ICorDebugHeapSegmentEnum Interface</span></span>

<span data-ttu-id="6a183-103">Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.</span><span class="sxs-lookup"><span data-stu-id="6a183-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="6a183-104">Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6a183-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a183-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6a183-105">Methods</span></span>  
  
|<span data-ttu-id="6a183-106">Methode</span><span class="sxs-lookup"><span data-stu-id="6a183-106">Method</span></span>|<span data-ttu-id="6a183-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a183-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a183-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="6a183-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="6a183-109">Ruft die angegebene Anzahl von [COR_SEGMENT](cor-segment-structure.md) Instanzen ab, die Informationen zu Regionen des verwalteten Heaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a183-109">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a183-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a183-110">Remarks</span></span>  

 <span data-ttu-id="6a183-111">Die `ICorDebugHeapSegmentEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6a183-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="6a183-112">Eine `ICorDebugHeapSegmentEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheapregions](icordebugprocess5-enumerateheapregions-method.md) -Methode mit [COR_SEGMENT](cor-segment-structure.md) Instanzen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="6a183-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_SEGMENT](cor-segment-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="6a183-113">Die [COR_SEGMENT](cor-segment-structure.md) -Objekte in der-Auflistung können durch Aufrufen der [icordebugheapsegmenterum:: Next](icordebugheapsegmentenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="6a183-113">The [COR_SEGMENT](cor-segment-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="6a183-114">Ein `ICorDebugHeapSegmentEnum` Auflistungs Objekt listet alle Speicherbereiche auf, die verwaltete Objekte enthalten können, garantiert jedoch nicht, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden.</span><span class="sxs-lookup"><span data-stu-id="6a183-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="6a183-115">Sie kann Informationen über leere oder reservierte Speicherbereiche enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a183-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a183-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6a183-116">Requirements</span></span>  

 <span data-ttu-id="6a183-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a183-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a183-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a183-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a183-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a183-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a183-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a183-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a183-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a183-121">See also</span></span>

- [<span data-ttu-id="6a183-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6a183-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
