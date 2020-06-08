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
ms.openlocfilehash: 6d732c6c2871cc5e042b8504db26aabb19963f8c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500506"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="c83d3-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="c83d3-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="c83d3-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="c83d3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c83d3-104">Informiert den Common Language Runtime (CLR) über einen Assemblyverweis, den der Profiler plant, im [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c83d3-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c83d3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c83d3-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c83d3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c83d3-106">Parameters</span></span>

- `pAssemblyRefInfo`

  <span data-ttu-id="c83d3-107">Ein Zeiger auf eine [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) Struktur, die der CLR Informationen über einen Assemblyverweis bereitstellt, die beim Ausführen eines assemblyverweisschließungs-Abschlusses berücksichtigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="c83d3-107">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c83d3-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c83d3-108">Remarks</span></span>  
 <span data-ttu-id="c83d3-109">Der Profiler ruft diese Methode für jede Zielassembly auf, auf die er von der im- `wszAssemblyPath` Argument des [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückrufs angegebenen Assembly verweisen soll.</span><span class="sxs-lookup"><span data-stu-id="c83d3-109">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="c83d3-110">Das [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellen Objekt wird zusammen mit dem Assemblypfad und-Namen im-Argument an den [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf des Profilers übergeben `wszAssemblyPath` .</span><span class="sxs-lookup"><span data-stu-id="c83d3-110">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c83d3-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c83d3-111">Requirements</span></span>  
 <span data-ttu-id="c83d3-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c83d3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c83d3-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c83d3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c83d3-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c83d3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c83d3-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c83d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c83d3-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c83d3-116">See also</span></span>

- [<span data-ttu-id="c83d3-117">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c83d3-117">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="c83d3-118">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="c83d3-118">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="c83d3-119">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="c83d3-119">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
