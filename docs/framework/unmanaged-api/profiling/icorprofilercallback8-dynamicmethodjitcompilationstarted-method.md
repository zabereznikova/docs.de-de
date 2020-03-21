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
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177045"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="baff3-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="baff3-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="baff3-103">[Unterstützt in .NET Framework 4.7 und neueren Versionen]</span><span class="sxs-lookup"><span data-stu-id="baff3-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="baff3-104">Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="baff3-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baff3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="baff3-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baff3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="baff3-106">Parameters</span></span>  
<span data-ttu-id="baff3-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="baff3-107">[in] `functionId`</span></span>  
<span data-ttu-id="baff3-108">Der Bezeichner der In-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="baff3-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="baff3-109">[in] `fIsSafeToBlock` , um anzugeben, dass das Blockieren dazu führen kann, dass die Laufzeit darauf wartet, dass der aufrufende Thread von diesem Rückruf 
 `true` zurückkehrt. `false` , um anzugeben, dass die Blockierung den Betrieb der Laufzeit nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="baff3-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="baff3-110">[in] `pILHeader` Ein Zeiger auf das erste Byte des IL-Headers der Methode.</span><span class="sxs-lookup"><span data-stu-id="baff3-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="baff3-111">[in] `cbILHeader` Die Anzahl der Bytes im IL-Header.</span><span class="sxs-lookup"><span data-stu-id="baff3-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="baff3-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="baff3-112">Remarks</span></span>  

<span data-ttu-id="baff3-113">Dieser Rückruf wird ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="baff3-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="baff3-114">Dazu gehören verschiedene IL-Stubs und LCG-Methoden.</span><span class="sxs-lookup"><span data-stu-id="baff3-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="baff3-115">Ziel ist es, Profilerautoren genügend Informationen zur Verfügung zu stellen, um die kompilierte Methode für Benutzer zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="baff3-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="baff3-116">`functionId`Werte können nicht zum Auflösen in ihre Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten haben.</span><span class="sxs-lookup"><span data-stu-id="baff3-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="baff3-117">Der `pILHeader` Zeiger ist nur während des Rückrufs gültig.</span><span class="sxs-lookup"><span data-stu-id="baff3-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="baff3-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="baff3-118">Requirements</span></span>  
 <span data-ttu-id="baff3-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baff3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baff3-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="baff3-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="baff3-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baff3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baff3-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="baff3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baff3-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="baff3-123">See also</span></span>

- [<span data-ttu-id="baff3-124">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="baff3-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="baff3-125">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="baff3-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
