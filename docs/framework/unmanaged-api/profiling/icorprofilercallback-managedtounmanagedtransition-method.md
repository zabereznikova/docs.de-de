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
ms.openlocfilehash: 0750ac66c654285e11dbbb5941f029bf5f900842
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866194"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="8f299-102">ICorProfilerCallback::ManagedToUnmanagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="8f299-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="8f299-103">Benachrichtigt den Profiler, dass ein Übergang von verwaltetem Code zu nicht verwaltetem Code erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="8f299-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f299-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f299-104">Syntax</span></span>  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f299-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8f299-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8f299-106">in Die ID der Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8f299-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="8f299-107">in Ein Wert der [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) -Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von nicht verwaltetem Code aus verwaltetem Code aufgetreten ist, oder aufgrund einer Rückgabe von einer verwalteten Funktion, die von einer nicht verwalteten Funktion aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="8f299-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f299-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f299-108">Remarks</span></span>  
 <span data-ttu-id="8f299-109">Wenn der Wert von `reason` COR_PRF_TRANSITION_CALL ist, entspricht die Funktions-ID der der nicht verwalteten Funktion, die nie mit dem Just-in-Time-Compiler kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="8f299-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="8f299-110">Nicht verwalteten Funktionen sind grundlegende Informationen zugeordnet, z. b. ein Name und einige Metadaten.</span><span class="sxs-lookup"><span data-stu-id="8f299-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="8f299-111">Wenn die nicht verwaltete Funktion mit dem impliziten Platt Form Aufruf (PInvoke) aufgerufen wurde, kann die Laufzeit das Ziel des Aufrufs nicht bestimmen, und der Wert `functionId` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="8f299-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="8f299-112">Weitere Informationen zu implizitem PInvoke finden [Sie C++ unter Using Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="8f299-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f299-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f299-113">Requirements</span></span>  
 <span data-ttu-id="8f299-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f299-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f299-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f299-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f299-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f299-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f299-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f299-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f299-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f299-118">See also</span></span>

- [<span data-ttu-id="8f299-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f299-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8f299-120">UnmanagedToManagedTransition-Methode</span><span class="sxs-lookup"><span data-stu-id="8f299-120">UnmanagedToManagedTransition Method</span></span>](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="8f299-121">Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)</span><span class="sxs-lookup"><span data-stu-id="8f299-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
