---
title: ICorProfilerCallback::JITFunctionPitched-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 9bb3934be4a2f4de4a3a235a00522c801331e1eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448429"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="3ecae-102">ICorProfilerCallback::JITFunctionPitched-Methode</span><span class="sxs-lookup"><span data-stu-id="3ecae-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="3ecae-103">Benachrichtigt den Profiler, dass eine Funktion, die Just-in-time (JIT)-kompiliert wurde, aus dem Arbeitsspeicher entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="3ecae-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ecae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ecae-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ecae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ecae-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="3ecae-106">in Die ID der Funktion, die entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="3ecae-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ecae-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ecae-107">Remarks</span></span>  
 <span data-ttu-id="3ecae-108">Wenn die entfernte Funktion aufgerufen wird, empfängt der Profiler neue JIT-Kompilierungs Ereignisse, wenn die Funktion erneut kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="3ecae-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="3ecae-109">Der Common Language Runtime (CLR)-JIT-Compiler entfernt derzeit keine Funktionen aus dem Arbeitsspeicher, weshalb dieser Rückruf derzeit nicht verwendet wird und nicht vom Profiler empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="3ecae-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="3ecae-110">Der Wert `functionId` ist erst gültig, wenn die Funktion erneut kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="3ecae-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="3ecae-111">Wenn die Funktion erneut kompiliert wird, wird derselbe `functionId` Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ecae-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ecae-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3ecae-112">Requirements</span></span>  
 <span data-ttu-id="3ecae-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ecae-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ecae-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ecae-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ecae-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ecae-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ecae-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ecae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ecae-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ecae-117">See also</span></span>

- [<span data-ttu-id="3ecae-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ecae-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
