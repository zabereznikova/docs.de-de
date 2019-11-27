---
title: ICorProfilerCallback::ExceptionOSHandlerLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
ms.openlocfilehash: e54f87f5f02a1857fd9b7639d00d4bcb976665b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445404"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="5da33-102">ICorProfilerCallback::ExceptionOSHandlerLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="5da33-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="5da33-103">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="5da33-103">Not implemented.</span></span> <span data-ttu-id="5da33-104">Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.</span><span class="sxs-lookup"><span data-stu-id="5da33-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5da33-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5da33-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5da33-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5da33-106">Requirements</span></span>  
 <span data-ttu-id="5da33-107">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5da33-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da33-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5da33-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5da33-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5da33-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5da33-110">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da33-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da33-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5da33-111">See also</span></span>

- [<span data-ttu-id="5da33-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5da33-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
