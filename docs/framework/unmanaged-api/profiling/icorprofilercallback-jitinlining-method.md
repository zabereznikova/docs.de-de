---
title: ICorProfilerCallback::JITInlining-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1e729a17101bbe9c659be729c685909932b5456
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="e852a-102">ICorProfilerCallback::JITInlining-Methode</span><span class="sxs-lookup"><span data-stu-id="e852a-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="e852a-103">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler umgehend eine Funktion mit einer anderen Funktion einfügen.</span><span class="sxs-lookup"><span data-stu-id="e852a-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e852a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e852a-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e852a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e852a-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="e852a-106">[in] Die ID der Funktion, in dem die `calleeId` Funktion eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e852a-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="e852a-107">[in] Die ID der Funktion, die eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e852a-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="e852a-108">[out] `true` ermöglichen das Einfügen erfolgen; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e852a-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e852a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e852a-109">Remarks</span></span>  
 <span data-ttu-id="e852a-110">Der Profiler kann festlegen, `pfShouldInline` auf `false` um zu verhindern, dass die `calleeId` Funktion eingefügt wird, in der `callerId` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e852a-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="e852a-111">Darüber hinaus der Profiler kann global Inline-Einfügung mit deaktivieren COR_PRF_DISABLE_INLINING-Wert, der die [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e852a-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="e852a-112">Inline eingefügte Funktionen lösen keine Ereignisse für die Eingabe oder verlassen.</span><span class="sxs-lookup"><span data-stu-id="e852a-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="e852a-113">Aus diesem Grund muss der Profiler festgelegt `pfShouldInline` auf `false` ein genaues Aufrufdiagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e852a-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="e852a-114">Festlegen von `pfShouldInline` auf `false` beeinflusst die Leistung, da die Inline-Einfügung in der Regel wird die Geschwindigkeit erhöht und reduziert die Anzahl der separate Ereignisse der JIT-Kompilierung für die inserted-Methode.</span><span class="sxs-lookup"><span data-stu-id="e852a-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e852a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e852a-115">Requirements</span></span>  
 <span data-ttu-id="e852a-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e852a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e852a-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e852a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e852a-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e852a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e852a-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e852a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e852a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e852a-120">See Also</span></span>  
 [<span data-ttu-id="e852a-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e852a-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
