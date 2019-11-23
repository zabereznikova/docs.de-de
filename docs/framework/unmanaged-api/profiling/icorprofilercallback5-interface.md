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
ms.openlocfilehash: ce34d43091cdee0bca88f94711e49072fa4fd08c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430063"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="e5ecc-102">ICorProfilerCallback5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5ecc-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="e5ecc-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span><span class="sxs-lookup"><span data-stu-id="e5ecc-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="e5ecc-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span><span class="sxs-lookup"><span data-stu-id="e5ecc-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5ecc-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5ecc-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5ecc-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="e5ecc-106">Methods</span></span>  
  
|<span data-ttu-id="e5ecc-107">Methode</span><span class="sxs-lookup"><span data-stu-id="e5ecc-107">Method</span></span>|<span data-ttu-id="e5ecc-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5ecc-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5ecc-109">ConditionalWeakTableElementReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="e5ecc-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="e5ecc-110">Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="e5ecc-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5ecc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5ecc-111">Requirements</span></span>  
 <span data-ttu-id="e5ecc-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5ecc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5ecc-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5ecc-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5ecc-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5ecc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ecc-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5ecc-115">See also</span></span>

- [<span data-ttu-id="e5ecc-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e5ecc-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="e5ecc-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5ecc-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
