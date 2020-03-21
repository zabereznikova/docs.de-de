---
title: FunctionEnter2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177058"
---
# <a name="functionenter2-function"></a><span data-ttu-id="238cd-102">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="238cd-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="238cd-103">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird, und stellt Informationen über den Stapelrahmen und die Funktionsargumente bereit.</span><span class="sxs-lookup"><span data-stu-id="238cd-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="238cd-104">Diese Funktion ersetzt die [FunctionEnter-Funktion.](functionenter-function.md)</span><span class="sxs-lookup"><span data-stu-id="238cd-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238cd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="238cd-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="238cd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="238cd-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="238cd-107">\[in] Der Bezeichner der Funktion, an die das Steuerelement übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="238cd-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="238cd-108">\[in] Der neu zugeordnete Funktionsbezeichner, den der Profiler zuvor mithilfe der [Funktion FunctionIDMapper](functionidmapper-function.md) angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="238cd-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="238cd-109">\[in] `COR_PRF_FRAME_INFO` Ein Wert, der auf Informationen über den Stapelrahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="238cd-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="238cd-110">Der Profiler sollte dies als undurchsichtiges Handle behandeln, das an das Ausführungsmodul in der [ICorProfilerInfo2::GetFunctionInfo2-Methode](icorprofilerinfo2-getfunctioninfo2-method.md) zurückübergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="238cd-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="238cd-111">\[in] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) Struktur, die die Positionen im Speicher der Argumente der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="238cd-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="238cd-112">Um auf Argumentinformationen zugreifen `COR_PRF_ENABLE_FUNCTION_ARGS` zu können, muss das Flag gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="238cd-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="238cd-113">Der Profiler kann die [ICorProfilerInfo::SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen.</span><span class="sxs-lookup"><span data-stu-id="238cd-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="238cd-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="238cd-114">Remarks</span></span>  
 <span data-ttu-id="238cd-115">Die Werte `func` der `argumentInfo` und Parameter sind `FunctionEnter2` ungültig, nachdem die Funktion zurückgegeben wurde, da sich die Werte ändern oder zerstört werden können.</span><span class="sxs-lookup"><span data-stu-id="238cd-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="238cd-116">Die `FunctionEnter2` Funktion ist ein Rückruf; Sie müssen es implementieren.</span><span class="sxs-lookup"><span data-stu-id="238cd-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="238cd-117">Die Implementierung muss `__declspec``naked`das ( ) Storage-Class-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="238cd-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="238cd-118">Das Ausführungsmodul speichert keine Register, bevor diese Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="238cd-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="238cd-119">Beim Eintrag müssen Sie alle Register speichern, die Sie verwenden, einschließlich der Register in der Gleitkommaeinheit (FPU).</span><span class="sxs-lookup"><span data-stu-id="238cd-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="238cd-120">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter deaktivieren, die vom Aufrufer gedrückt wurden.</span><span class="sxs-lookup"><span data-stu-id="238cd-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="238cd-121">Die Implementierung `FunctionEnter2` von sollte nicht blockiert werden, da die Garbage Collection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="238cd-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="238cd-122">Die Implementierung sollte keine Garbage Collection versuchen, da sich der Stapel möglicherweise nicht in einem Garbage Collection-freundlichen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="238cd-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="238cd-123">Wenn versucht wird, eine Garbage Collection zu `FunctionEnter2` sammeln, wird die Laufzeit blockiert, bis sie zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="238cd-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="238cd-124">Außerdem darf `FunctionEnter2` die Funktion keinen verwalteten Code aufrufen oder in irgendeiner Weise eine verwaltete Speicherzuweisung verursachen.</span><span class="sxs-lookup"><span data-stu-id="238cd-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238cd-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="238cd-125">Requirements</span></span>  
 <span data-ttu-id="238cd-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="238cd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238cd-127">**Kopfzeile:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="238cd-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="238cd-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="238cd-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="238cd-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="238cd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238cd-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="238cd-130">See also</span></span>

- [<span data-ttu-id="238cd-131">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="238cd-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="238cd-132">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="238cd-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="238cd-133">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="238cd-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="238cd-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="238cd-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
