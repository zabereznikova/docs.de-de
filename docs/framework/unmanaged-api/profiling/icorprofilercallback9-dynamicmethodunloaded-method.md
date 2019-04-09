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
ms.openlocfilehash: 96cdfb79c1573648173305d6ee789aa8db030ff8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211009"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="345ce-102">ICorProfilerCallback9::DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="345ce-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="345ce-103">[Wird nur in .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="345ce-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="345ce-104">Benachrichtigt den Profiler an, wenn eine dynamische Methode Garbage Collector gesammelt und anschließend entladen wird.</span><span class="sxs-lookup"><span data-stu-id="345ce-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="345ce-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="345ce-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="345ce-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="345ce-106">Parameters</span></span>  
<span data-ttu-id="345ce-107">[in]</span><span class="sxs-lookup"><span data-stu-id="345ce-107">[in]</span></span> `functionId`  
<span data-ttu-id="345ce-108">Der Bezeichner der in-Memory-Funktion, die Garbage Collector gesammelt und entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="345ce-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="345ce-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="345ce-109">Requirements</span></span>  
 <span data-ttu-id="345ce-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="345ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="345ce-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="345ce-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="345ce-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="345ce-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="345ce-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="345ce-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="345ce-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="345ce-114">See also</span></span>

- [<span data-ttu-id="345ce-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="345ce-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="345ce-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="345ce-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="345ce-117">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="345ce-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="345ce-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="345ce-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
