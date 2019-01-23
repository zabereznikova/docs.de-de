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
ms.openlocfilehash: c5025f4bb6433d193ecf7dec1d8375104147e9e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562569"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="a2f2c-102">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2f2c-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="a2f2c-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="a2f2c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a2f2c-104">Eine Unterklasse von [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) , die stellt einer Rückrufmethode, die die common Language Runtime verwendet, um einen Profiler zu benachrichtigen, die eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2f2c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a2f2c-105">Methods</span></span>  
  
|<span data-ttu-id="a2f2c-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a2f2c-106">Method</span></span>|<span data-ttu-id="a2f2c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2f2c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2f2c-108">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="a2f2c-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="a2f2c-109">Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.</span><span class="sxs-lookup"><span data-stu-id="a2f2c-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2f2c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2f2c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f2c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2f2c-111">Requirements</span></span>  
 <span data-ttu-id="a2f2c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2f2c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f2c-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2f2c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a2f2c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f2c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f2c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2f2c-115">See also</span></span>
- [<span data-ttu-id="a2f2c-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2f2c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
