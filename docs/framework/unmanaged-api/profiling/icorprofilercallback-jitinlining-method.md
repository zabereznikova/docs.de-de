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
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449901"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="e3a00-102">ICorProfilerCallback::JITInlining-Methode</span><span class="sxs-lookup"><span data-stu-id="e3a00-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="e3a00-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) eine Funktion in der Zeile mit einer anderen Funktion einfügen soll.</span><span class="sxs-lookup"><span data-stu-id="e3a00-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3a00-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3a00-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3a00-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="e3a00-106">in Die ID der Funktion, in die die `calleeId` Funktion eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e3a00-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="e3a00-107">in Die ID der Funktion, die eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3a00-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="e3a00-108">[out] `true`, damit die Einfügung erfolgen kann. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e3a00-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3a00-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3a00-109">Remarks</span></span>  
 <span data-ttu-id="e3a00-110">Der Profiler kann `pfShouldInline` auf `false` festlegen, um zu verhindern, dass die `calleeId` Funktion in die `callerId` Funktion eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e3a00-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="e3a00-111">Außerdem kann der Profiler die Inline Einfügung mit dem COR_PRF_DISABLE_INLINING Wert der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration global deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e3a00-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="e3a00-112">Inline-Funktionen, die Inline eingefügt werden, machen keine Ereignisse für die Eingabe oder den Abbruch</span><span class="sxs-lookup"><span data-stu-id="e3a00-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="e3a00-113">Daher muss der Profiler `pfShouldInline` auf `false` festlegen, um ein genaues CallGraph zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e3a00-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="e3a00-114">Wenn Sie `pfShouldInline` auf `false` festlegen, wirkt sich dies auf die Leistung aus, da die Inline Einfügung in der Regel die Geschwindigkeit erhöht und die Anzahl der separaten JIT-Kompilierungs Ereignisse für die</span><span class="sxs-lookup"><span data-stu-id="e3a00-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3a00-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e3a00-115">Requirements</span></span>  
 <span data-ttu-id="e3a00-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3a00-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3a00-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3a00-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3a00-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3a00-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3a00-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3a00-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a00-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3a00-120">See also</span></span>

- [<span data-ttu-id="e3a00-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3a00-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
