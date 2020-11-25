---
title: ICorProfilerCallback::ThreadCreated-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
ms.openlocfilehash: 72b074d1794a6039060cbd84aabb0bc0155c154e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717257"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="878ab-102">ICorProfilerCallback::ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="878ab-102">ICorProfilerCallback::ThreadCreated Method</span></span>

<span data-ttu-id="878ab-103">Benachrichtigt den Profiler, dass ein Thread erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="878ab-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="878ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="878ab-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="878ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="878ab-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="878ab-106">in Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="878ab-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="878ab-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="878ab-107">Remarks</span></span>  

 <span data-ttu-id="878ab-108">Der `threadId` Wert ist sofort gültig.</span><span class="sxs-lookup"><span data-stu-id="878ab-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="878ab-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="878ab-109">Requirements</span></span>  

 <span data-ttu-id="878ab-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="878ab-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="878ab-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="878ab-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="878ab-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="878ab-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="878ab-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="878ab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="878ab-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="878ab-114">See also</span></span>

- [<span data-ttu-id="878ab-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="878ab-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="878ab-116">ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="878ab-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
