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
ms.openlocfilehash: 062229245e3ae209de0eda65d4be59e286f4da7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517746"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="58511-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="58511-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="58511-103">[Wird nur in der .NET Framework 4.7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="58511-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="58511-104">Benachrichtigt den Profiler an, wenn JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="58511-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58511-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58511-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58511-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="58511-106">Parameters</span></span>  
<span data-ttu-id="58511-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="58511-107">[in] `functionId`</span></span>  
<span data-ttu-id="58511-108">Der Bezeichner der in-Memory-Funktion, die für die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="58511-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="58511-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="58511-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="58511-110">`true` um anzugeben, das blockieren die Laufzeit zu warten, bis der aufrufende Thread von diesem Rückruf zurück zur Folge haben. `false` um anzugeben, dass die Blockierung der Vorgang der Laufzeit nicht beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="58511-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="58511-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="58511-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="58511-112">Ein Zeiger auf das erste Byte des IL-Headers der Methode.</span><span class="sxs-lookup"><span data-stu-id="58511-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="58511-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="58511-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="58511-114">Die Anzahl der Bytes in der IL-Header.</span><span class="sxs-lookup"><span data-stu-id="58511-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="58511-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58511-115">Remarks</span></span>  

<span data-ttu-id="58511-116">Dieser Rückruf wird immer dann ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="58511-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="58511-117">Dies umfasst verschiedene IL-Stubs und LCG-Methoden.</span><span class="sxs-lookup"><span data-stu-id="58511-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="58511-118">Das Ziel ist, die Profiler-Schreiber genügend Informationen zum Identifizieren der kompilierten Methode für Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="58511-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="58511-119">`functionId` Werte können nicht zum Auflösen in ihren Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten haben.</span><span class="sxs-lookup"><span data-stu-id="58511-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="58511-120">Die `pILHeader` -Zeiger ist nur gültig, während des Rückrufs.</span><span class="sxs-lookup"><span data-stu-id="58511-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="58511-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58511-121">Requirements</span></span>  
 <span data-ttu-id="58511-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58511-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58511-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58511-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58511-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58511-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58511-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="58511-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58511-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58511-126">See also</span></span>
- [<span data-ttu-id="58511-127">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="58511-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="58511-128">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58511-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
