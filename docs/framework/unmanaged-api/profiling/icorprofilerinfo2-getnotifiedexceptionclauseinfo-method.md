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
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode
Der systemeigene Adresse und Rahmen für die Ausnahmeklausel abgerufen (`catch`/`finally`/`filter`), die auszuführende ist oder gerade ausgeführt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pinfo`  
 [out] Ein Zeiger auf eine [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) Struktur, die die aktuelle Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Ausnahme Benachrichtigung empfangen wird, `GetNotifiedExceptionClauseInfo` dienen zum Abrufen der systemeigenen Adresse und Frame-Informationen für die Ausnahmeklausel (`catch`/`finally`/`filter`), ist gleich (ausgeführtwerden[ ICorProfilerCallback:: ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), oder [ICorProfilerCallback:: ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)Rückruf vom Profiler empfangen wird) oder gerade ausgeführt wurde ([ICorProfilerCallback:: ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), oder [ ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) Rückruf vom Profiler empfangen wird).  
  
 Dieser Aufruf kann jederzeit nach der Komprimierung einer Enter-Rückrufe vorgenommen werden, bis entweder der übereinstimmende Leave-Rückruf empfangen wird oder eine geschachtelte Ausnahme, in der aktuellen-Klausel ausgelöst wird, in der Fall, dass keine Leave-Benachrichtigung für diese Klausel ist. Beachten Sie, dass es nicht möglich, dass eine ausgelöste Ausnahme als Escapesequenz für einen `filter` Ausnahmeklausel, daher immer eine Benachrichtigung lassen Sie in diesem Fall besteht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
