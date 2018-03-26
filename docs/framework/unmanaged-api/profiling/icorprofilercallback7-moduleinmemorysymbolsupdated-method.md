---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: ''
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 898adf043e425c00d6e311e2f67c53ed65cacb33
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="9e9bf-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span><span class="sxs-lookup"><span data-stu-id="9e9bf-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="9e9bf-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="9e9bf-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="9e9bf-104">Benachrichtigt den Profiler an, wenn der symbolstream ein in-Memory-Modul aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e9bf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e9bf-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e9bf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e9bf-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9e9bf-107">Der Bezeichner des in-Memory-Moduls, deren symbolstream aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-107">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e9bf-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e9bf-108">Remarks</span></span>  
 <span data-ttu-id="9e9bf-109">Dieser Rückruf wird gesteuert durch Festlegen der [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) ereignismaskenkennzeichnens beim Aufrufen der [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-109">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e9bf-110">Dieses Ereignis ist derzeit nicht für Symbole implizit erstellt oder geändert wird, über ausgelöst <xref:System.Reflection.Emit> APIs.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-110">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="9e9bf-111">Selbst wenn Symbole vorab in einem Aufruf an eine der Überladungen der verwalteten bereitgestellt werden <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> Methoden, die umfasst eine `rawSymbolStore` Argument an die Symbole für die Assembly, die Common Language Runtime kann die symbolischen Daten nicht tatsächlich mit dem Modul zuordnen erst nachdem die [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-111">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="9e9bf-112">Dieses Ereignis ermöglicht eine höhere Symbole für solche Modulen zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-112">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e9bf-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e9bf-113">Requirements</span></span>  
 <span data-ttu-id="9e9bf-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e9bf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e9bf-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e9bf-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e9bf-116">**Library:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e9bf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e9bf-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e9bf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e9bf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e9bf-118">See Also</span></span>  
 [<span data-ttu-id="9e9bf-119">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="9e9bf-119">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="9e9bf-120">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="9e9bf-120">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="9e9bf-121">CorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e9bf-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
