---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3e5ad1742d6f714b53b109bb99fc288bccd4a3bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="470f2-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="470f2-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="470f2-103">Der systemeigene Adresse und Rahmen für die Ausnahmeklausel abgerufen (`catch`/`finally`/`filter`), die auszuführende ist oder gerade ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="470f2-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="470f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="470f2-104">Syntax</span></span>  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="470f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="470f2-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="470f2-106">[out] Ein Zeiger auf eine [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) Struktur, die die aktuelle Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="470f2-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="470f2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="470f2-107">Remarks</span></span>  
 <span data-ttu-id="470f2-108">Wenn eine Ausnahme Benachrichtigung empfangen wird, `GetNotifiedExceptionClauseInfo` dienen zum Abrufen der systemeigenen Adresse und Frame-Informationen für die Ausnahmeklausel (`catch`/`finally`/`filter`), ist gleich (ausgeführtwerden[ ICorProfilerCallback:: ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), oder [ICorProfilerCallback:: ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)Rückruf vom Profiler empfangen wird) oder gerade ausgeführt wurde ([ICorProfilerCallback:: ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), oder [ ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) Rückruf vom Profiler empfangen wird).</span><span class="sxs-lookup"><span data-stu-id="470f2-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="470f2-109">Dieser Aufruf kann jederzeit nach der Komprimierung einer Enter-Rückrufe vorgenommen werden, bis entweder der übereinstimmende Leave-Rückruf empfangen wird oder eine geschachtelte Ausnahme, in der aktuellen-Klausel ausgelöst wird, in der Fall, dass keine Leave-Benachrichtigung für diese Klausel ist.</span><span class="sxs-lookup"><span data-stu-id="470f2-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="470f2-110">Beachten Sie, dass es nicht möglich, dass eine ausgelöste Ausnahme als Escapesequenz für einen `filter` Ausnahmeklausel, daher immer eine Benachrichtigung lassen Sie in diesem Fall besteht.</span><span class="sxs-lookup"><span data-stu-id="470f2-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="470f2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="470f2-111">Requirements</span></span>  
 <span data-ttu-id="470f2-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="470f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="470f2-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="470f2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="470f2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="470f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="470f2-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="470f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470f2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="470f2-116">See Also</span></span>  
 [<span data-ttu-id="470f2-117">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="470f2-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="470f2-118">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="470f2-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
