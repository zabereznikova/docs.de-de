---
title: ICorProfilerInfo::GetInprocInspectionIThisThread-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionIThisThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c36688af3ab8941a7004061add8598a480f3e202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="a045d-102">ICorProfilerInfo::GetInprocInspectionIThisThread-Methode</span><span class="sxs-lookup"><span data-stu-id="a045d-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="a045d-103">Ruft ein Objekt, das abgefragt werden kann, für die ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a045d-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="a045d-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="a045d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a045d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a045d-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a045d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a045d-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="a045d-107">[out](/cpp/atl/iunknown) -Objekt, das abgefragt werden kann die `ICorDebugThread` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a045d-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a045d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a045d-108">Remarks</span></span>  
 <span data-ttu-id="a045d-109">Debugdiensten der common Language Runtime (CLR) unterstützten beschränkt prozessinternes Debuggen in .NET Framework, Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="a045d-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="a045d-110">Prozessinternes Debuggen aktiviert einen Profiler an die Inspektionsteile der Debug-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="a045d-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="a045d-111">Aufgrund von Kundenfeedback wurde prozessinternes Debuggen aus .NET Framework Version 2.0 entfernt, und durch eine Reihe von Funktionen, die mehrere im Einklang mit den die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a045d-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a045d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a045d-112">Requirements</span></span>  
 <span data-ttu-id="a045d-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a045d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a045d-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a045d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a045d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a045d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a045d-116">**.NET Framework-Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="a045d-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a045d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a045d-117">See Also</span></span>  
 [<span data-ttu-id="a045d-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a045d-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
