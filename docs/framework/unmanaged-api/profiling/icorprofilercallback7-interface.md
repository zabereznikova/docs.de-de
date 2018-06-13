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
ms.openlocfilehash: f681001b610f42fef28181ffe3b47d702aabdf6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452690"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="36b72-102">ICorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36b72-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="36b72-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="36b72-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="36b72-104">Eine Unterklasse von [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) , die eine Rückrufmethode bereitstellt, über die die Common Language Runtime den Profiler benachrichtigt, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="36b72-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36b72-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="36b72-105">Methods</span></span>  
  
|<span data-ttu-id="36b72-106">Methode</span><span class="sxs-lookup"><span data-stu-id="36b72-106">Method</span></span>|<span data-ttu-id="36b72-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36b72-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36b72-108">ModuleInMemorySymbolsUpdated-Methode</span><span class="sxs-lookup"><span data-stu-id="36b72-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="36b72-109">Benachrichtigt den Profiler, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="36b72-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36b72-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36b72-110">Requirements</span></span>  
 <span data-ttu-id="36b72-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36b72-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36b72-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36b72-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36b72-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36b72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b72-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36b72-114">See Also</span></span>  
 [<span data-ttu-id="36b72-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="36b72-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
