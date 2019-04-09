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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f613842c12b50b8a58aac1b71bf2f3c53aaf961f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231096"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="2c7da-102">ICorProfilerCallback2::GarbageCollectionFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="2c7da-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="2c7da-103">Benachrichtigt den Profiler, Garbagecollection abgeschlossen und alle Garbage Collection-Rückrufe ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="2c7da-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c7da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c7da-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2c7da-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c7da-105">Remarks</span></span>  
 <span data-ttu-id="2c7da-106">Es ist sicher für den Profiler, um Objekte in die endgültigen Speicherorte zu überprüfen bei der `GarbageCollectionFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c7da-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c7da-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c7da-107">Requirements</span></span>  
 <span data-ttu-id="2c7da-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c7da-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c7da-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c7da-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c7da-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c7da-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2c7da-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2c7da-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2c7da-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c7da-112">See also</span></span>

- [<span data-ttu-id="2c7da-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c7da-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2c7da-114">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c7da-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
