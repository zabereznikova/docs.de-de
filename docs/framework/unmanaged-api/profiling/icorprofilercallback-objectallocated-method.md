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
ms.openlocfilehash: fda234a6a280aeea1f497ad195d6d41efb6aa951
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674331"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="d7709-102">ICorProfilerCallback::ObjectAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="d7709-102">ICorProfilerCallback::ObjectAllocated Method</span></span>

<span data-ttu-id="d7709-103">Benachrichtigt den Profiler, dass der Arbeitsspeicher im Heap für ein Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="d7709-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7709-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7709-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7709-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7709-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="d7709-106">in Die ID des Objekts, für das Speicher zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d7709-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="d7709-107">in Die ID der Klasse, für die das Objekt eine Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="d7709-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7709-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7709-108">Remarks</span></span>  

 <span data-ttu-id="d7709-109">Die- `ObjectedAllocated` Methode wird nicht für Zuordnungen aus dem Stapel oder dem nicht verwalteten Speicher aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d7709-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="d7709-110">Der- `classId` Parameter kann auf eine Klasse in verwaltetem Code verweisen, die noch nicht geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="d7709-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="d7709-111">Der Profiler empfängt direkt nach dem Rückruf einen Klassen Lade Rückruf für diese Klasse `ObjectAllocated` .</span><span class="sxs-lookup"><span data-stu-id="d7709-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7709-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d7709-112">Requirements</span></span>  

 <span data-ttu-id="d7709-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7709-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7709-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7709-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7709-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7709-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7709-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7709-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7709-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7709-117">See also</span></span>

- [<span data-ttu-id="d7709-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7709-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d7709-119">ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="d7709-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="d7709-120">ClassLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="d7709-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
