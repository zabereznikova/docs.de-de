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
ms.openlocfilehash: e536e61a8d812e442e1e54188c99d6a1d4586757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125566"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="b3d4c-102">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3d4c-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="b3d4c-103">[Wird nur in der .NET Framework 4.7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b3d4c-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="b3d4c-104">Eine Unterklasse von [ICorProfilerCallback7](icorprofilercallback7-interface.md) , die Rückrufmethoden, die von der common Language Runtime verwendet wird, um den Profiler zu benachrichtigen, die JIT-Kompilierung einer dynamischen Methode gestartet und beendet bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b3d4c-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="b3d4c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b3d4c-105">Methods</span></span>  
  
|<span data-ttu-id="b3d4c-106">Methode</span><span class="sxs-lookup"><span data-stu-id="b3d4c-106">Method</span></span>|<span data-ttu-id="b3d4c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3d4c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3d4c-108">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b3d4c-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="b3d4c-109">Benachrichtigt den Profiler an, dass JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b3d4c-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="b3d4c-110">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b3d4c-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="b3d4c-111">Benachrichtigt den Profiler an, die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b3d4c-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3d4c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3d4c-112">Requirements</span></span>  
 <span data-ttu-id="b3d4c-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3d4c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3d4c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3d4c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
**<span data-ttu-id="b3d4c-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b3d4c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="b3d4c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3d4c-116">See also</span></span>

- [<span data-ttu-id="b3d4c-117">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b3d4c-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b3d4c-118">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3d4c-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
