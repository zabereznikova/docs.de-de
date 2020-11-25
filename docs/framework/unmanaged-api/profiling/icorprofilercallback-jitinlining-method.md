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
ms.openlocfilehash: cf68594620b24f2a5823aa423c5911f2d9d6b328
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725494"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="fa873-102">ICorProfilerCallback::JITInlining-Methode</span><span class="sxs-lookup"><span data-stu-id="fa873-102">ICorProfilerCallback::JITInlining Method</span></span>

<span data-ttu-id="fa873-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) eine Funktion in der Zeile mit einer anderen Funktion einfügen soll.</span><span class="sxs-lookup"><span data-stu-id="fa873-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa873-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa873-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa873-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa873-105">Parameters</span></span>  

 `callerId`  
 <span data-ttu-id="fa873-106">in Die ID der Funktion, in die die `calleeId` Funktion eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fa873-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="fa873-107">in Die ID der Funktion, die eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa873-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="fa873-108">[out] `true` , um das Einfügen zuzulassen. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="fa873-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa873-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa873-109">Remarks</span></span>  

 <span data-ttu-id="fa873-110">Der Profiler kann `pfShouldInline` auf festlegen `false` , um zu verhindern, `calleeId` dass die Funktion in die Funktion eingefügt wird `callerId` .</span><span class="sxs-lookup"><span data-stu-id="fa873-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="fa873-111">Außerdem kann der Profiler die Inline Einfügung mit dem COR_PRF_DISABLE_INLINING Wert der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration global deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa873-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="fa873-112">Inline-Funktionen, die Inline eingefügt werden, machen keine Ereignisse für die Eingabe oder den Abbruch</span><span class="sxs-lookup"><span data-stu-id="fa873-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="fa873-113">Daher muss der Profiler auf festlegen, um `pfShouldInline` `false` ein genaues CallGraph zu generieren.</span><span class="sxs-lookup"><span data-stu-id="fa873-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="fa873-114">`pfShouldInline`Wenn Sie auf festlegen `false` , wirkt sich dies auf die Leistung aus, da die Inline Einfügung normalerweise die Geschwindigkeit erhöht und die Anzahl der separaten JIT-Kompilierungs Ereignisse für die</span><span class="sxs-lookup"><span data-stu-id="fa873-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa873-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fa873-115">Requirements</span></span>  

 <span data-ttu-id="fa873-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa873-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa873-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa873-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa873-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa873-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa873-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa873-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa873-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa873-120">See also</span></span>

- [<span data-ttu-id="fa873-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa873-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
