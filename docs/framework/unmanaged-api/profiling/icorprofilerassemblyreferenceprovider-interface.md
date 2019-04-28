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
ms.openlocfilehash: 3bad1cc71b9a27896141837a6d342f2cfe068fc5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598660"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="2ebef-102">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ebef-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="2ebef-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="2ebef-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2ebef-104">Ermöglicht es dem Profiler, die common Language Runtime (CLR) über Assemblyverweise zu informieren, die der Profiler im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="2ebef-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ebef-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2ebef-105">Methods</span></span>  
  
|<span data-ttu-id="2ebef-106">Methode</span><span class="sxs-lookup"><span data-stu-id="2ebef-106">Method</span></span>|<span data-ttu-id="2ebef-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ebef-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ebef-108">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="2ebef-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="2ebef-109">Informiert die CLR über Assemblyverweise, die der Profiler plant, fügen Sie in der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="2ebef-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ebef-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ebef-110">Remarks</span></span>  
 <span data-ttu-id="2ebef-111">Die CLR übergibt den Profiler eine `ICorProfilerAssemblyReferenceProvider` -Schnittstellenobjekt im der [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="2ebef-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="2ebef-112">Dies kann der Profiler die CLR über Assemblyverweise zu informieren, die der Profiler plant, später im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="2ebef-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="2ebef-113">-Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2ebef-113">callback.</span></span> <span data-ttu-id="2ebef-114">Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="2ebef-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="2ebef-115">Diese Schnittstelle kann nur in verwendet werden, die [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf, der dieses Schnittstellenobjekt an den Profiler weitergibt.</span><span class="sxs-lookup"><span data-stu-id="2ebef-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ebef-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ebef-116">Requirements</span></span>  
 <span data-ttu-id="2ebef-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ebef-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ebef-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ebef-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ebef-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ebef-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebef-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ebef-120">See also</span></span>

- [<span data-ttu-id="2ebef-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2ebef-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
