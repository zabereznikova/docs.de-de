---
title: ICorProfilerAssemblyReferenceProvider-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 203362d2780d372236b05f753bedc0d59565d2b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="db162-102">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db162-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="db162-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="db162-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="db162-104">Ermöglicht es dem Profiler an die common Language Runtime (CLR) über Assemblyverweise zu informieren, die der Profiler im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="db162-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db162-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="db162-105">Methods</span></span>  
  
|<span data-ttu-id="db162-106">Methode</span><span class="sxs-lookup"><span data-stu-id="db162-106">Method</span></span>|<span data-ttu-id="db162-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db162-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db162-108">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="db162-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="db162-109">Informiert die CLR einen Assemblyverweis, die der Profiler plant, fügen Sie in der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="db162-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db162-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db162-110">Remarks</span></span>  
 <span data-ttu-id="db162-111">Die CLR übergibt den Profiler eine `ICorProfilerAssemblyReferenceProvider` Schnittstellenobjekt, das in der [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="db162-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="db162-112">Dies ermöglicht es dem Profiler, die CLR über Assemblyverweise zu informieren, die der Profiler plant, die später im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="db162-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="db162-113">-Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="db162-113">callback.</span></span> <span data-ttu-id="db162-114">Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="db162-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="db162-115">Diese Schnittstelle kann nur in verwendet das [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf, der dieses Schnittstellenobjekt an den Profiler weitergibt.</span><span class="sxs-lookup"><span data-stu-id="db162-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db162-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db162-116">Requirements</span></span>  
 <span data-ttu-id="db162-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db162-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db162-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db162-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db162-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db162-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db162-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db162-120">See Also</span></span>  
 [<span data-ttu-id="db162-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="db162-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
