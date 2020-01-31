---
title: FunctionEnter3WithInfo-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: 75a9a7174f105d99e9d1c9b220cfc5bf928d46ec
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866969"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="3fb48-102">FunctionEnter3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="3fb48-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="3fb48-103">Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übermittelt wird, und stellt ein Handle bereit, das an die [ICorProfilerInfo3:: GetFunctionEnter3Info-Methode](icorprofilerinfo3-getfunctionenter3info-method.md) zum Abrufen des Stapel Rahmens und der Funktionsargumente übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3fb48-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fb48-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fb48-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3fb48-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="3fb48-106">\[in] der Bezeichner der Funktion, an die das Steuerelement übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="3fb48-106">\[in] The identifier of the function to which control is passed.</span></span>

- `eltInfo`

  <span data-ttu-id="3fb48-107">\[in] ein undurchsichtiges handle, das Informationen zu einem angegebenen Stapel Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="3fb48-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="3fb48-108">Dieses Handle ist nur während des Rückrufs gültig, an den er übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="3fb48-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fb48-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fb48-109">Remarks</span></span>  
 <span data-ttu-id="3fb48-110">Die `FunctionEnter3WithInfo` Rückruf Methode benachrichtigt den Profiler, wenn Funktionen aufgerufen werden, und ermöglicht es dem Profiler, mithilfe der [ICorProfilerInfo3:: GetFunctionEnter3Info-Methode](icorprofilerinfo3-getfunctionenter3info-method.md) Argument Werte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3fb48-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="3fb48-111">Für den Zugriff auf Argument Informationen muss das `COR_PRF_ENABLE_FUNCTION_ARGS`-Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3fb48-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="3fb48-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo-Methode](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) verwenden, um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="3fb48-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="3fb48-113">Die `FunctionEnter3WithInfo` Funktion ist ein Rückruf. Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="3fb48-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="3fb48-114">Die-Implementierung muss das `__declspec(naked)`-Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="3fb48-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="3fb48-115">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="3fb48-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="3fb48-116">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="3fb48-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="3fb48-117">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="3fb48-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="3fb48-118">Die Implementierung von `FunctionEnter3WithInfo` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="3fb48-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="3fb48-119">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="3fb48-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="3fb48-120">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionEnter3WithInfo` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3fb48-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="3fb48-121">Die `FunctionEnter3WithInfo` Funktion darf keinen verwalteten Code abrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.</span><span class="sxs-lookup"><span data-stu-id="3fb48-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb48-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fb48-122">Requirements</span></span>  
 <span data-ttu-id="3fb48-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fb48-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb48-124">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="3fb48-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3fb48-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fb48-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fb48-126">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fb48-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb48-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fb48-127">See also</span></span>

- [<span data-ttu-id="3fb48-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="3fb48-128">GetFunctionEnter3Info</span></span>](icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="3fb48-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="3fb48-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="3fb48-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="3fb48-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="3fb48-131">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="3fb48-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
