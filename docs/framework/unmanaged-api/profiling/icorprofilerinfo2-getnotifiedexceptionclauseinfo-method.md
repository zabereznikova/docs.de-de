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
ms.openlocfilehash: 52ad124638a1c1ec7d39fa41b9163f3ab50ffe70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433068"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode
Ruft die nativen Adress-und Frame Informationen für die Ausnahmeklausel (`catch`/`finally`/`filter`) ab, die gerade ausgeführt oder gerade ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parameter  
 `pinfo`  
 vorgenommen Ein Zeiger auf eine [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) -Struktur, die die aktuelle Exception-klauselinstanz und den zugehörigen Frame beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Ausnahme Benachrichtigung empfangen wird, können `GetNotifiedExceptionClauseInfo` verwendet werden, um die systemeigene Adresse und die Frame Informationen für die Ausnahmeklausel (`catch`/`finally`/`filter`), die ausgeführt werden soll, zu erhalten ([ICorProfilerCallback:: exceptioncallcherenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)oder [ICorProfilerCallback:: ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) Callback wird vom Profiler empfangen) oder gerade ausgeführt ([ICorProfilerCallback:: exceptioncallcherleave ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)oder [ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) -Rückruf wird vom Profiler empfangen).  
  
 Dieser Aufruf kann jederzeit nach einer der obigen Eingabe Rückrufe erfolgen, bis entweder der übereinstimmende Leave-Rückruf empfangen oder eine geschpostete Ausnahme in der aktuellen Klausel ausgelöst wird. in diesem Fall gibt es keine Benachrichtigung über die Überschreibung für diese Klausel. Beachten Sie, dass es für eine ausgelöste Ausnahme nicht möglich ist, eine `filter` Exception-Klausel mit Escapezeichen zu versehen  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
