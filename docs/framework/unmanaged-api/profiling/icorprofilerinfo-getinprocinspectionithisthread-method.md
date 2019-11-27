---
title: ICorProfilerInfo::GetInprocInspectionIThisThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: bcc324d0f5cd14e1de9f02c8e6844a5868b70e8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438909"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="facc3-102">ICorProfilerInfo::GetInprocInspectionIThisThread-Methode</span><span class="sxs-lookup"><span data-stu-id="facc3-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="facc3-103">Ruft ein Objekt ab, das für die ICorDebugThread-Schnittstelle abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="facc3-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="facc3-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="facc3-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="facc3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="facc3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="facc3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="facc3-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="facc3-107">[out](/cpp/atl/iunknown) -Objekt, das für die `ICorDebugThread`-Schnittstelle abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="facc3-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="facc3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="facc3-108">Remarks</span></span>  
 <span data-ttu-id="facc3-109">Die Common Language Runtime (CLR)-debuggingdienste unterstützten das eingeschränkte Prozess interne Debuggen in Version 1,0 von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="facc3-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="facc3-110">Das Prozess interne Debuggen ermöglichte es einem Profiler, die Inspektions Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="facc3-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="facc3-111">Aufgrund des Feedbacks von Kunden wurde das Prozess interne Debuggen aus der .NET Framework in Version 2,0 entfernt und durch eine Reihe von Funktionen ersetzt, die sich besser mit der Profilerstellungs-API in Einklang setzen.</span><span class="sxs-lookup"><span data-stu-id="facc3-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="facc3-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="facc3-112">Requirements</span></span>  
 <span data-ttu-id="facc3-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="facc3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facc3-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="facc3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="facc3-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="facc3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="facc3-116">**.NET Framework Version:** 1,0</span><span class="sxs-lookup"><span data-stu-id="facc3-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facc3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="facc3-117">See also</span></span>

- [<span data-ttu-id="facc3-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="facc3-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
