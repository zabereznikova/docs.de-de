---
title: ICorProfilerCallback6::GetAssemblyReferences-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc2e80d6d8207a869d43beb46cc9448bdd86dfec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="dd9a3-102">ICorProfilerCallback6::GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="dd9a3-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="dd9a3-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="dd9a3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dd9a3-104">Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd9a3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd9a3-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd9a3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd9a3-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="dd9a3-107">[in] Der Pfad und Name des Assemblys, dessen Metadaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="dd9a3-108">[in] Ein Zeiger auf die Adresse des ein [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) Schnittstelle, der angibt, die Assembly verweist, hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd9a3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd9a3-109">Return Value</span></span>  
 <span data-ttu-id="dd9a3-110">Rückgabewerte von diesem Rückruf werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd9a3-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd9a3-111">Remarks</span></span>  
 <span data-ttu-id="dd9a3-112">Dieser Rückruf wird gesteuert durch Festlegen der [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) ereignismaskenkennzeichnens beim Aufrufen der [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="dd9a3-113">Wenn der Profiler für registriert die [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückrufmethode darstellt, die Common Language Runtime übergibt, der Pfad und Name der Assembly geladen und zusammen mit einem Zeiger auf eine [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellenobjekt an diese Methode.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="dd9a3-114">Der Profiler ruft dann die [AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Methode mit einem `COR_PRF_ASSEMBLY_REFERENCE_INFO` -Objekt für jede Zielassembly auf aus der Assembly aus verweisen die `GetAssemblyReferences` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="dd9a3-115">Verwenden Sie den `GetAssemblyReferences`-Rückruf nur, wenn der Profiler die Metadaten einer Assembly für das Hinzufügen von Assemblyreferenzen ändern muss.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="dd9a3-116">(Beachten Sie, die die tatsächliche Änderung der Metadaten einer Assembly in erfolgt jedoch die [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)Rückrufmethode.) Der Profiler muss die Rückrufmethode `GetAssemblyReferences` implementieren, um die Common Language Runtime (CLR) zu informieren, dass Assemblyverweise hinzugefügt werden, nachdem das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="dd9a3-117">Damit kann sichergestellt werden, dass die Freigabeentscheidungen der Assembly, die in dieser frühen Phase von der CLR getroffen werden, gültig bleiben, auch wenn der Profiler die Assemblyverweise der Metadaten später ändert.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="dd9a3-118">Damit kann verhindert werden, dass manche Instanzen mit Profiler-Metadatenänderungen einen `SECURITY_E_INCOMPATIBLE_SHARE`-Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="dd9a3-119">Der Profiler verwendet das [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) Objekt, das von dieser Methode hinzuzufügenden Assemblyverweise die CLR Assemblyverweis-abschlussdurchlaufs bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="dd9a3-120">Die [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) Objekt sollte nur von innerhalb dieses Rückrufs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-120">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="dd9a3-121">Aufrufe von der [AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Methode, die von diesem Rückruf führen nicht zu geänderten Metadaten, aber nur in einem geänderten Assemblyverweis-abschlussdurchlauf.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="dd9a3-122">Der Profiler weiterhin verwenden, müssen ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) Objekt explizit hinzuzufügenden Assemblyverweise innerhalb der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf für die verweisende Assembly, selbst wenn es implementiert die `GetAssemblyReferences` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="dd9a3-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="dd9a3-123">Der Profiler sollte darauf vorbereitet sein, empfangen doppelter Aufrufe auf diesen Rückruf für dieselbe Assembly und sollte für jeden solchen Aufruf identisch reagieren (indem Sie den gleichen Satz von [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Aufrufe).</span><span class="sxs-lookup"><span data-stu-id="dd9a3-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd9a3-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd9a3-124">Requirements</span></span>  
 <span data-ttu-id="dd9a3-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd9a3-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd9a3-126">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dd9a3-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dd9a3-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd9a3-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd9a3-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd9a3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9a3-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd9a3-129">See Also</span></span>  
 [<span data-ttu-id="dd9a3-130">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd9a3-130">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 [<span data-ttu-id="dd9a3-131">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="dd9a3-131">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="dd9a3-132">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="dd9a3-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 [<span data-ttu-id="dd9a3-133">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd9a3-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
