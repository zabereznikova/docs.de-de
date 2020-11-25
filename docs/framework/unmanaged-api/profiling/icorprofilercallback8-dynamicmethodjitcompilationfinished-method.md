---
title: ICorProfilerCallback8::D ynamicmethodjitcompilationbeendete-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 6354667e754da42692cc0de2dc5330c56f951aa1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725442"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="74e82-102">ICorProfilerCallback8::D ynamicmethodjitcompilationbeendete-Methode</span><span class="sxs-lookup"><span data-stu-id="74e82-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>

<span data-ttu-id="74e82-103">[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="74e82-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="74e82-104">Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="74e82-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74e82-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74e82-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74e82-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="74e82-106">Parameters</span></span>  

<span data-ttu-id="74e82-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="74e82-107">[in] `functionId`</span></span>  
<span data-ttu-id="74e82-108">Der Bezeichner der in-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="74e82-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="74e82-109">[in] `hrStatus` Ein Wert, der angibt, ob die JIT-Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="74e82-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="74e82-110">[in] `fIsSafeToBlock` 
 `true` , um anzugeben, dass das blockieren möglicherweise dazu führt, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung den Lauf der Laufzeit nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="74e82-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="74e82-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74e82-111">Remarks</span></span>  

<span data-ttu-id="74e82-112">Dieser Rückruf wird ausgelöst, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="74e82-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="74e82-113">Dies schließt verschiedene IL-Stub-und LCG-Methoden ein.</span><span class="sxs-lookup"><span data-stu-id="74e82-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="74e82-114">Ziel ist es, Profiler-Writern ausreichend Informationen bereitzustellen, um die kompilierte Methode für Benutzer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="74e82-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="74e82-115">`functionId` Werte können nicht verwendet werden, um Ihre Metadatentoken aufzulösen, da dynamische Methoden keine Metadaten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="74e82-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="74e82-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="74e82-116">Requirements</span></span>  

 <span data-ttu-id="74e82-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74e82-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74e82-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74e82-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74e82-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74e82-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74e82-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="74e82-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e82-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74e82-121">See also</span></span>

- [<span data-ttu-id="74e82-122">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="74e82-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="74e82-123">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74e82-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
