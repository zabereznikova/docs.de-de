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
ms.openlocfilehash: 680bd351a64632e67432ee03352ee7caa8f4b2d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780387"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="7e455-102">ICorProfilerCallback9::DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="7e455-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="7e455-103">[Wird nur in .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="7e455-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="7e455-104">Benachrichtigt den Profiler an, wenn eine dynamische Methode Garbage Collector gesammelt und anschließend entladen wird.</span><span class="sxs-lookup"><span data-stu-id="7e455-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e455-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e455-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e455-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e455-106">Parameters</span></span>  
<span data-ttu-id="7e455-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="7e455-107">[in] `functionId`</span></span>  
<span data-ttu-id="7e455-108">Der Bezeichner der in-Memory-Funktion, die Garbage Collector gesammelt und entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7e455-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="7e455-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e455-109">Requirements</span></span>  
 <span data-ttu-id="7e455-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e455-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e455-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e455-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e455-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e455-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e455-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7e455-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e455-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e455-114">See also</span></span>

- [<span data-ttu-id="7e455-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="7e455-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="7e455-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="7e455-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="7e455-117">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e455-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="7e455-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="7e455-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
