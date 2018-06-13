---
title: ICorProfilerCallback9-Schnittstelle
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452376"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="de8e1-102">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de8e1-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="de8e1-103">[Wird nur in .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="de8e1-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="de8e1-104">Eine Unterklasse von [ICorProfilerCallback8](icorprofilercallback8-interface.md) , der eine Rückrufmethode, die von der common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass eine dynamische Methode eine Garbage Collection gesammelt und anschließend entladen wurde bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="de8e1-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de8e1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="de8e1-105">Methods</span></span>  
  
|<span data-ttu-id="de8e1-106">Methode</span><span class="sxs-lookup"><span data-stu-id="de8e1-106">Method</span></span>|<span data-ttu-id="de8e1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de8e1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de8e1-108">DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="de8e1-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="de8e1-109">Benachrichtigt den Profiler, dass eine dynamische Methode eine Garbage Collection gesammelt und anschließend entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="de8e1-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de8e1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de8e1-110">Requirements</span></span>  
 <span data-ttu-id="de8e1-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de8e1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de8e1-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de8e1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="de8e1-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="de8e1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="de8e1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de8e1-114">See Also</span></span>  
<span data-ttu-id="de8e1-115">[Profilerstellungsschnittstellen](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="de8e1-115">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
<span data-ttu-id="de8e1-116">[ICorProfilerCallback8-Schnittstelle](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="de8e1-116">[ICorProfilerCallback8 Interface](icorprofilercallback9-interface.md) </span></span>  
<span data-ttu-id="de8e1-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span><span class="sxs-lookup"><span data-stu-id="de8e1-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted method](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span></span>  
[<span data-ttu-id="de8e1-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="de8e1-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
