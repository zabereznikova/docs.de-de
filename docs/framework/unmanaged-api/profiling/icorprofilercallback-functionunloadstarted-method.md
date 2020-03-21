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
ms.openlocfilehash: 988843559e55cc4cacd2a40bb3e6ac51721e99b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175160"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="2c427-102">ICorProfilerCallback::FunctionUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="2c427-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="2c427-103">Benachrichtigt den Profiler, dass die Laufzeit mit dem Entladen einer Funktion begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="2c427-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c427-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c427-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="2c427-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c427-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="2c427-106">\[in] Die ID der Funktion, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="2c427-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c427-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2c427-107">Remarks</span></span>  
 <span data-ttu-id="2c427-108">Der Wert `functionId` des Parameters ist nicht mehr gültig, nachdem diese Methode an den Aufrufer zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2c427-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c427-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2c427-109">Requirements</span></span>  
 <span data-ttu-id="2c427-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c427-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c427-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c427-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c427-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c427-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c427-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c427-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c427-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c427-114">See also</span></span>

- [<span data-ttu-id="2c427-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c427-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
