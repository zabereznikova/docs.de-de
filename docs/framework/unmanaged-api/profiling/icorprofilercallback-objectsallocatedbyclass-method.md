---
title: ICorProfilerCallback::ObjectsAllocatedByClass-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9f5d2c08abbcab6bc1a6d0569b8e70d7c919def
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195864"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="ff07c-102">ICorProfilerCallback::ObjectsAllocatedByClass-Methode</span><span class="sxs-lookup"><span data-stu-id="ff07c-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="ff07c-103">Benachrichtigt den Profiler über die Anzahl der Instanzen der einzelnen angegebenen Klassen, die seit der letzten Garbagecollection erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ff07c-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff07c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff07c-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff07c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff07c-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="ff07c-106">[in] Die Größe der `classIds` und `cObjects` Arrays.</span><span class="sxs-lookup"><span data-stu-id="ff07c-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="ff07c-107">[in] Ein Array von Klassen-IDs, die, in dem jede ID eine Klasse mit einer oder mehreren Instanzen angibt.</span><span class="sxs-lookup"><span data-stu-id="ff07c-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="ff07c-108">[in] Ein Array von ganzen Zahlen, wobei jede ganze Zahl die Anzahl der Instanzen für die entsprechende Klasse im angibt der `classIds` Array.</span><span class="sxs-lookup"><span data-stu-id="ff07c-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff07c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff07c-109">Remarks</span></span>  
 <span data-ttu-id="ff07c-110">Die `classIds` und `cObjects` Arrays sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="ff07c-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="ff07c-111">Z. B. `classIds[i]` und `cObjects[i]` verweisen auf die gleiche Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff07c-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="ff07c-112">Wenn keine Instanz einer Klasse seit der letzten Garbagecollection erstellt wurde, wird die Klasse weggelassen.</span><span class="sxs-lookup"><span data-stu-id="ff07c-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="ff07c-113">Die `ObjectsAllocatedByClass` Rückruf meldet nicht in den großen Objektheap reservierten Objekte.</span><span class="sxs-lookup"><span data-stu-id="ff07c-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="ff07c-114">Die Anzahl von gemeldeten `ObjectsAllocatedByClass` nur Schätzungen.</span><span class="sxs-lookup"><span data-stu-id="ff07c-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="ff07c-115">Verwenden Sie für die genaue Anzahl, [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="ff07c-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="ff07c-116">Die `classIds` Array kann eine oder mehrere null-Einträge enthalten, wenn die entsprechende `cObjects` Array verfügt über die Typen, die entladen werden.</span><span class="sxs-lookup"><span data-stu-id="ff07c-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff07c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff07c-117">Requirements</span></span>  
 <span data-ttu-id="ff07c-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff07c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff07c-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff07c-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff07c-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff07c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff07c-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff07c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff07c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff07c-122">See also</span></span>

- [<span data-ttu-id="ff07c-123">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff07c-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
