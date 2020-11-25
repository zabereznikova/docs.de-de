---
title: ICorProfilerCallback::FunctionUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: bab8d446347646081cee635035e954da58c3550c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733879"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="3f345-102">ICorProfilerCallback::FunctionUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="3f345-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="3f345-103">Benachrichtigt den Profiler, dass die Laufzeit begonnen hat, eine Funktion zu entladen.</span><span class="sxs-lookup"><span data-stu-id="3f345-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f345-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f345-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="3f345-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f345-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="3f345-106">\[in] die ID der Funktion, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="3f345-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f345-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f345-107">Remarks</span></span>  

 <span data-ttu-id="3f345-108">Der Wert des- `functionId` Parameters ist nicht mehr gültig, nachdem diese Methode an den Aufrufer zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3f345-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f345-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3f345-109">Requirements</span></span>  

 <span data-ttu-id="3f345-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f345-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f345-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f345-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f345-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f345-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f345-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f345-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f345-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f345-114">See also</span></span>

- [<span data-ttu-id="3f345-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f345-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
