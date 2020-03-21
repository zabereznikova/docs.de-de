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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175095"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="974ad-102">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="974ad-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="974ad-103">[Unterstützt in .NET Framework 4.7 und neueren Versionen]</span><span class="sxs-lookup"><span data-stu-id="974ad-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="974ad-104">Eine Unterklasse von [ICorProfilerCallback7,](icorprofilercallback7-interface.md) die Rückrufmethoden bereitstellt, die von der Common Language Runtime verwendet werden, um den Profiler darüber zu informieren, dass die JIT-Kompilierung einer dynamischen Methode gestartet und abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="974ad-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="974ad-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="974ad-105">Methods</span></span>  
  
|<span data-ttu-id="974ad-106">Methode</span><span class="sxs-lookup"><span data-stu-id="974ad-106">Method</span></span>|<span data-ttu-id="974ad-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="974ad-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="974ad-108">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="974ad-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="974ad-109">Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="974ad-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="974ad-110">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="974ad-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="974ad-111">Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="974ad-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="974ad-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="974ad-112">Requirements</span></span>  
 <span data-ttu-id="974ad-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="974ad-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="974ad-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="974ad-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="974ad-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="974ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="974ad-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="974ad-116">See also</span></span>

- [<span data-ttu-id="974ad-117">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="974ad-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="974ad-118">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="974ad-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
