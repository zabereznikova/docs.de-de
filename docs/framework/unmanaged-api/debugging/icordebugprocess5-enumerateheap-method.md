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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d080145ac63882e04412b44c34d040a75746243
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767527"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="4f5c6-102">ICorDebugProcess5::EnumerateHeap-Methode</span><span class="sxs-lookup"><span data-stu-id="4f5c6-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="4f5c6-103">Ruft einen Enumerator für die Objekte ab, auf dem verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="4f5c6-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f5c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f5c6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f5c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f5c6-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="4f5c6-106">[out] Ein Zeiger auf die Adresse des ein [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das einen Enumerator für die Objekte, die auf dem verwalteten Heap gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4f5c6-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f5c6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f5c6-107">Remarks</span></span>  
 <span data-ttu-id="4f5c6-108">Vor dem Aufruf der `ICorDebugProcess5::EnumerateHeap` -Methode, die Sie aufrufen sollten die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode, und untersuchen Sie den Wert des der `areGCStructuresValid` Feld des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Objekt, um sicherzustellen, dass die Garbage Collection-Heap im aktuellen Zustand aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="4f5c6-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="4f5c6-109">Darüber hinaus die `ICorDebugProcess5::EnumerateHeap` gibt `E_FAIL` Wenn Sie zu früh während der Lebensdauer des Prozesses, bevor Speicher anfügen, für der verwaltete Heap zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4f5c6-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="4f5c6-110">Die [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Schnittstellenobjekt wird einen Standardenumerator, die von der ICorDebugEnum-Schnittstelle, die Sie zum Aufzählen kann abgeleitet [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="4f5c6-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="4f5c6-111">Diese Methode füllt den [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Auflistungsobjekts mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu allen Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4f5c6-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="4f5c6-112">Die Auflistung kann auch enthalten [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen, die Informationen über Objekte bereitzustellen, die nicht von einem Stamm verfügen Objekt aber noch nicht vom Garbage Collector erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="4f5c6-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f5c6-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f5c6-113">Requirements</span></span>  
 <span data-ttu-id="4f5c6-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f5c6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f5c6-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f5c6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f5c6-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f5c6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f5c6-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f5c6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f5c6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f5c6-118">See also</span></span>

- [<span data-ttu-id="4f5c6-119">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f5c6-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="4f5c6-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f5c6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
