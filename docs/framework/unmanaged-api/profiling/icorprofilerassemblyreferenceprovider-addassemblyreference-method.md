---
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09ce4f3a293e7870ddadf4ad6ee2c15de10f4594
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598528"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="8b26c-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="8b26c-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="8b26c-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="8b26c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="8b26c-104">Informiert die common Language Runtime (CLR) über Assemblyverweise, die der Profiler plant, fügen Sie in der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="8b26c-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b26c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b26c-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b26c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b26c-106">Parameters</span></span>  
 <span data-ttu-id="8b26c-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="8b26c-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="8b26c-108">Ein Zeiger auf eine [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) -Struktur, die die CLR mit Informationen über einen Assemblyverweis, die beachtet werden muss bereitstellt, wenn ein Assemblyverweis-abschlussdurchlauf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b26c-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b26c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b26c-109">Remarks</span></span>  
 <span data-ttu-id="8b26c-110">Der Profiler ruft diese Methode für jede Zielassembly, die sie aus der Assembly aus verweisen möchte die `wszAssemblyPath` Argument der [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="8b26c-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="8b26c-111">Die [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellenobjekt wird an des Profilers übergeben [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf, der zusammen mit dem Assemblypfad sowie den Namen in der `wszAssemblyPath` Argument.</span><span class="sxs-lookup"><span data-stu-id="8b26c-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b26c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b26c-112">Requirements</span></span>  
 <span data-ttu-id="8b26c-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b26c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b26c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b26c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b26c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b26c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b26c-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b26c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b26c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b26c-117">See also</span></span>

- [<span data-ttu-id="8b26c-118">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b26c-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="8b26c-119">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="8b26c-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="8b26c-120">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="8b26c-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
