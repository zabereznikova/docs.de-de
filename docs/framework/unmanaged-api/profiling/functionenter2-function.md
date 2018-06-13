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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d79249a2540adbd7f1b7e9bf36c899ba94d71e2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452389"
---
# <a name="functionenter2-function"></a><span data-ttu-id="e26ec-102">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="e26ec-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="e26ec-103">Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben werden und Informationen über den Stapelrahmen und die Funktionsargumente bietet.</span><span class="sxs-lookup"><span data-stu-id="e26ec-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="e26ec-104">Diese Funktion ersetzt die [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="e26ec-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26ec-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e26ec-105">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e26ec-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e26ec-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="e26ec-107">[in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e26ec-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="e26ec-108">[in] Der Funktionsbezeichner, die der Profiler zuvor mithilfe des Parameters der [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="e26ec-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="e26ec-109">[in] Ein `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapelrahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="e26ec-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="e26ec-110">Der Profiler sollte dies als ein nicht transparentes Handle, das an das Ausführungsmodul in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e26ec-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="e26ec-111">[in] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) -Struktur, die Speicherorte im Arbeitsspeicher, der die Argumente der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="e26ec-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="e26ec-112">Zugriff auf Informationen, die `COR_PRF_ENABLE_FUNCTION_ARGS` Flag muss festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e26ec-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="e26ec-113">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode, um die Ereignisflags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e26ec-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e26ec-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e26ec-114">Remarks</span></span>  
 <span data-ttu-id="e26ec-115">Die Werte der `func` und `argumentInfo` Parameter sind nicht gültig, nachdem die `FunctionEnter2` zurückgegeben, da die Werte möglicherweise geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e26ec-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="e26ec-116">Die `FunctionEnter2` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="e26ec-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="e26ec-117">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="e26ec-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="e26ec-118">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="e26ec-118">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="e26ec-119">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="e26ec-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="e26ec-120">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="e26ec-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e26ec-121">Die Implementierung der `FunctionEnter2` sollte nicht blockiert werden, da es die Garbagecollection verzögert.</span><span class="sxs-lookup"><span data-stu-id="e26ec-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="e26ec-122">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status.</span><span class="sxs-lookup"><span data-stu-id="e26ec-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e26ec-123">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionEnter2` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e26ec-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="e26ec-124">Darüber hinaus die `FunctionEnter2` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="e26ec-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e26ec-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e26ec-125">Requirements</span></span>  
 <span data-ttu-id="e26ec-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e26ec-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e26ec-127">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e26ec-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e26ec-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e26ec-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e26ec-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e26ec-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26ec-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e26ec-130">See Also</span></span>  
 [<span data-ttu-id="e26ec-131">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="e26ec-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="e26ec-132">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="e26ec-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="e26ec-133">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="e26ec-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="e26ec-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="e26ec-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
