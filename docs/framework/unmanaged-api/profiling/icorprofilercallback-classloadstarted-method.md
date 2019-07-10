---
title: ICorProfilerCallback::ClassLoadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84ff6cb79abdb60a3c01c66580ed6fc10f6c137e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762935"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="6c863-102">ICorProfilerCallback::ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="6c863-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="6c863-103">Benachrichtigt den Profiler, dass eine Klasse geladen wird.</span><span class="sxs-lookup"><span data-stu-id="6c863-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c863-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c863-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c863-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c863-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6c863-106">[in] Identifiziert die Klasse, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="6c863-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c863-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c863-107">Remarks</span></span>  
 <span data-ttu-id="6c863-108">Der Wert des `classId` gilt nicht für eine Anforderung von Informationen bis der [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6c863-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c863-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c863-109">Requirements</span></span>  
 <span data-ttu-id="6c863-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c863-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c863-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c863-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c863-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c863-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c863-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c863-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c863-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c863-114">See also</span></span>

- [<span data-ttu-id="6c863-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c863-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
