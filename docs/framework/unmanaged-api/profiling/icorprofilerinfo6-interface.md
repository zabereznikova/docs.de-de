---
title: ICorProfilerInfo6-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041118"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="c377e-102">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c377e-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="c377e-103">[Wird nur in der .NET Framework 4.6 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="c377e-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="c377e-104">Eine Unterklasse von [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) , die stellt eines Enumerators für alle Methoden, die in einem bestimmten NGen-Modul und Inline einer bestimmten Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c377e-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c377e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c377e-105">Methods</span></span>  
  
|<span data-ttu-id="c377e-106">Methode</span><span class="sxs-lookup"><span data-stu-id="c377e-106">Method</span></span>|<span data-ttu-id="c377e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c377e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c377e-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="c377e-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="c377e-109">Gibt einen Enumerator für alle Methoden, die ein bestimmtes NGen-Modul gehören, und im Text einer bestimmten Methode Inline sind.</span><span class="sxs-lookup"><span data-stu-id="c377e-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c377e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c377e-110">Requirements</span></span>  
 <span data-ttu-id="c377e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c377e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c377e-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c377e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c377e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c377e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c377e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c377e-114">See also</span></span>

- [<span data-ttu-id="c377e-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c377e-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
