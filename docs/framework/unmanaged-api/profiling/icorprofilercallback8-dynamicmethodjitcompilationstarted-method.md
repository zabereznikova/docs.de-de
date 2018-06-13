---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454749"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="2475a-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="2475a-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="2475a-103">[Wird nur in .NET Framework 4.7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="2475a-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="2475a-104">Benachrichtigt den Profiler, wenn JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2475a-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2475a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2475a-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2475a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2475a-106">Parameters</span></span>  
<span data-ttu-id="2475a-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="2475a-107">[in] `functionId`</span></span>  
<span data-ttu-id="2475a-108">Der Bezeichner der in-Memory-Funktion, die für die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2475a-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="2475a-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="2475a-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="2475a-110">`true` um anzugeben, dass blockiert die Common Language Runtime zu warten, bis der aufrufende Thread von diesem Rückruf zurückgegeben bewirken kann. `false` um anzugeben, dass blockiert die Ausführung von der Laufzeit nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="2475a-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="2475a-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="2475a-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="2475a-112">Ein Zeiger auf das erste Byte des IL-Headers für die Methode.</span><span class="sxs-lookup"><span data-stu-id="2475a-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="2475a-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="2475a-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="2475a-114">Die Anzahl der Bytes im IL-Header.</span><span class="sxs-lookup"><span data-stu-id="2475a-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="2475a-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2475a-115">Remarks</span></span>  

<span data-ttu-id="2475a-116">Dieser Rückruf wird ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="2475a-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="2475a-117">Dies umfasst verschiedene IL-Stubs und LCG-Methoden.</span><span class="sxs-lookup"><span data-stu-id="2475a-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="2475a-118">Das Ziel besteht Profiler Writer genügend Informationen zum Identifizieren Sie der kompilierten Methode für Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2475a-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="2475a-119">`functionId` Werte können nicht zum Auflösen in ihren Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2475a-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="2475a-120">Die `pILHeader` -Zeiger ist nur gültig, während des Rückrufs.</span><span class="sxs-lookup"><span data-stu-id="2475a-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="2475a-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2475a-121">Requirements</span></span>  
 <span data-ttu-id="2475a-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2475a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2475a-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2475a-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2475a-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2475a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2475a-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2475a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2475a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2475a-126">See Also</span></span>  
 [<span data-ttu-id="2475a-127">DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="2475a-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [<span data-ttu-id="2475a-128">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2475a-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
