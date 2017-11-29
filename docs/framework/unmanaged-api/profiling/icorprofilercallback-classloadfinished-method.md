---
title: ICorProfilerCallback::ClassLoadFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3f321849c62ffd653ffa174ff91447a2c8eec73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="347a1-102">ICorProfilerCallback::ClassLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="347a1-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="347a1-103">Benachrichtigt den Profiler, dass eine Klasse vollständig geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="347a1-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="347a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="347a1-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="347a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="347a1-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="347a1-106">[in] Identifiziert die Klasse, die geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="347a1-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="347a1-107">[in] Ein HRESULT, das angibt, ob die Klasse erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="347a1-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="347a1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="347a1-108">Remarks</span></span>  
 <span data-ttu-id="347a1-109">Der Wert der `classId` gilt nicht für eine Anforderung Informationen, bis die `ClassLoadFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="347a1-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="347a1-110">Einige Teile der Laden der Klasse möglicherweise weiterhin nach dem `ClassLoadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="347a1-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="347a1-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="347a1-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="347a1-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Ladevorgangs für die Klasse erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="347a1-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="347a1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="347a1-113">Requirements</span></span>  
 <span data-ttu-id="347a1-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="347a1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="347a1-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="347a1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="347a1-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="347a1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="347a1-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="347a1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="347a1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="347a1-118">See Also</span></span>  
 [<span data-ttu-id="347a1-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="347a1-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="347a1-120">ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="347a1-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
