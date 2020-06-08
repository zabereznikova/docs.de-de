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
ms.openlocfilehash: 554cc93de934061e87322c7557e05545e5e7bc62
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499076"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="2a06e-102">ICorProfilerCallback8::D ynamicmethodjitcompilationbeendete-Methode</span><span class="sxs-lookup"><span data-stu-id="2a06e-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="2a06e-103">[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="2a06e-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="2a06e-104">Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2a06e-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a06e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a06e-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a06e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a06e-106">Parameters</span></span>  
<span data-ttu-id="2a06e-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="2a06e-107">[in] `functionId`</span></span>  
<span data-ttu-id="2a06e-108">Der Bezeichner der in-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2a06e-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="2a06e-109">[in] `hrStatus` Ein Wert, der angibt, ob die JIT-Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2a06e-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="2a06e-110">[in] `fIsSafeToBlock` 
 `true` , um anzugeben, dass das blockieren möglicherweise dazu führt, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung den Lauf der Laufzeit nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="2a06e-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="2a06e-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2a06e-111">Remarks</span></span>  

<span data-ttu-id="2a06e-112">Dieser Rückruf wird ausgelöst, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2a06e-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="2a06e-113">Dies schließt verschiedene IL-Stub-und LCG-Methoden ein.</span><span class="sxs-lookup"><span data-stu-id="2a06e-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="2a06e-114">Ziel ist es, Profiler-Writern ausreichend Informationen bereitzustellen, um die kompilierte Methode für Benutzer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2a06e-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="2a06e-115">`functionId`Werte können nicht verwendet werden, um Ihre Metadatentoken aufzulösen, da dynamische Methoden keine Metadaten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2a06e-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a06e-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2a06e-116">Requirements</span></span>  
 <span data-ttu-id="2a06e-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a06e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a06e-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a06e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a06e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a06e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a06e-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a06e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a06e-121">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2a06e-121">See also</span></span>

- [<span data-ttu-id="2a06e-122">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="2a06e-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="2a06e-123">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a06e-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
