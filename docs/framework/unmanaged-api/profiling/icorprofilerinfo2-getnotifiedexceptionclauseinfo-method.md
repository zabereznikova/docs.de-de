---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: 08337a118a80d213f16e2a16f744b96f5dde2e7f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496999"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="470f9-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="470f9-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="470f9-103">Ruft die systemeigene Adresse und die Frame Informationen für die Ausnahmeklausel ( `catch` / `finally` / `filter` ) ab, die gerade ausgeführt wird oder gerade ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="470f9-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="470f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="470f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="470f9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="470f9-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="470f9-106">vorgenommen Ein Zeiger auf eine [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) -Struktur, die die aktuelle Exception-klauselinstanz und den zugehörigen Frame beschreibt.</span><span class="sxs-lookup"><span data-stu-id="470f9-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="470f9-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="470f9-107">Remarks</span></span>  
 <span data-ttu-id="470f9-108">Wenn eine Ausnahme Benachrichtigung empfangen wird, `GetNotifiedExceptionClauseInfo` kann verwendet werden, um die systemeigene Adresse und die Frame Informationen für die Ausnahmeklausel () zu erhalten, die `catch` / `finally` / `filter` ausgeführt werden soll ([ICorProfilerCallback:: exceptioncallcherenter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)oder [ICorProfilerCallback:: der ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) -Rückruf wird vom Profiler empfangen) oder gerade ausgeführt ([ICorProfilerCallback:: exceptioncallcherleave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)oder [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) -Rückruf wird vom Profiler empfangen).</span><span class="sxs-lookup"><span data-stu-id="470f9-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="470f9-109">Dieser Aufruf kann jederzeit nach einer der obigen Eingabe Rückrufe erfolgen, bis entweder der übereinstimmende Leave-Rückruf empfangen oder eine geschpostete Ausnahme in der aktuellen Klausel ausgelöst wird. in diesem Fall gibt es keine Benachrichtigung über die Überschreibung für diese Klausel.</span><span class="sxs-lookup"><span data-stu-id="470f9-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="470f9-110">Beachten Sie, dass es für eine ausgelöste Ausnahme nicht möglich ist, eine Ausnahmeklausel mit Escapezeichen zu versehen `filter` , sodass es in diesem Fall immer eine Benachrichtigung zum verlassen gibt.</span><span class="sxs-lookup"><span data-stu-id="470f9-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="470f9-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="470f9-111">Requirements</span></span>  
 <span data-ttu-id="470f9-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="470f9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="470f9-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="470f9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="470f9-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="470f9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="470f9-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="470f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470f9-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="470f9-116">See also</span></span>

- [<span data-ttu-id="470f9-117">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="470f9-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="470f9-118">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="470f9-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
