---
title: ICorProfilerCallback::RuntimeSuspendAborted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendAborted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2d1c181a471763ea0220c081d64af915ca6be149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="ab55d-102">ICorProfilerCallback::RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="ab55d-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="ab55d-103">Benachrichtigt den Profiler, dass die Common Language Runtime die Runtime-Unterbrechung abgebrochen wurde, die aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ab55d-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab55d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab55d-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ab55d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab55d-105">Remarks</span></span>  
 <span data-ttu-id="ab55d-106">Die Unterbrechung zur Laufzeit möglicherweise abgebrochen werden, wenn zwei Threads gleichzeitig, zum Anhalten der Laufzeit versuchen.</span><span class="sxs-lookup"><span data-stu-id="ab55d-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="ab55d-107">Entweder die [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) Rückruf oder `RuntimeSuspendAborted` Rückruf auf einem einzelnen Thread folgenden erfolgt eine [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="ab55d-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="ab55d-108">Die `RuntimeSuspendAborted` ist gewährleistet, dass Rückruf auftreten, auf dem gleichen Thread wie der `RuntimeSuspendStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="ab55d-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab55d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab55d-109">Requirements</span></span>  
 <span data-ttu-id="ab55d-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab55d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab55d-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab55d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab55d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab55d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab55d-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab55d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab55d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab55d-114">See Also</span></span>  
 [<span data-ttu-id="ab55d-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab55d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
