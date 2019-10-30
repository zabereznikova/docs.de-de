---
title: ICorProfilerCallback8-Schnittstelle
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4516c8f9673052b521c1f0f594978236fef1e0ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136456"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="eb0eb-102">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb0eb-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="eb0eb-103">[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="eb0eb-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="eb0eb-104">Eine Unterklasse von [ICorProfilerCallback7](icorprofilercallback7-interface.md) , die Rückruf Methoden bereitstellt, die vom Common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass die JIT-Kompilierung einer dynamischen Methode gestartet und beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="eb0eb-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="eb0eb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="eb0eb-105">Methods</span></span>  
  
|<span data-ttu-id="eb0eb-106">Methode</span><span class="sxs-lookup"><span data-stu-id="eb0eb-106">Method</span></span>|<span data-ttu-id="eb0eb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb0eb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb0eb-108">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="eb0eb-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="eb0eb-109">Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="eb0eb-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="eb0eb-110">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="eb0eb-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="eb0eb-111">Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="eb0eb-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb0eb-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb0eb-112">Requirements</span></span>  
 <span data-ttu-id="eb0eb-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb0eb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb0eb-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb0eb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="eb0eb-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eb0eb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="eb0eb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb0eb-116">See also</span></span>

- [<span data-ttu-id="eb0eb-117">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="eb0eb-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="eb0eb-118">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb0eb-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
