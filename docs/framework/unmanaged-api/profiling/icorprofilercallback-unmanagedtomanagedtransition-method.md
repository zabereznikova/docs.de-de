---
title: ICorProfilerCallback::UnmanagedToManagedTransition-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6bd0c9796fa2c5d8eff8dfb9d3fa3f707ce4761
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453244"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="f9bfb-102">ICorProfilerCallback::UnmanagedToManagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="f9bfb-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="f9bfb-103">Benachrichtigt den Profiler, dass ein Übergang zwischen nicht verwaltetem Code zu verwaltetem Code aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f9bfb-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9bfb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9bfb-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9bfb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9bfb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f9bfb-106">[in] Die ID der Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f9bfb-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="f9bfb-107">[in] Der Wert der [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von nicht verwaltetem Code zu verwaltetem Code oder aufgrund einer Rückgabe von einer verwalteten Funktion aufgerufen wird, indem Sie eine verwaltete aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f9bfb-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9bfb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9bfb-108">Remarks</span></span>  
 <span data-ttu-id="f9bfb-109">Wenn der Wert der `reason` COR_PRF_TRANSITION_RETURN und `functionId` nicht null ist, ist die Funktion-ID ist, die nicht verwaltete Funktion und wird nie wurden kompiliert den Just-in-Time (JIT)-Compiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9bfb-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="f9bfb-110">Nicht verwaltete Funktionen haben einige grundlegende Informationen zugeordnet werden, z. B. einen Namen und einige Metadaten.</span><span class="sxs-lookup"><span data-stu-id="f9bfb-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="f9bfb-111">Wenn der Wert des `reason` COR_PRF_TRANSITION_CALL, ist es eventuell möglich, dass die aufgerufene Funktion (d. h. die verwaltete Funktion) noch kein JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="f9bfb-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9bfb-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9bfb-112">Requirements</span></span>  
 <span data-ttu-id="f9bfb-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9bfb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9bfb-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9bfb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9bfb-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9bfb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9bfb-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9bfb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bfb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9bfb-117">See Also</span></span>  
 [<span data-ttu-id="f9bfb-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9bfb-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f9bfb-119">ManagedToUnmanagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="f9bfb-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [<span data-ttu-id="f9bfb-120">Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)</span><span class="sxs-lookup"><span data-stu-id="f9bfb-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [<span data-ttu-id="f9bfb-121">Verwenden von C++-Interop (implizites PInvoke)</span><span class="sxs-lookup"><span data-stu-id="f9bfb-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
