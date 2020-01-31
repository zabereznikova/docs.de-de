---
title: ICorProfilerCallback5-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: 7981e7d2d2a4588e56d3c30d0ede2d003fdcd32e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865024"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="d4eea-102">ICorProfilerCallback5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4eea-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="d4eea-103">Ergänzt Informationen, um einem Profiler zu helfen, den vollständigen Abschluss von Live-Objekten zu identifizieren, wenn er mit der [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) -Methode oder der [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) -Methode zusammen mit den [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) -und [conditionalweaktableelementreferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) -Methoden verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4eea-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="d4eea-104">`ICorProfilerCallback5` müssen von einem verwalteten arbeitsspeicherprofiler implementiert werden, um Benachrichtigungen zu abonnieren, die mit abhängigen Handles verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="d4eea-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4eea-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4eea-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4eea-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="d4eea-106">Methods</span></span>  
  
|<span data-ttu-id="d4eea-107">-Methode</span><span class="sxs-lookup"><span data-stu-id="d4eea-107">Method</span></span>|<span data-ttu-id="d4eea-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4eea-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4eea-109">ConditionalWeakTableElementReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="d4eea-109">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="d4eea-110">Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="d4eea-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4eea-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4eea-111">Requirements</span></span>  
 <span data-ttu-id="d4eea-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4eea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4eea-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d4eea-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4eea-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4eea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4eea-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4eea-115">See also</span></span>

- [<span data-ttu-id="d4eea-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d4eea-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d4eea-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4eea-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
