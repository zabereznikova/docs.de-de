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
ms.openlocfilehash: 0156a7dfa2a67ce9e62b502df00fc6bc5fccf925
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499180"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="9ce7d-102">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ce7d-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="9ce7d-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="9ce7d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="9ce7d-104">Eine Unterklasse von [ICorProfilerCallback5](icorprofilercallback5-interface.md) , die eine Rückruf Methode bereitstellt, die der Common Language Runtime verwendet, um einen Profiler zu benachrichtigen, dass eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9ce7d-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ce7d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9ce7d-105">Methods</span></span>  
  
|<span data-ttu-id="9ce7d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9ce7d-106">Method</span></span>|<span data-ttu-id="9ce7d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9ce7d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ce7d-108">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="9ce7d-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="9ce7d-109">Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.</span><span class="sxs-lookup"><span data-stu-id="9ce7d-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ce7d-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9ce7d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ce7d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9ce7d-111">Requirements</span></span>  
 <span data-ttu-id="9ce7d-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ce7d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ce7d-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ce7d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ce7d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ce7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce7d-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9ce7d-115">See also</span></span>

- [<span data-ttu-id="9ce7d-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9ce7d-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
