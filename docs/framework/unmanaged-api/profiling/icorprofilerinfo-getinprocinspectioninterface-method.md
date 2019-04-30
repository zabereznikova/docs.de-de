---
title: ICorProfilerInfo::GetInprocInspectionInterface-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 456dd8aedf11b1b27ee4926988fc615ebb7a76d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991821"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="9839c-102">ICorProfilerInfo::GetInprocInspectionInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="9839c-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="9839c-103">Ruft ein Objekt, das abgefragt werden kann, für eine "ICorDebugProcess"-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="9839c-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="9839c-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="9839c-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9839c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9839c-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9839c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9839c-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="9839c-107">[out](/cpp/atl/iunknown) -Objekt, das abgefragt werden kann ein `ICorDebugProcess` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9839c-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9839c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9839c-108">Remarks</span></span>  
 <span data-ttu-id="9839c-109">Die common Language Runtime (CLR), das Debug-API unterstützt eingeschränkte prozessinternen Debuggens in .NET Framework, Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="9839c-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="9839c-110">In-Process-Debuggen aktiviert einen Profiler, die Prüfung Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9839c-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="9839c-111">Aufgrund von Kundenfeedback wurde prozessinternes Debuggen von .NET Framework Version 2.0 entfernt, und durch eine Reihe von Funktionen, die enger an die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9839c-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9839c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9839c-112">Requirements</span></span>  
 <span data-ttu-id="9839c-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9839c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9839c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9839c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9839c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9839c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9839c-116">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="9839c-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9839c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9839c-117">See also</span></span>

- [<span data-ttu-id="9839c-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9839c-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
