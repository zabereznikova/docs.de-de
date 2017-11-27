---
title: ICorProfilerCallback::ExceptionUnwindFunctionEnter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc41dc95776ca31178153402d2e145a3d2c13bf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="44da9-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="44da9-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="44da9-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung begonnen hat, eine Funktion zu entladen.</span><span class="sxs-lookup"><span data-stu-id="44da9-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44da9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44da9-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44da9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44da9-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="44da9-106">[in] Die ID der Funktion, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="44da9-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44da9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44da9-107">Remarks</span></span>  
 <span data-ttu-id="44da9-108">Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="44da9-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="44da9-109">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44da9-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="44da9-110">Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="44da9-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44da9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44da9-111">Requirements</span></span>  
 <span data-ttu-id="44da9-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44da9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44da9-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44da9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44da9-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44da9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44da9-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44da9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44da9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44da9-116">See Also</span></span>  
 [<span data-ttu-id="44da9-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44da9-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="44da9-118">ExceptionUnwindFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="44da9-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
