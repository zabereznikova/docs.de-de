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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffb891e61fcb34e6d33a069fc32e68865739b86b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450881"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="06c3f-102">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06c3f-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="06c3f-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="06c3f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="06c3f-104">Ermöglicht es dem Profiler an die common Language Runtime (CLR) über Assemblyverweise zu informieren, die der Profiler im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="06c3f-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06c3f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="06c3f-105">Methods</span></span>  
  
|<span data-ttu-id="06c3f-106">Methode</span><span class="sxs-lookup"><span data-stu-id="06c3f-106">Method</span></span>|<span data-ttu-id="06c3f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06c3f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06c3f-108">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="06c3f-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="06c3f-109">Informiert die CLR einen Assemblyverweis, die der Profiler plant, fügen Sie in der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="06c3f-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06c3f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06c3f-110">Remarks</span></span>  
 <span data-ttu-id="06c3f-111">Die CLR übergibt den Profiler eine `ICorProfilerAssemblyReferenceProvider` Schnittstellenobjekt, das in der [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="06c3f-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="06c3f-112">Dies ermöglicht es dem Profiler, die CLR über Assemblyverweise zu informieren, die der Profiler plant, die später im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="06c3f-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="06c3f-113">-Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="06c3f-113">callback.</span></span> <span data-ttu-id="06c3f-114">Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="06c3f-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="06c3f-115">Diese Schnittstelle kann nur in verwendet das [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf, der dieses Schnittstellenobjekt an den Profiler weitergibt.</span><span class="sxs-lookup"><span data-stu-id="06c3f-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06c3f-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06c3f-116">Requirements</span></span>  
 <span data-ttu-id="06c3f-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06c3f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06c3f-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06c3f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06c3f-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06c3f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c3f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06c3f-120">See Also</span></span>  
 [<span data-ttu-id="06c3f-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="06c3f-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
