---
title: ICorProfilerCallback5-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback5
helpviewer_keywords: ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a862707dc64efbf3a9b1604a0e6a4ff1be81b43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="69b9b-102">ICorProfilerCallback5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69b9b-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="69b9b-103">Ergänzt Informationen, um einen Profiler den vollständigen Abschluss von aktiven Objekten zu identifizieren, bei Verwendung entweder mit Hilfe der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) oder [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)-Methode zusammen mit der [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) und [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="69b9b-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="69b9b-104">`ICorProfilerCallback5`muss von einem Profiler verwalteten Speicher zum Abonnieren von Benachrichtigungen im Zusammenhang mit abhängigen Handles implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="69b9b-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69b9b-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69b9b-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69b9b-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="69b9b-106">Methods</span></span>  
  
|<span data-ttu-id="69b9b-107">Methode</span><span class="sxs-lookup"><span data-stu-id="69b9b-107">Method</span></span>|<span data-ttu-id="69b9b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69b9b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69b9b-109">ConditionalWeakTableElementReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="69b9b-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="69b9b-110">Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="69b9b-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69b9b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69b9b-111">Requirements</span></span>  
 <span data-ttu-id="69b9b-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69b9b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69b9b-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69b9b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69b9b-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69b9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b9b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69b9b-115">See Also</span></span>  
 [<span data-ttu-id="69b9b-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="69b9b-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="69b9b-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69b9b-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
