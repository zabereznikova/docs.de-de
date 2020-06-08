---
title: ICorProfilerCallback::RuntimeResumeStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
ms.openlocfilehash: 08e76e295e30ede48733ab35870ec965eb157f60
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499869"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="0c062-102">ICorProfilerCallback::RuntimeResumeStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="0c062-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="0c062-103">Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="0c062-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c062-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c062-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="0c062-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0c062-105">Requirements</span></span>  
 <span data-ttu-id="0c062-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c062-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c062-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c062-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c062-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c062-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c062-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c062-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c062-110">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="0c062-110">See also</span></span>

- [<span data-ttu-id="0c062-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c062-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0c062-112">RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="0c062-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
