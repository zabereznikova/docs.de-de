---
title: ICorProfilerInfo3::EnumModules-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.EnumModules Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0215662439672aecc787530ceb68d16cc58bcc3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="4cb41-102">ICorProfilerInfo3::EnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="4cb41-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="4cb41-103">Gibt einen Enumerator zurück, der Methoden zum sequenziellen Iterieren durch eine Auflistung von verwalteten Modulen bereitstellt, die in die Anwendung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4cb41-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb41-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cb41-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cb41-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cb41-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4cb41-106">[out] Ein Zeiger auf ein [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4cb41-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cb41-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4cb41-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb41-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4cb41-108">Requirements</span></span>  
 <span data-ttu-id="4cb41-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb41-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb41-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cb41-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cb41-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb41-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb41-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb41-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb41-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cb41-113">See Also</span></span>  
 [<span data-ttu-id="4cb41-114">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cb41-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="4cb41-115">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cb41-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="4cb41-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4cb41-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="4cb41-117">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="4cb41-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
