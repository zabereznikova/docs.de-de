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
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732384"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="4e474-102">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e474-102">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="4e474-103">[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="4e474-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="4e474-104">Eine Unterklasse von [ICorProfilerCallback7](icorprofilercallback7-interface.md) , die Rückruf Methoden bereitstellt, die vom Common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass die JIT-Kompilierung einer dynamischen Methode gestartet und beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4e474-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="4e474-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4e474-105">Methods</span></span>  
  
|<span data-ttu-id="4e474-106">Methode</span><span class="sxs-lookup"><span data-stu-id="4e474-106">Method</span></span>|<span data-ttu-id="4e474-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4e474-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e474-108">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="4e474-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="4e474-109">Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="4e474-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="4e474-110">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="4e474-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="4e474-111">Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4e474-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e474-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4e474-112">Requirements</span></span>  

 <span data-ttu-id="4e474-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e474-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e474-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e474-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="4e474-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4e474-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4e474-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e474-116">See also</span></span>

- [<span data-ttu-id="4e474-117">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4e474-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4e474-118">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e474-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
