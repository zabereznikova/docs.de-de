---
title: ICorProfilerCallback::ClassLoadStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f1622fdbbeb1f200f996e49c432600165a029aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="8aa2a-102">ICorProfilerCallback::ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="8aa2a-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="8aa2a-103">Benachrichtigt den Profiler, dass eine Klasse geladen wird.</span><span class="sxs-lookup"><span data-stu-id="8aa2a-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aa2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8aa2a-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8aa2a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8aa2a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="8aa2a-106">[in] Identifiziert die Klasse, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="8aa2a-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8aa2a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8aa2a-107">Remarks</span></span>  
 <span data-ttu-id="8aa2a-108">Der Wert der `classId` gilt nicht für eine Anforderung Informationen, bis die [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8aa2a-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aa2a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8aa2a-109">Requirements</span></span>  
 <span data-ttu-id="8aa2a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aa2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aa2a-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8aa2a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8aa2a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8aa2a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aa2a-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aa2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa2a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8aa2a-114">See Also</span></span>  
 [<span data-ttu-id="8aa2a-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8aa2a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
