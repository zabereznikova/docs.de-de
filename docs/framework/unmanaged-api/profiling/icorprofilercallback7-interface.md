---
title: ICorProfilerCallback7-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81477010b22edee71098edfc1b8557db08b6038f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178632"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="bffe1-102">ICorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bffe1-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="bffe1-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="bffe1-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="bffe1-104">Eine Unterklasse von [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) , die eine Rückrufmethode bereitstellt, über die die Common Language Runtime den Profiler benachrichtigt, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bffe1-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bffe1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bffe1-105">Methods</span></span>  
  
|<span data-ttu-id="bffe1-106">Methode</span><span class="sxs-lookup"><span data-stu-id="bffe1-106">Method</span></span>|<span data-ttu-id="bffe1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bffe1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bffe1-108">ModuleInMemorySymbolsUpdated-Methode</span><span class="sxs-lookup"><span data-stu-id="bffe1-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="bffe1-109">Benachrichtigt den Profiler, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bffe1-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bffe1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bffe1-110">Requirements</span></span>  
 <span data-ttu-id="bffe1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bffe1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bffe1-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bffe1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="bffe1-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="bffe1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bffe1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bffe1-114">See also</span></span>

- [<span data-ttu-id="bffe1-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bffe1-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
