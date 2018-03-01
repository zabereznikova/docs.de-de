---
title: ICorProfilerCallback2::GarbageCollectionFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ae517fcf9beb2205cf17177ed639ef0bd07adbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="52831-102">ICorProfilerCallback2::GarbageCollectionFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="52831-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="52831-103">Benachrichtigt den Profiler, dass Garbagecollection abgeschlossen und alle Garbage Collection-Rückrufe ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="52831-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52831-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52831-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="52831-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52831-105">Remarks</span></span>  
 <span data-ttu-id="52831-106">Ist für den Profiler zum Überprüfen von Objekten in ihren endgültigen Speicherorten sicher bei der `GarbageCollectionFinished` -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="52831-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52831-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52831-107">Requirements</span></span>  
 <span data-ttu-id="52831-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52831-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52831-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52831-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52831-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52831-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52831-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52831-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52831-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52831-112">See Also</span></span>  
 [<span data-ttu-id="52831-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52831-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="52831-114">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52831-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
