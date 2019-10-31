---
title: ICorProfilerCallback9::D ynamicmethodunloaded-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 05a788179ff40a6889ed613b5f8659dd3f8e066f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196323"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="643f8-102">ICorProfilerCallback9::D ynamicmethodunloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="643f8-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="643f8-103">[Wird in der .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="643f8-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="643f8-104">Benachrichtigt den Profiler, wenn eine dynamische Methode in eine Garbage Collection und anschließend entladen wird.</span><span class="sxs-lookup"><span data-stu-id="643f8-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="643f8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="643f8-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="643f8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="643f8-106">Parameters</span></span>  
<span data-ttu-id="643f8-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="643f8-107">[in] `functionId`</span></span>  
<span data-ttu-id="643f8-108">Der Bezeichner der in-Memory-Funktion, die in den Garbage Collection-und entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="643f8-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="643f8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="643f8-109">Requirements</span></span>  
 <span data-ttu-id="643f8-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="643f8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="643f8-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="643f8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="643f8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="643f8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="643f8-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="643f8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643f8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="643f8-114">See also</span></span>

- [<span data-ttu-id="643f8-115">ICorProfilerCallback8. dynamicmethodjitcompilationstarted-Methode</span><span class="sxs-lookup"><span data-stu-id="643f8-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="643f8-116">ICorProfilerCallback8. dynamicmethodjitcompilationabgeschlossene-Methode</span><span class="sxs-lookup"><span data-stu-id="643f8-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="643f8-117">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="643f8-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="643f8-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="643f8-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
