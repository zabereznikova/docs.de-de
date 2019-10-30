---
title: ICorProfilerAssemblyReferenceProvider-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: f5ba72dca25889fb57c0ae1bb2429e54a8cf2228
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128718"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="fa76d-102">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa76d-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="fa76d-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="fa76d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fa76d-104">Ermöglicht es dem Profiler, die Common Language Runtime (CLR) der Assemblyverweise zu informieren, die der Profiler im [ICorProfilerCallback:: moduleloadabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fa76d-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa76d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fa76d-105">Methods</span></span>  
  
|<span data-ttu-id="fa76d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fa76d-106">Method</span></span>|<span data-ttu-id="fa76d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa76d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa76d-108">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="fa76d-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="fa76d-109">Informiert die CLR über einen Assemblyverweis, den der Profiler plant, im [moduleloadabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa76d-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa76d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa76d-110">Remarks</span></span>  
 <span data-ttu-id="fa76d-111">Die CLR übergibt dem Profiler ein `ICorProfilerAssemblyReferenceProvider` Interface-Objekt im [ICorProfilerCallback6:: getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf.</span><span class="sxs-lookup"><span data-stu-id="fa76d-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="fa76d-112">Dies ermöglicht es dem Profiler, die CLR der Assemblyverweise zu informieren, die der Profiler später in [ICorProfilerCallback:: moduleloadabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)hinzufügen möchte.</span><span class="sxs-lookup"><span data-stu-id="fa76d-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="fa76d-113">-Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fa76d-113">callback.</span></span> <span data-ttu-id="fa76d-114">Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="fa76d-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="fa76d-115">Diese Schnittstelle kann nur im [ICorProfilerCallback6:: getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf verwendet werden, der dieses Schnittstellen Objekt an den Profiler übergibt.</span><span class="sxs-lookup"><span data-stu-id="fa76d-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa76d-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa76d-116">Requirements</span></span>  
 <span data-ttu-id="fa76d-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa76d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa76d-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa76d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa76d-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa76d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa76d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa76d-120">See also</span></span>

- [<span data-ttu-id="fa76d-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fa76d-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
