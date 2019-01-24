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
ms.openlocfilehash: a6c480af921fb0259ef85beec8d8f65bdd430522
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689309"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="219e8-102">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="219e8-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="219e8-103">[Wird nur in .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="219e8-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="219e8-104">Eine Unterklasse von [ICorProfilerCallback8](icorprofilercallback8-interface.md) , der eine Rückrufmethode, die von der common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass eine dynamische Methode Garbage Collector gesammelt und anschließend entladen wurde bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="219e8-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="219e8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="219e8-105">Methods</span></span>  
  
|<span data-ttu-id="219e8-106">Methode</span><span class="sxs-lookup"><span data-stu-id="219e8-106">Method</span></span>|<span data-ttu-id="219e8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="219e8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="219e8-108">DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="219e8-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="219e8-109">Benachrichtigt den Profiler, dass eine dynamische Methode Garbage Collector gesammelt und anschließend entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="219e8-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="219e8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="219e8-110">Requirements</span></span>  
 <span data-ttu-id="219e8-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="219e8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="219e8-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="219e8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="219e8-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="219e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="219e8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="219e8-114">See also</span></span>
- [<span data-ttu-id="219e8-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="219e8-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="219e8-116">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="219e8-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="219e8-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="219e8-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="219e8-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="219e8-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
