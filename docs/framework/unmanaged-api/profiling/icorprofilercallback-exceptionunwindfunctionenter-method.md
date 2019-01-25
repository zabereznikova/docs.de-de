---
title: ICorProfilerCallback::ExceptionUnwindFunctionEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3184b0b3bc03aa300832211b52e40f2f2f2988a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678641"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="61f0b-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="61f0b-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="61f0b-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung begonnen hat, eine Funktion zu entladen.</span><span class="sxs-lookup"><span data-stu-id="61f0b-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f0b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61f0b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61f0b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61f0b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="61f0b-106">[in] Die ID der Funktion, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="61f0b-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61f0b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61f0b-107">Remarks</span></span>  
 <span data-ttu-id="61f0b-108">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="61f0b-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="61f0b-109">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="61f0b-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="61f0b-110">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="61f0b-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61f0b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61f0b-111">Requirements</span></span>  
 <span data-ttu-id="61f0b-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61f0b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61f0b-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="61f0b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="61f0b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61f0b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61f0b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61f0b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f0b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61f0b-116">See also</span></span>
- [<span data-ttu-id="61f0b-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61f0b-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="61f0b-118">ExceptionUnwindFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="61f0b-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
