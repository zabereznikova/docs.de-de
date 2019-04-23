---
title: ICorProfilerCallback::ObjectAllocated-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c07b37e58141f7aff747bd3772be265ae0da42ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222015"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="9e38f-102">ICorProfilerCallback::ObjectAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="9e38f-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="9e38f-103">Benachrichtigt den Profiler, die für ein Objekt Speicher im Heap belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e38f-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e38f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e38f-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e38f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e38f-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="9e38f-106">[in] Die ID des Objekts für den Arbeitsspeicher zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="9e38f-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="9e38f-107">[in] Die ID der Klasse, von der das Objekt eine Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="9e38f-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e38f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e38f-108">Remarks</span></span>  
 <span data-ttu-id="9e38f-109">Die `ObjectedAllocated` Methode wird nicht für Zuordnungen der Stapel oder in nicht verwalteten Speicher aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9e38f-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="9e38f-110">Die `classId` Parameter kann verweisen auf eine Klasse in verwalteten Code, der noch nicht geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="9e38f-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="9e38f-111">Empfängt der Profiler einen-Klasse Last-Rückruf für diese Klasse unmittelbar nach der `ObjectAllocated` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="9e38f-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e38f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e38f-112">Requirements</span></span>  
 <span data-ttu-id="9e38f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e38f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e38f-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e38f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e38f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e38f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e38f-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e38f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e38f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e38f-117">See also</span></span>

- [<span data-ttu-id="9e38f-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e38f-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="9e38f-119">ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="9e38f-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="9e38f-120">ClassLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="9e38f-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
