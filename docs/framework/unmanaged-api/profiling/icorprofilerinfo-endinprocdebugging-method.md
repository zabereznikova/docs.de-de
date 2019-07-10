---
title: ICorProfilerInfo::EndInprocDebugging-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7365deb11bf620fcda43e7f04347cfe4685b5a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780246"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="b6d7f-102">ICorProfilerInfo::EndInprocDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="b6d7f-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="b6d7f-103">Eine in-Process-Debugsitzung wird heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="b6d7f-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d7f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6d7f-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6d7f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6d7f-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="b6d7f-107">[in] Ein Wert, der die Debugsitzung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="b6d7f-108">Dieser Wert muss der identisch sein, die empfangen werden, der [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6d7f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6d7f-109">Remarks</span></span>  
 <span data-ttu-id="b6d7f-110">Rufen Sie [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) und `EndInprocDebugging` in die gleiche Rückrufmethode.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="b6d7f-111">Die Debugdiensten der CLR unterstützt eingeschränkte prozessinternen Debuggens in .NET Framework, Version 1.0 und 1.1.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="b6d7f-112">In-Process-Debuggen aktiviert einen Profiler, die Prüfung Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b6d7f-113">Jedoch aufgrund von Kundenfeedback hat prozessinternen Debuggens wurden entfernt von .NET Framework Version 2.0, und mit einem Satz von Funktionen, die enger an die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d7f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6d7f-114">Requirements</span></span>  
 <span data-ttu-id="b6d7f-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6d7f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d7f-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6d7f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6d7f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6d7f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6d7f-118">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="b6d7f-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d7f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6d7f-119">See also</span></span>

- [<span data-ttu-id="b6d7f-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6d7f-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
