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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12414064bf0651eab443951bde2a50dcff7b2291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992094"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="056b7-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span><span class="sxs-lookup"><span data-stu-id="056b7-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="056b7-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="056b7-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="056b7-104">Benachrichtigt den Profiler an, wenn der symbolstream ein in-Memory-Modul aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="056b7-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="056b7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="056b7-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="056b7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="056b7-106">Parameters</span></span>  
 <span data-ttu-id="056b7-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="056b7-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="056b7-108">Der Bezeichner des Moduls im Arbeitsspeicher, deren symbolstream aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="056b7-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="056b7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="056b7-109">Remarks</span></span>  
 <span data-ttu-id="056b7-110">Dieser Rückruf wird gesteuert, indem die [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) ereignismaskenkennzeichnens beim Aufrufen der [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="056b7-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="056b7-111">Dieses Ereignis wird derzeit nicht für Symbole implizit erstellt oder geändert wird, über ausgelöst <xref:System.Reflection.Emit> APIs.</span><span class="sxs-lookup"><span data-stu-id="056b7-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="056b7-112">Auch wenn Symbole vorab in einem Aufruf einer Überladung der verwalteten bereitgestellt werden <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> Methoden, die umfasst eine `rawSymbolStore` Argument an die Symbole für die Assembly, die Laufzeit kann die symbolische Daten nicht tatsächlich mit dem Modul zuordnen erst nachdem der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="056b7-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="056b7-113">Dieses Ereignis bietet eine höhere Chance Symbole für diese Module zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="056b7-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="056b7-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="056b7-114">Requirements</span></span>  
 <span data-ttu-id="056b7-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="056b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="056b7-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="056b7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="056b7-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="056b7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="056b7-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="056b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056b7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="056b7-119">See also</span></span>

- [<span data-ttu-id="056b7-120">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="056b7-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="056b7-121">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="056b7-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="056b7-122">CorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="056b7-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
