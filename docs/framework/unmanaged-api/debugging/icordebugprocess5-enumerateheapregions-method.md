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
ms.openlocfilehash: 8070b0693b5718ad8b4cbeb9bf5792cb7f4a0a85
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792406"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="fffa4-102">ICorDebugProcess5::EnumerateHeapRegions-Methode</span><span class="sxs-lookup"><span data-stu-id="fffa4-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="fffa4-103">Ruft einen Enumerator für die Speicherbereiche des verwalteten Heaps ab.</span><span class="sxs-lookup"><span data-stu-id="fffa4-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fffa4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fffa4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fffa4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="fffa4-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="fffa4-106">vorgenommen Ein Zeiger auf die Adresse eines [icordebugheapsegmentenum](icordebugheapsegmentenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Enumerator für die Speicherbereiche handelt, in denen-Objekte im verwalteten Heap gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="fffa4-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fffa4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fffa4-107">Remarks</span></span>  
 <span data-ttu-id="fffa4-108">Bevor Sie die `ICorDebugProcess5::EnumerateHeapRegions`-Methode aufrufen, sollten Sie die [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode aufrufen und den Wert des `areGCStructuresValid` Felds des zurückgegebenen [COR_HEAPINFO](cor-heapinfo-structure.md) Objekts überprüfen, um sicherzustellen, dass der Garbage Collection Heap im aktuellen Zustand aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="fffa4-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="fffa4-109">Außerdem gibt die `ICorDebugProcess5::EnumerateHeapRegions`-Methode `E_FAIL` zurück, wenn Sie die Lebensdauer des Prozesses zu früh anfügen, bevor Speicherbereiche erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fffa4-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="fffa4-110">Mit dieser Methode werden alle Speicherbereiche aufgelistet, die möglicherweise verwaltete Objekte enthalten, aber es wird nicht garantiert, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden.</span><span class="sxs-lookup"><span data-stu-id="fffa4-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="fffa4-111">Das [icordebugheapsegmentenum](icordebugheapsegmentenum-interface.md) -Auflistungs Objekt kann leere oder reservierte Speicherbereiche enthalten.</span><span class="sxs-lookup"><span data-stu-id="fffa4-111">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="fffa4-112">Das [icordebugheapsegmentenum](icordebugheapsegmentenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der ICorDebugEnum-Schnittstelle abgeleitet wird, die es Ihnen ermöglicht, [COR_SEGMENT](cor-segment-structure.md) Objekte aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="fffa4-112">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](cor-segment-structure.md) objects.</span></span> <span data-ttu-id="fffa4-113">Jedes [COR_SEGMENT](cor-segment-structure.md) Objekt stellt Informationen zum Speicherbereich eines bestimmten Segments zusammen mit der Generierung der Objekte in diesem Segment bereit.</span><span class="sxs-lookup"><span data-stu-id="fffa4-113">Each [COR_SEGMENT](cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fffa4-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fffa4-114">Requirements</span></span>  
 <span data-ttu-id="fffa4-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fffa4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fffa4-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fffa4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fffa4-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fffa4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fffa4-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fffa4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fffa4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fffa4-119">See also</span></span>

- [<span data-ttu-id="fffa4-120">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fffa4-120">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="fffa4-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fffa4-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
