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
ms.openlocfilehash: e61f6a104b8b9613db32ed6912395fd07c18dcff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864816"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="23da9-102">ICorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23da9-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="23da9-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="23da9-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="23da9-104">Eine Unterklasse von [ICorProfilerCallback6](icorprofilercallback6-interface.md) , die eine Rückrufmethode bereitstellt, über die die Common Language Runtime den Profiler benachrichtigt, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="23da9-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23da9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="23da9-105">Methods</span></span>  
  
|<span data-ttu-id="23da9-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="23da9-106">Method</span></span>|<span data-ttu-id="23da9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23da9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23da9-108">ModuleInMemorySymbolsUpdated-Methode</span><span class="sxs-lookup"><span data-stu-id="23da9-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="23da9-109">Benachrichtigt den Profiler, dass der Symbolstream aktualisiert wird, der einem In-Memory-Modul zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="23da9-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23da9-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23da9-110">Requirements</span></span>  
 <span data-ttu-id="23da9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23da9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23da9-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23da9-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23da9-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23da9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23da9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23da9-114">See also</span></span>

- [<span data-ttu-id="23da9-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="23da9-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
