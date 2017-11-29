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
ms.openlocfilehash: 9a260143e36939f4201d7949f5783f80e5c20ba7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="2cdc6-102">ICorProfilerInfo::GetInprocInspectionIThisThread-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdc6-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="2cdc6-103">Ruft ein Objekt, das abgefragt werden kann, für die ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2cdc6-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="2cdc6-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="2cdc6-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cdc6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cdc6-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cdc6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cdc6-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="2cdc6-107">[out](/cpp/atl/iunknown) -Objekt, das abgefragt werden kann die `ICorDebugThread` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2cdc6-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cdc6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cdc6-108">Remarks</span></span>  
 <span data-ttu-id="2cdc6-109">Debugdiensten der common Language Runtime (CLR) unterstützten beschränkt prozessinternes Debuggen in .NET Framework, Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="2cdc6-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="2cdc6-110">Prozessinternes Debuggen aktiviert einen Profiler an die Inspektionsteile der Debug-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cdc6-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="2cdc6-111">Aufgrund von Kundenfeedback wurde prozessinternes Debuggen aus .NET Framework Version 2.0 entfernt, und durch eine Reihe von Funktionen, die mehrere im Einklang mit den die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2cdc6-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cdc6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cdc6-112">Requirements</span></span>  
 <span data-ttu-id="2cdc6-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cdc6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cdc6-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cdc6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2cdc6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cdc6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cdc6-116">**.NET Framework-Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="2cdc6-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cdc6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cdc6-117">See Also</span></span>  
 [<span data-ttu-id="2cdc6-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cdc6-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
