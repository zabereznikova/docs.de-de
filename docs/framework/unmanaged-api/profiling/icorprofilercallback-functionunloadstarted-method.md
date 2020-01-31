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
ms.openlocfilehash: 2b228337a55d50b94da966b45877e2000b3c03e4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866311"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="8c28a-102">ICorProfilerCallback::FunctionUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="8c28a-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="8c28a-103">Benachrichtigt den Profiler, dass die Laufzeit begonnen hat, eine Funktion zu entladen.</span><span class="sxs-lookup"><span data-stu-id="8c28a-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c28a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c28a-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8c28a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8c28a-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="8c28a-106">\[in] die ID der Funktion, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="8c28a-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c28a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c28a-107">Remarks</span></span>  
 <span data-ttu-id="8c28a-108">Der Wert des `functionId`-Parameters ist nicht mehr gültig, nachdem diese Methode an den Aufrufer zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8c28a-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c28a-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c28a-109">Requirements</span></span>  
 <span data-ttu-id="8c28a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c28a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c28a-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c28a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c28a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c28a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c28a-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c28a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c28a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c28a-114">See also</span></span>

- [<span data-ttu-id="8c28a-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c28a-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
