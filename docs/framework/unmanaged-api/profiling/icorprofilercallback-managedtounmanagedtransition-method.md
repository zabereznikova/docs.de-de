---
title: ICorProfilerCallback::ManagedToUnmanagedTransition-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 277e035ab542f895ca700ecd5f3205cc757c9ddd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769311"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="8be6f-102">ICorProfilerCallback::ManagedToUnmanagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="8be6f-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="8be6f-103">Benachrichtigt den Profiler, dass ein Übergang aus verwaltetem Code an nicht verwalteten Code aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8be6f-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8be6f-104">Syntax</span></span>  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8be6f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8be6f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8be6f-106">[in] Die ID der Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8be6f-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="8be6f-107">[in] Der Wert der [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) Enumeration, der angibt, ob der Übergang erfolgt ist, aufgrund eines Aufrufs in nicht verwaltetem Code aus verwaltetem Code oder aufgrund einer Rückgabe von einer verwalteten Funktion, die von einer nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8be6f-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8be6f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8be6f-108">Remarks</span></span>  
 <span data-ttu-id="8be6f-109">Wenn der Wert des `reason` COR_PRF_TRANSITION_CALL die Funktion, die ID ist, dass der nicht verwaltete Funktion, die nicht kompiliert wurden wird mithilfe des just-in-Time-Compilers.</span><span class="sxs-lookup"><span data-stu-id="8be6f-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="8be6f-110">Nicht verwaltete Funktionen sind grundlegende Informationen, die zugeordnet sind, z. B. einen Namen und einige Metadaten.</span><span class="sxs-lookup"><span data-stu-id="8be6f-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="8be6f-111">Wenn die nicht verwaltete Funktion aufgerufen wurde, mithilfe des impliziten Plattform Plattformaufruf (PInvoke), die Laufzeit nicht bestimmen, das Ziel des Aufrufs und den Wert der `functionId` NULL.</span><span class="sxs-lookup"><span data-stu-id="8be6f-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="8be6f-112">Weitere Informationen zu implizites PInvoke, finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="8be6f-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be6f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8be6f-113">Requirements</span></span>  
 <span data-ttu-id="8be6f-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8be6f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be6f-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8be6f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8be6f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8be6f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8be6f-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be6f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be6f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8be6f-118">See also</span></span>

- [<span data-ttu-id="8be6f-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8be6f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8be6f-120">UnmanagedToManagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="8be6f-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="8be6f-121">Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)</span><span class="sxs-lookup"><span data-stu-id="8be6f-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
