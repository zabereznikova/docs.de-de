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
ms.openlocfilehash: 9a283d305c1a19112574cbf3486b1c67e64ed24c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717240"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="31fc7-102">ICorProfilerCallback::RuntimeResumeStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="31fc7-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>

<span data-ttu-id="31fc7-103">Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="31fc7-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31fc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31fc7-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="31fc7-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="31fc7-105">Requirements</span></span>  

 <span data-ttu-id="31fc7-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31fc7-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31fc7-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31fc7-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31fc7-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31fc7-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31fc7-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31fc7-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fc7-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31fc7-110">See also</span></span>

- [<span data-ttu-id="31fc7-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31fc7-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="31fc7-112">RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="31fc7-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
