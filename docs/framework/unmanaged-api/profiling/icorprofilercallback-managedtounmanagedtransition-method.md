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
ms.openlocfilehash: ef65ed908c71bcc2755aaf42070439fd7dab3f6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733138"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="d5bcc-102">ICorProfilerCallback::ManagedToUnmanagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="d5bcc-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>

<span data-ttu-id="d5bcc-103">Benachrichtigt den Profiler, dass ein Übergang von verwaltetem Code zu nicht verwaltetem Code erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5bcc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5bcc-104">Syntax</span></span>  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5bcc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5bcc-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="d5bcc-106">in Die ID der Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="d5bcc-107">in Ein Wert der [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) -Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von nicht verwaltetem Code aus verwaltetem Code aufgetreten ist, oder aufgrund einer Rückgabe von einer verwalteten Funktion, die von einer nicht verwalteten Funktion aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5bcc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5bcc-108">Remarks</span></span>  

 <span data-ttu-id="d5bcc-109">Wenn der Wert von `reason` COR_PRF_TRANSITION_CALL ist, ist die Funktions-ID die der nicht verwalteten Funktion, die nie mit dem Just-in-Time-Compiler kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="d5bcc-110">Nicht verwalteten Funktionen sind grundlegende Informationen zugeordnet, z. b. ein Name und einige Metadaten.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="d5bcc-111">Wenn die nicht verwaltete Funktion mit dem impliziten Platt Form Aufruf (PInvoke) aufgerufen wurde, kann die Laufzeit das Ziel des Aufrufs nicht bestimmen, und der Wert von ist `functionId` NULL.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="d5bcc-112">Weitere Informationen zu implizitem PInvoke finden [Sie unter Using C++ Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="d5bcc-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5bcc-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d5bcc-113">Requirements</span></span>  

 <span data-ttu-id="d5bcc-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5bcc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5bcc-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5bcc-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5bcc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5bcc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5bcc-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5bcc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5bcc-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5bcc-118">See also</span></span>

- [<span data-ttu-id="d5bcc-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5bcc-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d5bcc-120">UnmanagedToManagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="d5bcc-120">UnmanagedToManagedTransition Method</span></span>](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="d5bcc-121">Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)</span><span class="sxs-lookup"><span data-stu-id="d5bcc-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
