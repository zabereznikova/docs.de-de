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
ms.openlocfilehash: 8734fa9c9418b818cbe14ebe87ce2af6fa59c078
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499843"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="a1507-102">ICorProfilerCallback::UnmanagedToManagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="a1507-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="a1507-103">Benachrichtigt den Profiler, dass ein Übergang von nicht verwaltetem Code zu verwaltetem Code erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="a1507-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1507-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1507-104">Syntax</span></span>  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1507-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1507-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a1507-106">in Die ID der Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a1507-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="a1507-107">in Ein Wert der [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) -Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von verwaltetem Code aus nicht verwaltetem Code oder aufgrund einer Rückgabe von einer nicht verwalteten Funktion, die von einem verwalteten Code aufgerufen wurde, aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a1507-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1507-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a1507-108">Remarks</span></span>  
 <span data-ttu-id="a1507-109">Wenn der Wert von `reason` COR_PRF_TRANSITION_RETURN und `functionId` nicht NULL ist, ist die Funktions-ID die der nicht verwalteten Funktion und wurde nie mit dem JIT-Compiler (Just-in-Time) kompiliert.</span><span class="sxs-lookup"><span data-stu-id="a1507-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="a1507-110">Nicht verwalteten Funktionen sind einige grundlegende Informationen zugeordnet, z. b. ein Name und einige Metadaten.</span><span class="sxs-lookup"><span data-stu-id="a1507-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="a1507-111">Wenn der Wert von `reason` COR_PRF_TRANSITION_CALL ist, kann es vorkommen, dass die aufgerufene Funktion (d. h. die verwaltete Funktion) noch nicht JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a1507-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1507-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a1507-112">Requirements</span></span>  
 <span data-ttu-id="a1507-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1507-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1507-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1507-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1507-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1507-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1507-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1507-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1507-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a1507-117">See also</span></span>

- [<span data-ttu-id="a1507-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1507-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a1507-119">ManagedToUnmanagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="a1507-119">ManagedToUnmanagedTransition Method</span></span>](icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="a1507-120">Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)</span><span class="sxs-lookup"><span data-stu-id="a1507-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="a1507-121">Verwenden von C++ Interop (implizites PInvoke)</span><span class="sxs-lookup"><span data-stu-id="a1507-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
