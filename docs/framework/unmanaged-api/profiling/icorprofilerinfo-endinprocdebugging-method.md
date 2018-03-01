---
title: ICorProfilerInfo::EndInprocDebugging-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a36c557d9ab2fa661808aa2f0be942d11ea9fa61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="8ab03-102">ICorProfilerInfo::EndInprocDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="8ab03-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="8ab03-103">Fährt eine Debugsitzung für in-Process.</span><span class="sxs-lookup"><span data-stu-id="8ab03-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="8ab03-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="8ab03-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ab03-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ab03-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ab03-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ab03-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="8ab03-107">[in] Ein Wert, der die Debugsitzung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8ab03-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="8ab03-108">Dieser Wert muss identisch, die innerhalb der [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="8ab03-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ab03-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ab03-109">Remarks</span></span>  
 <span data-ttu-id="8ab03-110">Rufen Sie [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) und `EndInprocDebugging` innerhalb der gleichen Rückrufmethode.</span><span class="sxs-lookup"><span data-stu-id="8ab03-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="8ab03-111">Die CLR-Debugdiensten unterstützt beschränkt prozessinternes Debuggen in .NET Framework, Version 1.0 und 1.1.</span><span class="sxs-lookup"><span data-stu-id="8ab03-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="8ab03-112">Prozessinternes Debuggen aktiviert einen Profiler an die Inspektionsteile der Debug-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ab03-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="8ab03-113">Jedoch aufgrund von Kundenfeedback wurde prozessinternes Debuggen von .NET Framework Version 2.0 entfernt, und durch eine Reihe von Funktionen, die mehrere im Einklang mit den die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="8ab03-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ab03-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ab03-114">Requirements</span></span>  
 <span data-ttu-id="8ab03-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ab03-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ab03-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ab03-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ab03-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ab03-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ab03-118">**.NET Framework-Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="8ab03-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab03-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ab03-119">See Also</span></span>  
 [<span data-ttu-id="8ab03-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ab03-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
