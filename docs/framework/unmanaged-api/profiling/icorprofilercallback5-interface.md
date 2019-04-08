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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 114d97e02b0a6b80c46f971ed74a24dc3c397f1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072648"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="fcd9c-102">ICorProfilerCallback5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcd9c-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="fcd9c-103">Ergänzt Informationen, um einen Profiler, die den vollständigen Abschluss von aktiven Objekten zu identifizieren, bei Verwendung entweder mit Hilfe der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) oder [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)-Methode zusammen mit den [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) und [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="fcd9c-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 `ICorProfilerCallback5` <span data-ttu-id="fcd9c-104">muss durch einen verwalteten Arbeitsspeicher-Profiler implementiert werden, um Benachrichtigungen zu abonnieren, die mit abhängigen Handles verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="fcd9c-104">must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd9c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcd9c-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcd9c-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="fcd9c-106">Methods</span></span>  
  
|<span data-ttu-id="fcd9c-107">Methode</span><span class="sxs-lookup"><span data-stu-id="fcd9c-107">Method</span></span>|<span data-ttu-id="fcd9c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcd9c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcd9c-109">ConditionalWeakTableElementReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="fcd9c-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="fcd9c-110">Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="fcd9c-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fcd9c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcd9c-111">Requirements</span></span>  
 <span data-ttu-id="fcd9c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcd9c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd9c-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fcd9c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="fcd9c-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fcd9c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fcd9c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcd9c-115">See also</span></span>

- [<span data-ttu-id="fcd9c-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcd9c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fcd9c-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcd9c-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
