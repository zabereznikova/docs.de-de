---
title: ICorProfilerCallback::ExceptionOSHandlerEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: b3088308e75fb7cbffcc439ab4440255ed0fb2b9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444912"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="d681b-102">ICorProfilerCallback::ExceptionOSHandlerEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="d681b-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="d681b-103">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="d681b-103">Not implemented.</span></span> <span data-ttu-id="d681b-104">Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.</span><span class="sxs-lookup"><span data-stu-id="d681b-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d681b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d681b-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d681b-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d681b-106">Requirements</span></span>  
 <span data-ttu-id="d681b-107">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d681b-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d681b-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d681b-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d681b-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d681b-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d681b-110">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d681b-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d681b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d681b-111">See also</span></span>

- [<span data-ttu-id="d681b-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d681b-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
