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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40e518e3cf5967d2b0a7eda8c7b58ec0f918e219
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000609"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="fc6ca-102">ICorProfilerInfo3::GetFunctionTailcall3Info-Methode</span><span class="sxs-lookup"><span data-stu-id="fc6ca-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="fc6ca-103">Stellt den Stapelrahmen der Funktion, die dem Profiler von gemeldet wird, wird die [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="fc6ca-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="fc6ca-104">Diese Methode kann nur während des `FunctionTailcall3WithInfo`-Rückrufs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ca-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc6ca-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc6ca-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc6ca-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc6ca-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fc6ca-107">[in] Die `FunctionID` der Funktion, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fc6ca-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="fc6ca-108">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="fc6ca-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="fc6ca-109">Der Profiler sollte gleich bereitstellen `eltInfo` , wurde übergeben, um dem Profiler von der `FunctionTailcall3WithInfo` Funktion.</span><span class="sxs-lookup"><span data-stu-id="fc6ca-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="fc6ca-110">[out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="fc6ca-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="fc6ca-111">Dieses Handle ist nur während des `FunctionTailcall3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionTailcall3Info`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="fc6ca-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc6ca-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc6ca-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc6ca-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc6ca-113">Requirements</span></span>  
 <span data-ttu-id="fc6ca-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc6ca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc6ca-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc6ca-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc6ca-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc6ca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc6ca-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc6ca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6ca-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc6ca-118">See also</span></span>

- [<span data-ttu-id="fc6ca-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fc6ca-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="fc6ca-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fc6ca-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="fc6ca-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fc6ca-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="fc6ca-122">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc6ca-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="fc6ca-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fc6ca-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fc6ca-124">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="fc6ca-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
