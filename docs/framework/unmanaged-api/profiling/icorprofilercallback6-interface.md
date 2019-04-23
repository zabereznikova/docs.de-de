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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077237"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="b11f6-102">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b11f6-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="b11f6-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b11f6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b11f6-104">Eine Unterklasse von [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) , die stellt einer Rückrufmethode, die die common Language Runtime verwendet, um einen Profiler zu benachrichtigen, die eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b11f6-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b11f6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b11f6-105">Methods</span></span>  
  
|<span data-ttu-id="b11f6-106">Methode</span><span class="sxs-lookup"><span data-stu-id="b11f6-106">Method</span></span>|<span data-ttu-id="b11f6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b11f6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b11f6-108">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="b11f6-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="b11f6-109">Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.</span><span class="sxs-lookup"><span data-stu-id="b11f6-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b11f6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b11f6-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b11f6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b11f6-111">Requirements</span></span>  
 <span data-ttu-id="b11f6-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b11f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b11f6-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b11f6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b11f6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b11f6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b11f6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b11f6-115">See also</span></span>

- [<span data-ttu-id="b11f6-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b11f6-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
