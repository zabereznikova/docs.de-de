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
ms.openlocfilehash: 7176c0f88daad64f793131aca8c6d9fa592a878c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503275"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="cf817-102">ICorProfilerCallback::ObjectsAllocatedByClass-Methode</span><span class="sxs-lookup"><span data-stu-id="cf817-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="cf817-103">Benachrichtigt den Profiler über die Anzahl von Instanzen der angegebenen Klasse, die seit dem letzten Garbage Collection erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="cf817-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf817-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf817-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf817-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf817-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="cf817-106">in Die Größe des `classIds` -Arrays und des- `cObjects` Arrays.</span><span class="sxs-lookup"><span data-stu-id="cf817-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="cf817-107">in Ein Array von Klassen-IDs, wobei jede ID eine Klasse mit einer oder mehreren Instanzen angibt.</span><span class="sxs-lookup"><span data-stu-id="cf817-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="cf817-108">in Ein Array von Ganzzahlen, wobei jede ganze Zahl die Anzahl der Instanzen für die entsprechende Klasse im `classIds` Array angibt.</span><span class="sxs-lookup"><span data-stu-id="cf817-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf817-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cf817-109">Remarks</span></span>  
 <span data-ttu-id="cf817-110">Die `classIds` `cObjects` Arrays und sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="cf817-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="cf817-111">Beispielsweise `classIds[i]` und `cObjects[i]` verweisen auf die gleiche Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf817-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="cf817-112">Wenn seit dem vorherigen Garbage Collection keine Instanz einer Klasse erstellt wurde, wird die Klasse ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="cf817-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="cf817-113">Der `ObjectsAllocatedByClass` Rückruf meldet im großen Objekt Heap zugeordnete Objekte nicht.</span><span class="sxs-lookup"><span data-stu-id="cf817-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="cf817-114">Die von gemeldeten Zahlen `ObjectsAllocatedByClass` sind nur Schätzungen.</span><span class="sxs-lookup"><span data-stu-id="cf817-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="cf817-115">Verwenden Sie für exakte Anzahlen [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="cf817-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="cf817-116">Das `classIds` Array kann mindestens einen NULL-Eintrag enthalten, wenn das entsprechende `cObjects` Array Typen aufweist, die entladen werden.</span><span class="sxs-lookup"><span data-stu-id="cf817-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf817-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cf817-117">Requirements</span></span>  
 <span data-ttu-id="cf817-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf817-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf817-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf817-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf817-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf817-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf817-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf817-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf817-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="cf817-122">See also</span></span>

- [<span data-ttu-id="cf817-123">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf817-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
