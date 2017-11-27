---
title: ICorProfilerInfo::GetCurrentThreadID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetCurrentThreadID
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 055a5f56f076cc29ca7ce5d45ecedd650e8f2f44
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="c1c9f-102">ICorProfilerInfo::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c9f-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="c1c9f-103">Ruft die ID des aktuellen Threads ab, wenn es sich um einen verwalteten Thread ist.</span><span class="sxs-lookup"><span data-stu-id="c1c9f-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c9f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1c9f-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1c9f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1c9f-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="c1c9f-106">[out] Ein Zeiger auf die zurückgegebene ID des verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="c1c9f-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1c9f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1c9f-107">Remarks</span></span>  
 <span data-ttu-id="c1c9f-108">Der aktuelle Thread ist ein interner Laufzeitthread oder anderen nicht verwalteten Threads `GetCurrentThreadID` gibt CORPROF_E_NOT_MANAGED_THREAD zurück, als das HRESULT, und der Rückgabewert von der `pThreadId` werden Parameter null sein.</span><span class="sxs-lookup"><span data-stu-id="c1c9f-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c9f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1c9f-109">Requirements</span></span>  
 <span data-ttu-id="c1c9f-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c9f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c9f-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1c9f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1c9f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1c9f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1c9f-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c9f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c9f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1c9f-114">See Also</span></span>  
 [<span data-ttu-id="c1c9f-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1c9f-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
