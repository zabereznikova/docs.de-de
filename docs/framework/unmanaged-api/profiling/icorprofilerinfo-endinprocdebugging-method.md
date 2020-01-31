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
ms.openlocfilehash: 8a15843e9169442d89996375ee85f62b38f92e30
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864257"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="72d78-102">ICorProfilerInfo::EndInprocDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="72d78-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="72d78-103">Beendet eine in-Process-Debuggingsitzung.</span><span class="sxs-lookup"><span data-stu-id="72d78-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="72d78-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="72d78-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72d78-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="72d78-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72d78-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="72d78-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="72d78-107">in Ein-Wert, der die Debugsitzung angibt.</span><span class="sxs-lookup"><span data-stu-id="72d78-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="72d78-108">Dieser Wert muss mit dem übereinstimmen, der in der [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) -Methode empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="72d78-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72d78-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72d78-109">Remarks</span></span>  
 <span data-ttu-id="72d78-110">Sie müssen [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) und `EndInprocDebugging` innerhalb derselben Rückruf Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="72d78-110">You must call [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="72d78-111">Die CLR-debuggingdienste unterstützten das eingeschränkte Prozess interne Debuggen in den .NET Framework-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="72d78-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="72d78-112">Das Prozess interne Debuggen ermöglichte es einem Profiler, die Inspektions Teile der Debug-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="72d78-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="72d78-113">Aufgrund des Feedbacks von Kunden wurde das Prozess interne Debuggen aus der .NET Framework in Version 2,0 entfernt und durch eine Reihe von Funktionen ersetzt, die mit der Profilerstellungs-API mehr übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="72d78-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72d78-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72d78-114">Requirements</span></span>  
 <span data-ttu-id="72d78-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72d78-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72d78-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72d78-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72d78-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72d78-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72d78-118">**.NET Framework Version:** 1,0</span><span class="sxs-lookup"><span data-stu-id="72d78-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d78-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72d78-119">See also</span></span>

- [<span data-ttu-id="72d78-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72d78-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
