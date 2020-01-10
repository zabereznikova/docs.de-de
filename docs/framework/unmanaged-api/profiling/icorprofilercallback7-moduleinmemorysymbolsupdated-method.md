---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: b9e404de96fa42509144904f5b2ff58e341578a9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740443"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="cf560-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span><span class="sxs-lookup"><span data-stu-id="cf560-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="cf560-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="cf560-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="cf560-104">Benachrichtigt den Profiler, wenn der einem in-Memory-Modul zugeordnete Symbol Datenstrom aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cf560-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf560-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf560-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf560-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="cf560-106">Parameters</span></span>  
 <span data-ttu-id="cf560-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="cf560-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="cf560-108">Der Bezeichner des Moduls im Arbeitsspeicher, dessen symbolstream aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cf560-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf560-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf560-109">Remarks</span></span>  
 <span data-ttu-id="cf560-110">Dieser Rückruf wird gesteuert, indem das Flag für die [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) -Ereignis Maske beim Aufrufen der [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) -Methode festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="cf560-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf560-111">Dieses Ereignis wird derzeit nicht für Symbole ausgelöst, die über <xref:System.Reflection.Emit> APIs implizit erstellt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cf560-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="cf560-112">Auch wenn Symbole in einem Aufrufs einer der über Ladungen der verwalteten <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methoden bereitgestellt werden, die ein `rawSymbolStore`-Argument zum Angeben der Symbole für die Assembly enthalten, ordnet die Runtime die symbolischen Daten möglicherweise erst dann dem Modul zu, wenn der [moduleloadbeendeten](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cf560-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="cf560-113">Dieses Ereignis bietet eine spätere Gelegenheit, Symbole für solche Module zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="cf560-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf560-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf560-114">Requirements</span></span>  
 <span data-ttu-id="cf560-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf560-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf560-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf560-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf560-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf560-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf560-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf560-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf560-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf560-119">See also</span></span>

- [<span data-ttu-id="cf560-120">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="cf560-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="cf560-121">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="cf560-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="cf560-122">CorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf560-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
