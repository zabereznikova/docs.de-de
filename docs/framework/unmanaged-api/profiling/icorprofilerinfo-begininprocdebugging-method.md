---
title: ICorProfilerInfo::BeginInprocDebugging-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 618be7482616ea155798973d02a90f32d46164db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780265"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="2b6e9-102">ICorProfilerInfo::BeginInprocDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="2b6e9-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="2b6e9-103">Initialisiert in-Process-debugging-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="2b6e9-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b6e9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b6e9-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b6e9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b6e9-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="2b6e9-107">[in] Legen Sie diesen Wert auf `true` zum Initialisieren der debugging-Unterstützung für nur den aktuellen Thread; legen Sie ihn auf `false` Debuggingunterstützung für alle Threads zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="2b6e9-108">[out] Der Zeiger auf ein Rückgabewert, der die Debugsitzung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b6e9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b6e9-109">Remarks</span></span>  
 <span data-ttu-id="2b6e9-110">Die Debugdiensten der CLR unterstützt eingeschränkte prozessinternen Debuggens in .NET Framework, Version 1.0 und 1.1.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="2b6e9-111">In-Process-Debuggen aktiviert einen Profiler, die Prüfung Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="2b6e9-112">Jedoch aufgrund von Kundenfeedback hat prozessinternen Debuggens wurden entfernt von .NET Framework Version 2.0, und mit einem Satz von Funktionen, die enger an die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b6e9-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b6e9-113">Requirements</span></span>  
 <span data-ttu-id="2b6e9-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b6e9-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2b6e9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2b6e9-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b6e9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b6e9-117">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="2b6e9-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b6e9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b6e9-118">See also</span></span>

- [<span data-ttu-id="2b6e9-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b6e9-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
