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
ms.openlocfilehash: 9a49d8e1ff31942c6564ab560d6726b9ede26466
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499141"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="9699a-102">ICorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9699a-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="9699a-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="9699a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="9699a-104">Eine Unterklasse von [ICorProfilerCallback6](icorprofilercallback6-interface.md) , die eine Rückrufmethode bereitstellt, über die die Common Language Runtime den Profiler benachrichtigt, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="9699a-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9699a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9699a-105">Methods</span></span>  
  
|<span data-ttu-id="9699a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9699a-106">Method</span></span>|<span data-ttu-id="9699a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9699a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9699a-108">ModuleInMemorySymbolsUpdated-Methode</span><span class="sxs-lookup"><span data-stu-id="9699a-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="9699a-109">Benachrichtigt den Profiler, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="9699a-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9699a-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9699a-110">Requirements</span></span>  
 <span data-ttu-id="9699a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9699a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9699a-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9699a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9699a-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9699a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9699a-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9699a-114">See also</span></span>

- [<span data-ttu-id="9699a-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9699a-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
