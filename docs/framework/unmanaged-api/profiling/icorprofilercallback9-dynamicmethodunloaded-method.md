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
ms.openlocfilehash: 0eb38c83e9ab706c96bdef971f0bf17cc096822b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177032"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="f1479-102">ICorProfilerCallback9::DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="f1479-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="f1479-103">[Unterstützt in .NET Framework 4.7.2 und neueren Versionen]</span><span class="sxs-lookup"><span data-stu-id="f1479-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="f1479-104">Benachrichtigt den Profiler, wenn eine dynamische Methode Garbage Collection und anschließend es entladen wird.</span><span class="sxs-lookup"><span data-stu-id="f1479-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1479-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1479-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1479-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1479-106">Parameters</span></span>  
<span data-ttu-id="f1479-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="f1479-107">[in] `functionId`</span></span>  
<span data-ttu-id="f1479-108">Der Bezeichner der In-Memory-Funktion, die garbage collected and unloaded wurde.</span><span class="sxs-lookup"><span data-stu-id="f1479-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1479-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1479-109">Requirements</span></span>  
 <span data-ttu-id="f1479-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1479-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1479-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1479-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1479-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1479-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1479-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f1479-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1479-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1479-114">See also</span></span>

- [<span data-ttu-id="f1479-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="f1479-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="f1479-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="f1479-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="f1479-117">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1479-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="f1479-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="f1479-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
