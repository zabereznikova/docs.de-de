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
ms.openlocfilehash: 23b91a2a58c6e76b31b94e0fa3661dfbc8e18e33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712767"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="42dcb-102">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42dcb-102">ICorProfilerCallback9 Interface</span></span>

<span data-ttu-id="42dcb-103">[Wird in der .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="42dcb-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="42dcb-104">Eine Unterklasse von [ICorProfilerCallback8](icorprofilercallback8-interface.md) , die eine Rückruf Methode bereitstellt, die vom Common Language Runtime verwendet wird, um den Profiler zu benachrichtigen, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="42dcb-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42dcb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="42dcb-105">Methods</span></span>  
  
|<span data-ttu-id="42dcb-106">Methode</span><span class="sxs-lookup"><span data-stu-id="42dcb-106">Method</span></span>|<span data-ttu-id="42dcb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42dcb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42dcb-108">DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="42dcb-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="42dcb-109">Benachrichtigt den Profiler, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="42dcb-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42dcb-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="42dcb-110">Requirements</span></span>  

 <span data-ttu-id="42dcb-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42dcb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42dcb-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42dcb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="42dcb-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42dcb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="42dcb-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42dcb-114">See also</span></span>

- [<span data-ttu-id="42dcb-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="42dcb-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="42dcb-116">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42dcb-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="42dcb-117">ICorProfilerCallback8. dynamicmethodjitcompilationstarted-Methode</span><span class="sxs-lookup"><span data-stu-id="42dcb-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="42dcb-118">ICorProfilerCallback8. dynamicmethodjitcompilationabgeschlossene-Methode</span><span class="sxs-lookup"><span data-stu-id="42dcb-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
