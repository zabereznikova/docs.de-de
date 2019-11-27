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
ms.openlocfilehash: f4deec3e2b49b5cd6a924af8024e775c5c549f97
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440863"
---
# <a name="functionenter2-function"></a><span data-ttu-id="6c69d-102">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="6c69d-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="6c69d-103">Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übermittelt wird, und stellt Informationen über den Stapel Rahmen und die Funktionsargumente bereit.</span><span class="sxs-lookup"><span data-stu-id="6c69d-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="6c69d-104">Diese Funktion löst die [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="6c69d-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c69d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c69d-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c69d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c69d-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="6c69d-107">in Der Bezeichner der Funktion, an die das Steuerelement übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="6c69d-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="6c69d-108">in Der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor mithilfe der [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Funktion angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="6c69d-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="6c69d-109">in Ein `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen zeigt.</span><span class="sxs-lookup"><span data-stu-id="6c69d-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="6c69d-110">Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="6c69d-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="6c69d-111">in Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) -Struktur, die die Speicherorte der Argumente der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="6c69d-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="6c69d-112">Um auf Argument Informationen zugreifen zu können, muss das `COR_PRF_ENABLE_FUNCTION_ARGS`-Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6c69d-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="6c69d-113">Der Profiler kann die [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6c69d-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c69d-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c69d-114">Remarks</span></span>  
 <span data-ttu-id="6c69d-115">Die Werte der Parameter "`func`" und "`argumentInfo`" sind nicht gültig, nachdem die `FunctionEnter2` Funktion zurückgegeben wurde, da sich die Werte ändern oder gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="6c69d-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="6c69d-116">Die `FunctionEnter2` Funktion ist ein Rückruf. Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="6c69d-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="6c69d-117">Die-Implementierung muss das `__declspec`(`naked`)-Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c69d-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="6c69d-118">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="6c69d-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="6c69d-119">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="6c69d-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="6c69d-120">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="6c69d-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6c69d-121">Die Implementierung von `FunctionEnter2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="6c69d-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="6c69d-122">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="6c69d-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6c69d-123">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionEnter2` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6c69d-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="6c69d-124">Außerdem darf die `FunctionEnter2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="6c69d-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c69d-125">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6c69d-125">Requirements</span></span>  
 <span data-ttu-id="6c69d-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c69d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c69d-127">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="6c69d-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6c69d-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c69d-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c69d-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c69d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c69d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c69d-130">See also</span></span>

- [<span data-ttu-id="6c69d-131">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="6c69d-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="6c69d-132">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="6c69d-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="6c69d-133">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="6c69d-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="6c69d-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6c69d-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
