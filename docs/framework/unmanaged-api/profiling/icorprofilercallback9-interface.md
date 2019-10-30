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
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136563"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="60015-102">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60015-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="60015-103">[Wird in der .NET Framework 4.7.2 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="60015-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="60015-104">Eine Unterklasse von [ICorProfilerCallback8](icorprofilercallback8-interface.md) , die eine Rückruf Methode bereitstellt, die vom Common Language Runtime verwendet wird, um den Profiler zu benachrichtigen, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="60015-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60015-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="60015-105">Methods</span></span>  
  
|<span data-ttu-id="60015-106">Methode</span><span class="sxs-lookup"><span data-stu-id="60015-106">Method</span></span>|<span data-ttu-id="60015-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60015-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60015-108">DynamicMethodUnloaded-Methode</span><span class="sxs-lookup"><span data-stu-id="60015-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="60015-109">Benachrichtigt den Profiler, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="60015-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60015-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60015-110">Requirements</span></span>  
 <span data-ttu-id="60015-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60015-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60015-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60015-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="60015-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="60015-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="60015-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60015-114">See also</span></span>

- [<span data-ttu-id="60015-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="60015-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="60015-116">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60015-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="60015-117">ICorProfilerCallback8. dynamicmethodjitcompilationstarted-Methode</span><span class="sxs-lookup"><span data-stu-id="60015-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="60015-118">ICorProfilerCallback8. dynamicmethodjitcompilationabgeschlossene-Methode</span><span class="sxs-lookup"><span data-stu-id="60015-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
