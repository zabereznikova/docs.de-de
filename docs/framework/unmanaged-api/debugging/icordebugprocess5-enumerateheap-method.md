---
title: ICorDebugProcess5::EnumerateHeap-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: 9386c77cc98df17d797d5886e1603ffc4824b6dc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205237"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="c2726-102">ICorDebugProcess5::EnumerateHeap-Methode</span><span class="sxs-lookup"><span data-stu-id="c2726-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="c2726-103">Ruft einen Enumerator für die Objekte im verwalteten Heap ab.</span><span class="sxs-lookup"><span data-stu-id="c2726-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2726-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2726-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2726-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2726-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="c2726-106">vorgenommen Ein Zeiger auf die Adresse eines [icordebugheapenum](icordebugheapenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Enumerator für die Objekte handelt, die sich auf dem verwalteten Heap befinden.</span><span class="sxs-lookup"><span data-stu-id="c2726-106">[out] A pointer to the address of an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2726-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2726-107">Remarks</span></span>  
 <span data-ttu-id="c2726-108">Bevor Sie die- `ICorDebugProcess5::EnumerateHeap` Methode aufrufen, sollten Sie die [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode aufrufen und den Wert des- `areGCStructuresValid` Felds des zurückgegebenen [COR_HEAPINFO](cor-heapinfo-structure.md) Objekts überprüfen, um sicherzustellen, dass der Garbage Collection Heap im aktuellen Zustand aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="c2726-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="c2726-109">Außerdem gibt den Wert `ICorDebugProcess5::EnumerateHeap` zurück `E_FAIL` , wenn Sie zu früh an der Lebensdauer des Prozesses anfügen, bevor der Speicher für den verwalteten Heap zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c2726-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="c2726-110">Das [icordebugheapenum](icordebugheapenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der ICorDebugEnum-Schnittstelle abgeleitet wird und die es Ihnen ermöglicht, [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekte aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="c2726-110">The [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="c2726-111">Diese Methode füllt das [icordebugheapenum](icordebugheapenum-interface.md) -Auflistungs Objekt mit [COR_HEAPOBJECT](cor-heapobject-structure.md) -Instanzen auf, die Informationen zu allen Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c2726-111">This method populates the [ICorDebugHeapEnum](icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="c2726-112">Die Auflistung kann auch [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen enthalten, die Informationen zu Objekten bereitstellen, die nicht von einem Objekt stammen, aber noch nicht vom Garbage Collector erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c2726-112">The collection may also include [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2726-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c2726-113">Requirements</span></span>  
 <span data-ttu-id="c2726-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2726-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2726-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2726-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2726-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2726-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2726-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2726-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2726-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2726-118">See also</span></span>

- [<span data-ttu-id="c2726-119">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2726-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="c2726-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c2726-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
