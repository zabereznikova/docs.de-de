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
ms.openlocfilehash: 75fb92be078c40f49ddcdc6662535b2a0be7a6ad
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866558"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="e427e-102">ICorProfilerCallback::ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="e427e-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="e427e-103">Benachrichtigt den Profiler, dass eine Klasse entladen wird.</span><span class="sxs-lookup"><span data-stu-id="e427e-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e427e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e427e-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e427e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e427e-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="e427e-106">\[in] identifiziert die Klasse, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="e427e-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="e427e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e427e-107">Remarks</span></span>  
 <span data-ttu-id="e427e-108">Der Wert `classId` ist für eine Informationsanforderung nicht gültig, nachdem die `ClassUnloadStarted`-Methode zurückgegeben wurde – dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e427e-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e427e-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e427e-109">Requirements</span></span>  
 <span data-ttu-id="e427e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e427e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e427e-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e427e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e427e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e427e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e427e-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e427e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e427e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e427e-114">See also</span></span>

- [<span data-ttu-id="e427e-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e427e-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e427e-116">ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="e427e-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
