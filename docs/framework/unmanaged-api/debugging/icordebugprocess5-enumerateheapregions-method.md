---
title: ICorDebugProcess5::EnumerateHeapRegions-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9340977c55c54b9a4683115000293d1c98dfcf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767456"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="1c930-102">ICorDebugProcess5::EnumerateHeapRegions-Methode</span><span class="sxs-lookup"><span data-stu-id="1c930-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="1c930-103">Ruft einen Enumerator für die Speicherbereiche des verwalteten Heaps ab.</span><span class="sxs-lookup"><span data-stu-id="1c930-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c930-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c930-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c930-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c930-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="1c930-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) Schnittstellenobjekts, das ein Enumerator für die Bereiche des Arbeitsspeichers ist in der Objekte befinden sich im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="1c930-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c930-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c930-107">Remarks</span></span>  
 <span data-ttu-id="1c930-108">Vor dem Aufruf der `ICorDebugProcess5::EnumerateHeapRegions` -Methode, die Sie aufrufen sollten die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode, und untersuchen Sie den Wert des der `areGCStructuresValid` Feld des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Objekt, um sicherzustellen, dass die Garbage Collection-Heap im aktuellen Zustand aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="1c930-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="1c930-109">Darüber hinaus die `ICorDebugProcess5::EnumerateHeapRegions` Methodenrückgabe `E_FAIL` Wenn Sie zu früh während der Lebensdauer des Prozesses anfügen, bevor Speicher Regionen werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="1c930-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="1c930-110">Diese Methode ist garantiert, alle Speicherbereiche aufzulisten, die verwaltete Objekten enthalten kann, aber dies garantiert nicht, dass verwaltete Objekte tatsächlich in diesen Regionen befinden.</span><span class="sxs-lookup"><span data-stu-id="1c930-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="1c930-111">Die [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) Auflistungsobjekt kann leer oder Reservierter Arbeitsspeicher Regionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1c930-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="1c930-112">Die [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) -Schnittstellenobjekt wird einen Standardenumerator, die von der ICorDebugEnum-Schnittstelle, die Sie zum Aufzählen kann abgeleitet [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="1c930-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="1c930-113">Jede [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) -Objekt stellt Informationen über den Arbeitsspeicherbereich von einem bestimmten Segment, sowie die Generation der Objekte in diesem Segment.</span><span class="sxs-lookup"><span data-stu-id="1c930-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c930-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c930-114">Requirements</span></span>  
 <span data-ttu-id="1c930-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c930-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c930-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c930-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c930-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c930-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c930-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c930-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c930-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c930-119">See also</span></span>

- [<span data-ttu-id="1c930-120">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c930-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="1c930-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1c930-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
