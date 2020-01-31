---
title: ICorProfilerCallback6-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 90071121411b706052e1cbb4cb647536dae2835a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864868"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="208d1-102">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="208d1-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="208d1-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="208d1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="208d1-104">Eine Unterklasse von [ICorProfilerCallback5](icorprofilercallback5-interface.md) , die eine Rückruf Methode bereitstellt, die der Common Language Runtime verwendet, um einen Profiler zu benachrichtigen, dass eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="208d1-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="208d1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="208d1-105">Methods</span></span>  
  
|<span data-ttu-id="208d1-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="208d1-106">Method</span></span>|<span data-ttu-id="208d1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="208d1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="208d1-108">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="208d1-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="208d1-109">Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.</span><span class="sxs-lookup"><span data-stu-id="208d1-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="208d1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="208d1-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="208d1-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="208d1-111">Requirements</span></span>  
 <span data-ttu-id="208d1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="208d1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="208d1-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="208d1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="208d1-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="208d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208d1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="208d1-115">See also</span></span>

- [<span data-ttu-id="208d1-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="208d1-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
