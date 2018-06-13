---
title: ICorProfilerCallback9::DynamicMethodUnloaded-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452402"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="59b7d-102">ICorProfilerCallback9::DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="59b7d-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="59b7d-103">[Wird nur in .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="59b7d-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="59b7d-104">Benachrichtigt den Profiler an, wenn eine dynamische Methode Garbage Collection gesammelt und anschließend entladen wird.</span><span class="sxs-lookup"><span data-stu-id="59b7d-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b7d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="59b7d-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59b7d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="59b7d-106">Parameters</span></span>  
<span data-ttu-id="59b7d-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="59b7d-107">[in] `functionId`</span></span>  
<span data-ttu-id="59b7d-108">Der Bezeichner der in-Memory-Funktion, die eine Garbage Collection erfasst und entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="59b7d-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="59b7d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59b7d-109">Requirements</span></span>  
 <span data-ttu-id="59b7d-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59b7d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b7d-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59b7d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59b7d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59b7d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59b7d-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59b7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b7d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59b7d-114">See Also</span></span>  
[<span data-ttu-id="59b7d-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="59b7d-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[<span data-ttu-id="59b7d-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="59b7d-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
<span data-ttu-id="59b7d-117">[ICorProfilerCallback9-Schnittstelle](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="59b7d-117">[ICorProfilerCallback9 Interface](icorprofilercallback9-interface.md) </span></span>  
[<span data-ttu-id="59b7d-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="59b7d-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
