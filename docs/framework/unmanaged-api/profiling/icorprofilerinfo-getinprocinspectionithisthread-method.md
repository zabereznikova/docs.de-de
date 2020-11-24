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
ms.openlocfilehash: 8daa84e3abbbc64c9a48d8957b4ad9c6756d0d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682080"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="001ac-102">ICorProfilerInfo::GetInprocInspectionIThisThread-Methode</span><span class="sxs-lookup"><span data-stu-id="001ac-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>

<span data-ttu-id="001ac-103">Ruft ein Objekt ab, das für die ICorDebugThread-Schnittstelle abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="001ac-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="001ac-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="001ac-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="001ac-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="001ac-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="001ac-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="001ac-106">Parameters</span></span>  

 `ppicd`  
 <span data-ttu-id="001ac-107">[out](/cpp/atl/iunknown) -Objekt, das für die-Schnittstelle abgefragt werden kann `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="001ac-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="001ac-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="001ac-108">Remarks</span></span>  

 <span data-ttu-id="001ac-109">Die Common Language Runtime (CLR)-debuggingdienste unterstützten das eingeschränkte Prozess interne Debuggen in Version 1,0 von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="001ac-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="001ac-110">Das Prozess interne Debuggen ermöglichte es einem Profiler, die Inspektions Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="001ac-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="001ac-111">Aufgrund des Feedbacks von Kunden wurde das Prozess interne Debuggen aus der .NET Framework in Version 2,0 entfernt und durch eine Reihe von Funktionen ersetzt, die sich besser mit der Profilerstellungs-API in Einklang setzen.</span><span class="sxs-lookup"><span data-stu-id="001ac-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="001ac-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="001ac-112">Requirements</span></span>  

 <span data-ttu-id="001ac-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="001ac-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="001ac-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="001ac-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="001ac-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="001ac-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="001ac-116">**.NET Framework Version:** 1,0</span><span class="sxs-lookup"><span data-stu-id="001ac-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001ac-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="001ac-117">See also</span></span>

- [<span data-ttu-id="001ac-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="001ac-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
