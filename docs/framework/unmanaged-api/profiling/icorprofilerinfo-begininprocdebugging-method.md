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
ms.openlocfilehash: c14979fa711145b9f1a134f90d7450b24e6d8a15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864296"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="24e09-102">ICorProfilerInfo::BeginInprocDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="24e09-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="24e09-103">Initialisiert die Prozess interne Debugunterstützung.</span><span class="sxs-lookup"><span data-stu-id="24e09-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="24e09-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="24e09-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e09-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="24e09-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24e09-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="24e09-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="24e09-107">in Legen Sie diesen Wert auf `true` fest, um die Debugunterstützung nur für den aktuellen Thread zu initialisieren. Legen Sie Sie auf `false`, um die Debugunterstützung für alle Threads zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="24e09-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="24e09-108">vorgenommen Der Zeiger auf einen zurückgegebenen Wert, der die Debugsitzung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="24e09-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24e09-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24e09-109">Remarks</span></span>  
 <span data-ttu-id="24e09-110">Die CLR-debuggingdienste unterstützten das eingeschränkte Prozess interne Debuggen in den .NET Framework-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="24e09-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="24e09-111">Das Prozess interne Debuggen ermöglichte es einem Profiler, die Inspektions Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="24e09-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="24e09-112">Aufgrund des Feedbacks von Kunden wurde das Prozess interne Debuggen aus der .NET Framework in Version 2,0 entfernt und durch eine Reihe von Funktionen ersetzt, die mit der Profilerstellungs-API mehr übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="24e09-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24e09-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24e09-113">Requirements</span></span>  
 <span data-ttu-id="24e09-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24e09-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24e09-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24e09-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24e09-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24e09-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24e09-117">**.NET Framework Version:** 1,0</span><span class="sxs-lookup"><span data-stu-id="24e09-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e09-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24e09-118">See also</span></span>

- [<span data-ttu-id="24e09-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e09-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
