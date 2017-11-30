---
title: ICorProfilerCallback::ObjectAllocated-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectAllocated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a7e67e6085db4b73ca39688935767072ceadb68e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="759f6-102">ICorProfilerCallback::ObjectAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="759f6-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="759f6-103">Benachrichtigt den Profiler, der Speicher im Heap für ein Objekt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="759f6-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="759f6-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="759f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="759f6-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="759f6-106">[in] Die ID des Objekts für den Speicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="759f6-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="759f6-107">[in] Die ID der Klasse, von der das Objekt eine Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="759f6-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="759f6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="759f6-108">Remarks</span></span>  
 <span data-ttu-id="759f6-109">Die `ObjectedAllocated` Methode wird nicht für Zuordnungen aus dem Stapel oder nicht verwalteten Speicher aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="759f6-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="759f6-110">Die `classId` Parameter kann verweisen auf eine Klasse in verwaltetem Code, die noch nicht geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="759f6-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="759f6-111">Empfängt der Profiler einen Klasse laden Rückruf für diese Klasse direkt nach der `ObjectAllocated` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="759f6-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="759f6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="759f6-112">Requirements</span></span>  
 <span data-ttu-id="759f6-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="759f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="759f6-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="759f6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="759f6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="759f6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="759f6-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="759f6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759f6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="759f6-117">See Also</span></span>  
 [<span data-ttu-id="759f6-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="759f6-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="759f6-119">ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="759f6-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [<span data-ttu-id="759f6-120">ClassLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="759f6-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
