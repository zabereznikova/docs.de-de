---
title: ICorProfilerCallback2::HandleDestroyed-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
ms.openlocfilehash: 06064d82e5f572de08e56fd83923134a94d5e77b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731929"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="e3ab6-102">ICorProfilerCallback2::HandleDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="e3ab6-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>

<span data-ttu-id="e3ab6-103">Benachrichtigt den Codeprofiler, dass ein Garbage Collection Handle zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="e3ab6-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ab6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3ab6-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3ab6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3ab6-105">Parameters</span></span>  

 `handleId`  
 <span data-ttu-id="e3ab6-106">in Die ID des Handles für die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e3ab6-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3ab6-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e3ab6-107">Requirements</span></span>  

 <span data-ttu-id="e3ab6-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3ab6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3ab6-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3ab6-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3ab6-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3ab6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3ab6-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3ab6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ab6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3ab6-112">See also</span></span>

- [<span data-ttu-id="e3ab6-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3ab6-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e3ab6-114">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3ab6-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
