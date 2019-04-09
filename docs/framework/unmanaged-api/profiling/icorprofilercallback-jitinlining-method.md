---
title: ICorProfilerCallback::JITInlining-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60183291fda551e328ee1def03c02240314a71e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178268"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="5a530-102">ICorProfilerCallback::JITInlining-Methode</span><span class="sxs-lookup"><span data-stu-id="5a530-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="5a530-103">Benachrichtigt den Profiler, dass der just-in-Time (JIT)-Compiler zum Einfügen einer Funktion mit einer anderen Funktion.</span><span class="sxs-lookup"><span data-stu-id="5a530-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a530-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a530-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a530-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a530-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="5a530-106">[in] Die ID der Funktion, in dem die `calleeId` Funktion eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a530-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="5a530-107">[in] Die ID der Funktion eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a530-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="5a530-108">[out] `true` können die Einfügung auftritt; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5a530-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a530-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a530-109">Remarks</span></span>  
 <span data-ttu-id="5a530-110">Der Profiler kann festlegen `pfShouldInline` zu `false` um zu verhindern, dass die `calleeId` Funktion eingefügt wird, in der `callerId` Funktion.</span><span class="sxs-lookup"><span data-stu-id="5a530-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="5a530-111">Darüber hinaus der Profiler kann global deaktivieren, Inline-Einfügung COR_PRF_DISABLE_INLINING-Wert, der mit der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5a530-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="5a530-112">Inlinefunktionen eingefügt lösen keine Ereignisse für wechselt oder diesen verlässt.</span><span class="sxs-lookup"><span data-stu-id="5a530-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="5a530-113">Aus diesem Grund muss der Profiler festgelegt `pfShouldInline` zu `false` um ein genaues Aufrufdiagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a530-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="5a530-114">Festlegen von `pfShouldInline` zu `false` wird die Leistung beeinträchtigen, da Inline-Einfügung in der Regel die Geschwindigkeit erhöht und die Anzahl der separate Ereignisse der JIT-Kompilierung für die inserted-Methode verringert.</span><span class="sxs-lookup"><span data-stu-id="5a530-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a530-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a530-115">Requirements</span></span>  
 <span data-ttu-id="5a530-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a530-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a530-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a530-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a530-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a530-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5a530-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5a530-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a530-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a530-120">See also</span></span>

- [<span data-ttu-id="5a530-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a530-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
