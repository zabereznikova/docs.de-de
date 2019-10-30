---
title: 'ICorProfilerCallback7:: moduleinmemorysymbolsupveraltet-Methode'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: f6dd10d196ffd3a653584e1bc8d1a5643850bc33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136607"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="0b72f-102">ICorProfilerCallback7:: moduleinmemorysymbolsupveraltet-Methode</span><span class="sxs-lookup"><span data-stu-id="0b72f-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="0b72f-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="0b72f-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="0b72f-104">Benachrichtigt den Profiler, wenn der einem in-Memory-Modul zugeordnete Symbol Datenstrom aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0b72f-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b72f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b72f-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b72f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b72f-106">Parameters</span></span>  
 <span data-ttu-id="0b72f-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="0b72f-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="0b72f-108">Der Bezeichner des Moduls im Arbeitsspeicher, dessen symbolstream aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0b72f-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b72f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b72f-109">Remarks</span></span>  
 <span data-ttu-id="0b72f-110">Dieser Rückruf wird gesteuert, indem das [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) -Ereignis Masken Flag beim Aufrufen der [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) -Methode festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0b72f-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b72f-111">Dieses Ereignis wird derzeit nicht für Symbole ausgelöst, die über <xref:System.Reflection.Emit> APIs implizit erstellt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0b72f-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="0b72f-112">Auch wenn Symbole im Vordergrund in einem Rückruf einer der über Ladungen der verwalteten <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType>-Methoden bereitgestellt werden, die ein `rawSymbolStore`-Argument zum Angeben der Symbole für die Assembly enthalten, ordnet die Common Language Runtime die symbolischen Daten möglicherweise erst dann dem Modul zu, wenn die Der [moduleloadabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0b72f-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="0b72f-113">Dieses Ereignis bietet eine spätere Gelegenheit, Symbole für solche Module zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="0b72f-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b72f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b72f-114">Requirements</span></span>  
 <span data-ttu-id="0b72f-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b72f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b72f-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b72f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b72f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b72f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b72f-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b72f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b72f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b72f-119">See also</span></span>

- [<span data-ttu-id="0b72f-120">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="0b72f-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="0b72f-121">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="0b72f-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="0b72f-122">CorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b72f-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
