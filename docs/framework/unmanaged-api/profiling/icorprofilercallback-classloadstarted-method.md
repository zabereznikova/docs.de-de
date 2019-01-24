---
title: ICorProfilerCallback::ClassLoadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a10ea7b257059d2b3177698e8d663a0c28e262b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737071"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="04ac4-102">ICorProfilerCallback::ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="04ac4-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="04ac4-103">Benachrichtigt den Profiler, dass eine Klasse geladen wird.</span><span class="sxs-lookup"><span data-stu-id="04ac4-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ac4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04ac4-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04ac4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="04ac4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="04ac4-106">[in] Identifiziert die Klasse, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="04ac4-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04ac4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04ac4-107">Remarks</span></span>  
 <span data-ttu-id="04ac4-108">Der Wert des `classId` gilt nicht für eine Anforderung von Informationen bis der [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="04ac4-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04ac4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04ac4-109">Requirements</span></span>  
 <span data-ttu-id="04ac4-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04ac4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04ac4-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04ac4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04ac4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04ac4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04ac4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04ac4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ac4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04ac4-114">See also</span></span>
- [<span data-ttu-id="04ac4-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04ac4-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
