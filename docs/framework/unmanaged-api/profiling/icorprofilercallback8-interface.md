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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455282"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="b0ff0-102">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0ff0-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="b0ff0-103">[Wird nur in .NET Framework 4.7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b0ff0-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="b0ff0-104">Eine Unterklasse von [ICorProfilerCallback7](icorprofilercallback7-interface.md) Rückrufmethoden, die von der common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, die gestartet und beendet JIT-Kompilierung einer dynamischen Methode bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b0ff0-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="b0ff0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b0ff0-105">Methods</span></span>  
  
|<span data-ttu-id="b0ff0-106">Methode</span><span class="sxs-lookup"><span data-stu-id="b0ff0-106">Method</span></span>|<span data-ttu-id="b0ff0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0ff0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0ff0-108">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b0ff0-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="b0ff0-109">Benachrichtigt den Profiler, dass JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b0ff0-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="b0ff0-110">DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="b0ff0-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="b0ff0-111">Benachrichtigt den Profiler, dass JIT-Kompilierung einer dynamischen Methode abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b0ff0-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0ff0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0ff0-112">Requirements</span></span>  
 <span data-ttu-id="b0ff0-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0ff0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0ff0-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0ff0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="b0ff0-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b0ff0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b0ff0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0ff0-116">See Also</span></span>  
<span data-ttu-id="b0ff0-117">[Profilerstellungsschnittstellen](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="b0ff0-117">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
[<span data-ttu-id="b0ff0-118">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0ff0-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
