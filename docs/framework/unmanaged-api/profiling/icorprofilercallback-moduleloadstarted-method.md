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
ms.openlocfilehash: 88da5a968bf224dc5b6f45ee5d1d2e75386086f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866155"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="a046a-102">ICorProfilerCallback::ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="a046a-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="a046a-103">Benachrichtigt den Profiler, dass ein Modul geladen wird.</span><span class="sxs-lookup"><span data-stu-id="a046a-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a046a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a046a-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a046a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a046a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a046a-106">in Die ID des Moduls, das geladen wird.</span><span class="sxs-lookup"><span data-stu-id="a046a-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a046a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a046a-107">Remarks</span></span>  
 <span data-ttu-id="a046a-108">Der Wert von `moduleId` ist erst gültig für eine Informationsanforderung, wenn die [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a046a-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a046a-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a046a-109">Requirements</span></span>  
 <span data-ttu-id="a046a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a046a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a046a-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a046a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a046a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a046a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a046a-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a046a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a046a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a046a-114">See also</span></span>

- [<span data-ttu-id="a046a-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a046a-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
