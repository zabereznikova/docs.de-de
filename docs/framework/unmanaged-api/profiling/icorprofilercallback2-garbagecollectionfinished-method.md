---
title: ICorProfilerCallback2::GarbageCollectionFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
ms.openlocfilehash: 1217bb30be8b88f8ba1cf21f03f2531778358d4b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439842"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="ea814-102">ICorProfilerCallback2::GarbageCollectionFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="ea814-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="ea814-103">Benachrichtigt den Profiler, dass Garbage Collection abgeschlossen ist und alle Garbage Collection Rückrufe dafür ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="ea814-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea814-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea814-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ea814-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea814-105">Remarks</span></span>  
 <span data-ttu-id="ea814-106">Wenn die `GarbageCollectionFinished`-Methode aufgerufen wird, ist es für den Profiler sicher, Objekte an ihren endgültigen Speicherorten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ea814-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea814-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ea814-107">Requirements</span></span>  
 <span data-ttu-id="ea814-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea814-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea814-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea814-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea814-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea814-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea814-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea814-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea814-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea814-112">See also</span></span>

- [<span data-ttu-id="ea814-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea814-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ea814-114">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea814-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
