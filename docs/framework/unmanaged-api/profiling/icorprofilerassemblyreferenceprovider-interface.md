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
ms.openlocfilehash: 2cee012be2665f5a7212600ec11e401b18160d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691395"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="217eb-102">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="217eb-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>

<span data-ttu-id="217eb-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="217eb-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="217eb-104">Ermöglicht es dem Profiler, die Common Language Runtime (CLR) der Assemblyverweise zu informieren, die der Profiler im [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="217eb-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="217eb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="217eb-105">Methods</span></span>  
  
|<span data-ttu-id="217eb-106">Methode</span><span class="sxs-lookup"><span data-stu-id="217eb-106">Method</span></span>|<span data-ttu-id="217eb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="217eb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="217eb-108">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="217eb-108">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="217eb-109">Informiert die CLR über einen Assemblyverweis, den der Profiler plant, im [moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="217eb-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="217eb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="217eb-110">Remarks</span></span>  

 <span data-ttu-id="217eb-111">Die CLR übergibt dem Profiler ein `ICorProfilerAssemblyReferenceProvider` Schnittstellen Objekt im [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf.</span><span class="sxs-lookup"><span data-stu-id="217eb-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="217eb-112">Dies ermöglicht es dem Profiler, die CLR der Assemblyverweise zu informieren, die der Profiler später in [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md)hinzufügen möchte.</span><span class="sxs-lookup"><span data-stu-id="217eb-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="217eb-113">-Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="217eb-113">callback.</span></span> <span data-ttu-id="217eb-114">Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="217eb-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="217eb-115">Diese Schnittstelle kann nur im [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf verwendet werden, der dieses Schnittstellen Objekt an den Profiler übergibt.</span><span class="sxs-lookup"><span data-stu-id="217eb-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="217eb-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="217eb-116">Requirements</span></span>  

 <span data-ttu-id="217eb-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="217eb-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="217eb-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="217eb-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="217eb-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="217eb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="217eb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="217eb-120">See also</span></span>

- [<span data-ttu-id="217eb-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="217eb-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
