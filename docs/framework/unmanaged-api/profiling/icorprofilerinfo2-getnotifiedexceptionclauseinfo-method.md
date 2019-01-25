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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 736fde9de1a7d4fa50d6a07bf17eacd742a6b86d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683884"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode
Ruft die systemeigenen und der Framezeiger Informationen für die Ausnahmeklausel ab (`catch`/`finally`/`filter`), wird gleich ausgeführt werden oder gerade ausgeführt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pinfo`  
 [out] Ein Zeiger auf eine [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) Struktur, die die aktuelle Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Ausnahme Benachrichtigung empfangen wird, `GetNotifiedExceptionClauseInfo` können verwendet werden, um die systemeigenen und der Framezeiger Informationen für die Ausnahmeklausel zu erhalten (`catch`/`finally`/`filter`), die gleich (ausgeführtwerden[ ICorProfilerCallback:: ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), oder [ICorProfilerCallback:: ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)Rückruf wird vom Profiler empfangen) oder gerade ausgeführt wurde ([ICorProfilerCallback:: ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), oder [ ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) Rückruf wird vom Profiler empfangen).  
  
 Dieser Aufruf kann zu einem beliebigen Zeitpunkt nach einem der oben genannten EINGABETASTE Rückrufe vorgenommen werden, bis die übereinstimmende Leave-Rückruf empfangen wird, oder eine geschachtelte Ausnahme, in der aktuellen Klausel ausgelöst wird, in der Fall, dass keine Leave-Benachrichtigung für diese Klausel ist. Beachten Sie, dass es nicht möglich, dass eine ausgelöste Ausnahme, die mit Escapezeichen versehen ist eine `filter` Ausnahmeklausel, sodass immer eine verlassen-Benachrichtigung in diesem Fall.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
