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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c30fb5d5576a7bed403f48504ead923df212de9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450374"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="5dbe4-102">ICorProfilerCallback::ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="5dbe4-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="5dbe4-103">Benachrichtigt den Profiler, dass eine Klasse entladen wird.</span><span class="sxs-lookup"><span data-stu-id="5dbe4-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dbe4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dbe4-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5dbe4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5dbe4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5dbe4-106">[in] Identifiziert die Klasse, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="5dbe4-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dbe4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5dbe4-107">Remarks</span></span>  
 <span data-ttu-id="5dbe4-108">Der Wert der `classId` gilt nicht für eine Anforderung Informationen nach der `ClassUnloadStarted` -Methode zurückkehrt – Dies ist der Profiler die letzte Möglichkeit zum Abrufen von Informationen zu dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="5dbe4-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dbe4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5dbe4-109">Requirements</span></span>  
 <span data-ttu-id="5dbe4-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dbe4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dbe4-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5dbe4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5dbe4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dbe4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5dbe4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dbe4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dbe4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dbe4-114">See Also</span></span>  
 [<span data-ttu-id="5dbe4-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5dbe4-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="5dbe4-116">ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="5dbe4-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
