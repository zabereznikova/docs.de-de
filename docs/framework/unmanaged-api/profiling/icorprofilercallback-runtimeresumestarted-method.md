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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fcc9d19a400e23d98a997d051c26af1c1084a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783024"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="c8e11-102">ICorProfilerCallback::RuntimeResumeStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="c8e11-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="c8e11-103">Benachrichtigt den Profiler, dass die Runtime alle Threads der Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c8e11-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8e11-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c8e11-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8e11-105">Requirements</span></span>  
 <span data-ttu-id="c8e11-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8e11-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8e11-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8e11-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8e11-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8e11-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8e11-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e11-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e11-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8e11-110">See also</span></span>

- [<span data-ttu-id="c8e11-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8e11-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c8e11-112">RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="c8e11-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
