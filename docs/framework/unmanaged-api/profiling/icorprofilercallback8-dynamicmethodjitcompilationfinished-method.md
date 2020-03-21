---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175108"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="256eb-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="256eb-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="256eb-103">[Unterstützt in .NET Framework 4.7 und neueren Versionen]</span><span class="sxs-lookup"><span data-stu-id="256eb-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="256eb-104">Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="256eb-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="256eb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="256eb-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="256eb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="256eb-106">Parameters</span></span>  
<span data-ttu-id="256eb-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="256eb-107">[in] `functionId`</span></span>  
<span data-ttu-id="256eb-108">Der Bezeichner der In-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="256eb-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="256eb-109">[in] `hrStatus` Ein Wert, der angibt, ob die JIT-Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="256eb-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="256eb-110">[in] `fIsSafeToBlock` , um anzugeben, dass das Blockieren dazu führen kann, dass die Laufzeit darauf wartet, dass der aufrufende Thread von diesem Rückruf 
 `true` zurückkehrt. `false` , um anzugeben, dass die Blockierung den Betrieb der Laufzeit nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="256eb-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="256eb-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="256eb-111">Remarks</span></span>  

<span data-ttu-id="256eb-112">Dieser Rückruf wird ausgelöst, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="256eb-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="256eb-113">Dazu gehören verschiedene IL-Stubs und LCG-Methoden.</span><span class="sxs-lookup"><span data-stu-id="256eb-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="256eb-114">Ziel ist es, Profilerautoren genügend Informationen zur Verfügung zu stellen, um die kompilierte Methode für Benutzer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="256eb-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="256eb-115">`functionId`Werte können nicht zum Auflösen in ihre Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten haben.</span><span class="sxs-lookup"><span data-stu-id="256eb-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="256eb-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="256eb-116">Requirements</span></span>  
 <span data-ttu-id="256eb-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="256eb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="256eb-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="256eb-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="256eb-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="256eb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="256eb-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="256eb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="256eb-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="256eb-121">See also</span></span>

- [<span data-ttu-id="256eb-122">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="256eb-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="256eb-123">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="256eb-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
