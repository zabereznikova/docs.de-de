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
ms.openlocfilehash: 46a25fc6e9119481f728275e0569429cc6c46dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725429"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="45776-102">ICorProfilerCallback8::D ynamicmethodjitcompilationstarted-Methode</span><span class="sxs-lookup"><span data-stu-id="45776-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>

<span data-ttu-id="45776-103">[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="45776-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="45776-104">Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="45776-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45776-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="45776-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45776-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="45776-106">Parameters</span></span>  

<span data-ttu-id="45776-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="45776-107">[in] `functionId`</span></span>  
<span data-ttu-id="45776-108">Der Bezeichner der in-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="45776-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="45776-109">[in] `fIsSafeToBlock` 
 `true` , um anzugeben, dass das blockieren möglicherweise dazu führt, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung den Lauf der Laufzeit nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="45776-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="45776-110">[in] `pILHeader` Ein Zeiger auf das erste Byte des Il-Headers der Methode.</span><span class="sxs-lookup"><span data-stu-id="45776-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="45776-111">[in] `cbILHeader` Die Anzahl der Bytes im Il-Header.</span><span class="sxs-lookup"><span data-stu-id="45776-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="45776-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45776-112">Remarks</span></span>  

<span data-ttu-id="45776-113">Dieser Rückruf wird ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="45776-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="45776-114">Dies schließt verschiedene IL-Stub-und LCG-Methoden ein.</span><span class="sxs-lookup"><span data-stu-id="45776-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="45776-115">Ziel ist es, Profiler-Writern ausreichend Informationen bereitzustellen, um die kompilierte Methode für Benutzer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="45776-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="45776-116">`functionId` Werte können nicht verwendet werden, um Ihre Metadatentoken aufzulösen, da dynamische Methoden keine Metadaten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="45776-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="45776-117">Der `pILHeader` Zeiger ist nur während des Rückrufs gültig.</span><span class="sxs-lookup"><span data-stu-id="45776-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="45776-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="45776-118">Requirements</span></span>  

 <span data-ttu-id="45776-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45776-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45776-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45776-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45776-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45776-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45776-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45776-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45776-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45776-123">See also</span></span>

- [<span data-ttu-id="45776-124">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="45776-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="45776-125">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45776-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
