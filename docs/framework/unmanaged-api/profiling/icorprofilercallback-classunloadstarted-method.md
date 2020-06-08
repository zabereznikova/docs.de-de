---
title: ICorProfilerCallback::ClassUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 86402abca5386f34256f1f44f674f1e1898ad5fd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500350"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="2a6d6-102">ICorProfilerCallback::ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="2a6d6-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="2a6d6-103">Benachrichtigt den Profiler, dass eine Klasse entladen wird.</span><span class="sxs-lookup"><span data-stu-id="2a6d6-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a6d6-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a6d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a6d6-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="2a6d6-106">\[in] identifiziert die Klasse, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="2a6d6-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a6d6-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2a6d6-107">Remarks</span></span>  
 <span data-ttu-id="2a6d6-108">Der Wert von `classId` ist für eine Informationsanforderung nach dem `ClassUnloadStarted` zurückkehren der Methode ungültig – Dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2a6d6-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a6d6-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2a6d6-109">Requirements</span></span>  
 <span data-ttu-id="2a6d6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a6d6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a6d6-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a6d6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a6d6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a6d6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a6d6-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a6d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6d6-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2a6d6-114">See also</span></span>

- [<span data-ttu-id="2a6d6-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a6d6-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2a6d6-116">ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="2a6d6-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
