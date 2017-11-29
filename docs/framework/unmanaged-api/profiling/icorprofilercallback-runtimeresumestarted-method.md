---
title: ICorProfilerCallback::RuntimeResumeStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeResumeStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf63dd0882784750747a3fe5a68bb8dd432c4a78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="9272a-102">ICorProfilerCallback::RuntimeResumeStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="9272a-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="9272a-103">Benachrichtigt den Profiler, dass die Common Language Runtime alle zur Laufzeit Threads fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="9272a-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9272a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9272a-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="9272a-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9272a-105">Requirements</span></span>  
 <span data-ttu-id="9272a-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9272a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9272a-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9272a-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9272a-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9272a-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9272a-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9272a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9272a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9272a-110">See Also</span></span>  
 [<span data-ttu-id="9272a-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9272a-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9272a-112">RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="9272a-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
