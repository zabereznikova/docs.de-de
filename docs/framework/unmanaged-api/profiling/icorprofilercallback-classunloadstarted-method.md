---
title: ICorProfilerCallback::ClassUnloadStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0056d97e7cf8286291292f27e942b7a846efb3f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="d7f75-102">ICorProfilerCallback::ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="d7f75-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="d7f75-103">Benachrichtigt den Profiler, dass eine Klasse entladen wird.</span><span class="sxs-lookup"><span data-stu-id="d7f75-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7f75-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7f75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7f75-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d7f75-106">[in] Identifiziert die Klasse, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="d7f75-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f75-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7f75-107">Remarks</span></span>  
 <span data-ttu-id="d7f75-108">Der Wert der `classId` gilt nicht für eine Anforderung Informationen nach der `ClassUnloadStarted` -Methode zurückkehrt – Dies ist der Profiler die letzte Möglichkeit zum Abrufen von Informationen zu dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="d7f75-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f75-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7f75-109">Requirements</span></span>  
 <span data-ttu-id="d7f75-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f75-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7f75-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7f75-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7f75-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7f75-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f75-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7f75-114">See Also</span></span>  
 [<span data-ttu-id="d7f75-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7f75-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d7f75-116">ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="d7f75-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
