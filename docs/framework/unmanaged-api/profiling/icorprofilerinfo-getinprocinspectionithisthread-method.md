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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e0f56dd6ece32b1f05418ea288da409af5cad5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782765"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="28ea6-102">ICorProfilerInfo::GetInprocInspectionIThisThread-Methode</span><span class="sxs-lookup"><span data-stu-id="28ea6-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="28ea6-103">Ruft ein Objekt, das abgefragt werden kann, für die ICorDebugThread-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="28ea6-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="28ea6-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="28ea6-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ea6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="28ea6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28ea6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="28ea6-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="28ea6-107">[out](/cpp/atl/iunknown) -Objekt, das abgefragt werden kann die `ICorDebugThread` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="28ea6-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28ea6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28ea6-108">Remarks</span></span>  
 <span data-ttu-id="28ea6-109">Die common Language Runtime (CLR), das Debuggen von Diensten unterstützt eingeschränkte prozessinternen Debuggens in .NET Framework, Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="28ea6-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="28ea6-110">In-Process-Debuggen aktiviert einen Profiler, die Prüfung Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="28ea6-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="28ea6-111">Aufgrund von Kundenfeedback wurde prozessinternes Debuggen von .NET Framework Version 2.0 entfernt, und durch eine Reihe von Funktionen, die enger an die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="28ea6-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ea6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28ea6-112">Requirements</span></span>  
 <span data-ttu-id="28ea6-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28ea6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ea6-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28ea6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28ea6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28ea6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28ea6-116">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="28ea6-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ea6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28ea6-117">See also</span></span>

- [<span data-ttu-id="28ea6-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28ea6-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
