---
title: ICorProfilerCallback8::D ynamicmethodjitcompilationstarted-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136468"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="8c7c0-102">ICorProfilerCallback8::D ynamicmethodjitcompilationstarted-Methode</span><span class="sxs-lookup"><span data-stu-id="8c7c0-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="8c7c0-103">[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="8c7c0-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="8c7c0-104">Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c7c0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c7c0-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c7c0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c7c0-106">Parameters</span></span>  
<span data-ttu-id="8c7c0-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="8c7c0-107">[in] `functionId`</span></span>  
<span data-ttu-id="8c7c0-108">Der Bezeichner der in-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="8c7c0-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="8c7c0-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="8c7c0-110">`true`, um anzugeben, dass eine Blockierung bewirken kann, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung sich nicht auf den Lauf Zeit Vorgang auswirkt.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="8c7c0-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="8c7c0-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="8c7c0-112">Ein Zeiger auf das erste Byte des Il-Headers der Methode.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="8c7c0-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="8c7c0-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="8c7c0-114">Die Anzahl der Bytes im Il-Header.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="8c7c0-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c7c0-115">Remarks</span></span>  

<span data-ttu-id="8c7c0-116">Dieser Rückruf wird ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="8c7c0-117">Dies schließt verschiedene IL-Stub-und LCG-Methoden ein.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="8c7c0-118">Ziel ist es, Profiler-Writern ausreichend Informationen bereitzustellen, um die kompilierte Methode für Benutzer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="8c7c0-119">`functionId` Werte können nicht verwendet werden, um Ihre Metadatentoken aufzulösen, da dynamische Methoden keine Metadaten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="8c7c0-120">Der `pILHeader` Zeiger ist nur während des Rückrufs gültig.</span><span class="sxs-lookup"><span data-stu-id="8c7c0-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c7c0-121">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8c7c0-121">Requirements</span></span>  
 <span data-ttu-id="8c7c0-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c7c0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c7c0-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c7c0-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c7c0-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c7c0-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c7c0-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8c7c0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7c0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c7c0-126">See also</span></span>

- [<span data-ttu-id="8c7c0-127">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="8c7c0-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="8c7c0-128">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c7c0-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
