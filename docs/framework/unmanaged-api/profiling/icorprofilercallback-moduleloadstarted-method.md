---
title: ICorProfilerCallback::ModuleLoadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
ms.openlocfilehash: 6fbd009b5785c5dc78df81e4411fbdf8e8eadf71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730330"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="c3378-102">ICorProfilerCallback::ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="c3378-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>

<span data-ttu-id="c3378-103">Benachrichtigt den Profiler, dass ein Modul geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c3378-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3378-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3378-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3378-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3378-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="c3378-106">in Die ID des Moduls, das geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c3378-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3378-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3378-107">Remarks</span></span>  

 <span data-ttu-id="c3378-108">Der Wert von `moduleId` ist für eine Informationsanforderung erst gültig, wenn die [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c3378-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3378-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c3378-109">Requirements</span></span>  

 <span data-ttu-id="c3378-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3378-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3378-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3378-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3378-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3378-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3378-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3378-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3378-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3378-114">See also</span></span>

- [<span data-ttu-id="c3378-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3378-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
