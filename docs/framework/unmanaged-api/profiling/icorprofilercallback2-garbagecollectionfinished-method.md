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
ms.openlocfilehash: 47f25dbb1f88dbf580b096246016cd46f2d0d89c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499824"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="b150e-102">ICorProfilerCallback2::GarbageCollectionFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="b150e-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="b150e-103">Benachrichtigt den Profiler, dass Garbage Collection abgeschlossen ist und alle Garbage Collection Rückrufe dafür ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="b150e-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b150e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b150e-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b150e-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b150e-105">Remarks</span></span>  
 <span data-ttu-id="b150e-106">Wenn die-Methode aufgerufen wird, ist es für den Profiler sicher, Objekte an ihren endgültigen Speicherorten zu überprüfen `GarbageCollectionFinished` .</span><span class="sxs-lookup"><span data-stu-id="b150e-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b150e-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b150e-107">Requirements</span></span>  
 <span data-ttu-id="b150e-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b150e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b150e-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b150e-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b150e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b150e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b150e-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b150e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b150e-112">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b150e-112">See also</span></span>

- [<span data-ttu-id="b150e-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b150e-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b150e-114">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b150e-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
