---
title: ICorDebugProcess5::EnumerateHeap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fabe3d70b493427f3845b5752946b00097c1e78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="9e36e-102">ICorDebugProcess5::EnumerateHeap-Methode</span><span class="sxs-lookup"><span data-stu-id="9e36e-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="9e36e-103">Ruft einen Enumerator für die Objekte im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="9e36e-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e36e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e36e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e36e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e36e-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="9e36e-106">[out] Ein Zeiger auf die Adresse des ein [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das einen Enumerator für die Objekte, die auf dem verwalteten Heap gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="9e36e-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e36e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e36e-107">Remarks</span></span>  
 <span data-ttu-id="9e36e-108">Vor dem Aufruf der `ICorDebugProcess5::EnumerateHeap` -Methode, die Sie aufrufen sollte die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode und überprüfen Sie den Wert von der `areGCStructuresValid` Feld des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Objekt, um sicherzustellen, dass die Garbage Collection-Heap in seinem aktuellen Status aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="9e36e-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="9e36e-109">Darüber hinaus die `ICorDebugProcess5::EnumerateHeap` gibt `E_FAIL` , wenn Sie zu früh in der Lebensdauer des Prozesses, bevor Speicher anfügen, für der verwaltete Heap zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e36e-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="9e36e-110">Die [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Schnittstellenobjekt ist eine standard-Enumerator ICorDebugEnum-Schnittstelle, die Ihnen ermöglicht, Auflisten von abgeleitet [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="9e36e-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="9e36e-111">Diese Methode füllt die [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Auflistungsobjekts mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu allen Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9e36e-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="9e36e-112">Die Auflistung kann außerdem enthalten [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen über Objekte bereitzustellen, die von einer nicht als Stammelement werden-Objekt jedoch noch nicht vom Garbage Collector erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="9e36e-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e36e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e36e-113">Requirements</span></span>  
 <span data-ttu-id="9e36e-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e36e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e36e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e36e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e36e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e36e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e36e-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e36e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e36e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e36e-118">See Also</span></span>  
 [<span data-ttu-id="9e36e-119">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e36e-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="9e36e-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9e36e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
