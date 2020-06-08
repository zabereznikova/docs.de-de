---
title: ICorProfilerInfo3::GetFunctionLeave3Info-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
ms.openlocfilehash: bab52d9179d7454cab4a47e1a2bfe80a49b00c2a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502833"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="19947-102">ICorProfilerInfo3::GetFunctionLeave3Info-Methode</span><span class="sxs-lookup"><span data-stu-id="19947-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="19947-103">Stellt den Stapel Rahmen und den Rückgabewert der Funktion bereit, die dem Profiler von der FunctionLeave3WithInfo- [Funktions](functionleave3withinfo-function.md) Funktion gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="19947-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="19947-104">Diese Methode kann nur während des `FunctionLeave3WithInfo`-Rückrufs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="19947-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19947-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="19947-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19947-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="19947-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="19947-107">in Der der `FunctionID` Funktion, die zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="19947-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="19947-108">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="19947-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="19947-109">Der Profiler sollte die gleiche bereitstellen `eltInfo` , die dem Profiler von der [FunctionLeave3WithInfo](functionleave3withinfo-function.md) -Funktion übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="19947-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="19947-110">[out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="19947-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="19947-111">Dieses Handle ist nur während des `FunctionLeave3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionLeave3Info`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="19947-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="19947-112">vorgenommen Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) Struktur, die den Wert enthält, der von der Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="19947-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="19947-113">Für den Zugriff auf Rückgabewert Informationen `COR_PRF_ENABLE_FUNCTION_RETVAL` muss das-Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="19947-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="19947-114">Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen.</span><span class="sxs-lookup"><span data-stu-id="19947-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19947-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="19947-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19947-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19947-116">Requirements</span></span>  
 <span data-ttu-id="19947-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19947-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19947-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19947-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19947-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19947-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19947-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19947-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19947-121">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="19947-121">See also</span></span>

- [<span data-ttu-id="19947-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="19947-122">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="19947-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="19947-123">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="19947-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="19947-124">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="19947-125">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19947-125">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="19947-126">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="19947-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="19947-127">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="19947-127">Profiling</span></span>](index.md)
