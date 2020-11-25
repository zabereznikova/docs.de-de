---
title: ICorProfilerInfo3::GetFunctionTailcall3Info-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: 27bbb1aac376866be7458a3737af9d89bf761411
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721609"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="754de-102">ICorProfilerInfo3::GetFunctionTailcall3Info-Methode</span><span class="sxs-lookup"><span data-stu-id="754de-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>

<span data-ttu-id="754de-103">Stellt den Stapel Rahmen der Funktion bereit, die dem Profiler von der [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Funktion gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="754de-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="754de-104">Diese Methode kann nur während des `FunctionTailcall3WithInfo`-Rückrufs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="754de-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754de-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="754de-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="754de-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="754de-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="754de-107">in Der der `FunctionID` Funktion, die zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="754de-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="754de-108">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="754de-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="754de-109">Der Profiler sollte die gleiche bereitstellen `eltInfo` , die dem Profiler von der- `FunctionTailcall3WithInfo` Funktion gegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="754de-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="754de-110">[out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="754de-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="754de-111">Dieses Handle ist nur während des `FunctionTailcall3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionTailcall3Info`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="754de-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="754de-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="754de-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="754de-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="754de-113">Requirements</span></span>  

 <span data-ttu-id="754de-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="754de-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754de-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="754de-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="754de-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="754de-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="754de-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754de-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="754de-118">See also</span></span>

- [<span data-ttu-id="754de-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="754de-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="754de-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="754de-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="754de-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="754de-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="754de-122">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="754de-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="754de-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="754de-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="754de-124">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="754de-124">Profiling</span></span>](index.md)
