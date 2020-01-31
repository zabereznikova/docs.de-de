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
ms.openlocfilehash: 3e13b17fb03530730a78f6889309f1993419574b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866211"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="ad74c-102">ICorProfilerCallback::JITInlining-Methode</span><span class="sxs-lookup"><span data-stu-id="ad74c-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="ad74c-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) eine Funktion in der Zeile mit einer anderen Funktion einfügen soll.</span><span class="sxs-lookup"><span data-stu-id="ad74c-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad74c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad74c-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad74c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ad74c-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="ad74c-106">in Die ID der Funktion, in die die `calleeId` Funktion eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ad74c-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="ad74c-107">in Die ID der Funktion, die eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad74c-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="ad74c-108">[out] `true`, damit die Einfügung erfolgen kann. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="ad74c-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad74c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad74c-109">Remarks</span></span>  
 <span data-ttu-id="ad74c-110">Der Profiler kann `pfShouldInline` auf `false` festlegen, um zu verhindern, dass die `calleeId` Funktion in die `callerId` Funktion eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ad74c-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="ad74c-111">Außerdem kann der Profiler die Inline Einfügung mit dem COR_PRF_DISABLE_INLINING Wert der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration global deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ad74c-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="ad74c-112">Inline-Funktionen, die Inline eingefügt werden, machen keine Ereignisse für die Eingabe oder den Abbruch</span><span class="sxs-lookup"><span data-stu-id="ad74c-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="ad74c-113">Daher muss der Profiler `pfShouldInline` auf `false` festlegen, um ein genaues CallGraph zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ad74c-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="ad74c-114">Wenn Sie `pfShouldInline` auf `false` festlegen, wirkt sich dies auf die Leistung aus, da die Inline Einfügung in der Regel die Geschwindigkeit erhöht und die Anzahl der separaten JIT-Kompilierungs Ereignisse für die</span><span class="sxs-lookup"><span data-stu-id="ad74c-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad74c-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad74c-115">Requirements</span></span>  
 <span data-ttu-id="ad74c-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad74c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad74c-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad74c-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad74c-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad74c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad74c-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad74c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad74c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad74c-120">See also</span></span>

- [<span data-ttu-id="ad74c-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad74c-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
