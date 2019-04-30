---
title: ICorProfilerInfo::GetCurrentThreadID-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 802072f3a0151aabc5ca5796df57ea7c694a2070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041209"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="81102-102">ICorProfilerInfo::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="81102-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="81102-103">Ruft die ID der im aktuellen Thread ab, wenn es sich um einen verwalteten Thread ist.</span><span class="sxs-lookup"><span data-stu-id="81102-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81102-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81102-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81102-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="81102-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="81102-106">[out] Ein Zeiger auf die zurückgegebene ID des verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="81102-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81102-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81102-107">Remarks</span></span>  
 <span data-ttu-id="81102-108">Der aktuelle Thread ist ein interner Laufzeitthread oder anderen nicht verwalteten Thread `GetCurrentThreadID` gibt CORPROF_E_NOT_MANAGED_THREAD zurück, als das HRESULT und der zurückgegebene Wert, der die `pThreadId` Parameter ist null.</span><span class="sxs-lookup"><span data-stu-id="81102-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81102-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81102-109">Requirements</span></span>  
 <span data-ttu-id="81102-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81102-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81102-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81102-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81102-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81102-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81102-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81102-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81102-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81102-114">See also</span></span>

- [<span data-ttu-id="81102-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81102-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
