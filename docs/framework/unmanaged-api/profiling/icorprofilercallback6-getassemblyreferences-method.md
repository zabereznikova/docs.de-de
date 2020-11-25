---
title: ICorProfilerCallback6::GetAssemblyReferences-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
ms.openlocfilehash: c9e973009f46ef7e554ee2df63493464f4956342
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725481"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="2adb5-102">ICorProfilerCallback6::GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="2adb5-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>

<span data-ttu-id="2adb5-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="2adb5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2adb5-104">Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.</span><span class="sxs-lookup"><span data-stu-id="2adb5-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2adb5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2adb5-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2adb5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2adb5-106">Parameters</span></span>  

 `wszAssemblyPath`  
 <span data-ttu-id="2adb5-107">[in] Der Pfad und Name des Assemblys, dessen Metadaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2adb5-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="2adb5-108">in Ein Zeiger auf die Adresse einer [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstelle, die die hinzu zufügenden Assemblyverweise angibt.</span><span class="sxs-lookup"><span data-stu-id="2adb5-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2adb5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2adb5-109">Return Value</span></span>  

 <span data-ttu-id="2adb5-110">Rückgabewerte von diesem Rückruf werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2adb5-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2adb5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2adb5-111">Remarks</span></span>  

 <span data-ttu-id="2adb5-112">Dieser Rückruf wird gesteuert, indem das Flag für die [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) -Ereignis Maske beim Aufrufen der [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2adb5-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="2adb5-113">Wenn der Profiler für die [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf Methode registriert, übergibt die Laufzeit den Pfad und den Namen der zu ladenden Assembly zusammen mit einem Zeiger auf ein [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellen Objekt an diese Methode.</span><span class="sxs-lookup"><span data-stu-id="2adb5-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="2adb5-114">Der Profiler kann dann die [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode mit einem- `COR_PRF_ASSEMBLY_REFERENCE_INFO` Objekt für jede Zielassembly abrufen, auf die von der im Rückruf angegebenen Assembly verwiesen werden soll `GetAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="2adb5-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="2adb5-115">Verwenden Sie den `GetAssemblyReferences`-Rückruf nur, wenn der Profiler die Metadaten einer Assembly für das Hinzufügen von Assemblyreferenzen ändern muss.</span><span class="sxs-lookup"><span data-stu-id="2adb5-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="2adb5-116">(Beachten Sie jedoch, dass die tatsächliche Änderung der Metadaten einer Assembly in der [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md)-Rückruf Methode erfolgt.) Der Profiler `GetAssemblyReferences` muss die Rückruf Methode implementieren, um die Common Language Runtime (CLR) zu informieren, dass Assemblyverweise hinzugefügt werden, wenn das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2adb5-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="2adb5-117">Damit kann sichergestellt werden, dass die Freigabeentscheidungen der Assembly, die in dieser frühen Phase von der CLR getroffen werden, gültig bleiben, auch wenn der Profiler die Assemblyverweise der Metadaten später ändert.</span><span class="sxs-lookup"><span data-stu-id="2adb5-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="2adb5-118">Damit kann verhindert werden, dass manche Instanzen mit Profiler-Metadatenänderungen einen `SECURITY_E_INCOMPATIBLE_SHARE`-Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="2adb5-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="2adb5-119">Der Profiler verwendet das von dieser Methode bereitgestellte [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Objekt zum Hinzufügen von Assemblyverweisen zum CLR-assemblyverweisclosure</span><span class="sxs-lookup"><span data-stu-id="2adb5-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="2adb5-120">Das [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Objekt darf nur innerhalb dieses Rückrufs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2adb5-120">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="2adb5-121">Aufrufe der [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode von diesem Rückruf ergeben nicht geänderte Metadaten, sondern nur in einem geänderten Assemblyverweis-Abschluss Durchlauf.</span><span class="sxs-lookup"><span data-stu-id="2adb5-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="2adb5-122">Der Profiler muss weiterhin ein [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) -Objekt verwenden, um Assemblyverweise explizit aus dem Rückruf " [ICorProfilerCallback:: moduleloadbeendet](icorprofilercallback-moduleloadfinished-method.md) " für die referenzierende Assembly hinzuzufügen, selbst wenn der Rückruf implementiert wird `GetAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="2adb5-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="2adb5-123">Der Profiler sollte darauf vorbereitet sein, doppelte Aufrufe dieses Rückrufs für dieselbe Assembly zu empfangen, und sollte für jeden solchen doppelten Aufruf identisch sein (durch Ausführen desselben Satzes von [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -aufrufen).</span><span class="sxs-lookup"><span data-stu-id="2adb5-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2adb5-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2adb5-124">Requirements</span></span>  

 <span data-ttu-id="2adb5-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2adb5-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2adb5-126">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2adb5-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2adb5-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2adb5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2adb5-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2adb5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2adb5-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2adb5-129">See also</span></span>

- [<span data-ttu-id="2adb5-130">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2adb5-130">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)
- [<span data-ttu-id="2adb5-131">ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="2adb5-131">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="2adb5-132">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="2adb5-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="2adb5-133">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2adb5-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
