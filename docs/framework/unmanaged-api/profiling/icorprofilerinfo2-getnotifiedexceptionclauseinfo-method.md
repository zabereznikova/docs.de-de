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
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo-Methode
Ruft die systemeigene Adresse und die Frame Informationen für die Ausnahmeklausel ( `catch` / `finally` / `filter` ) ab, die gerade ausgeführt wird oder gerade ausgeführt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parameter  
 `pinfo`  
 vorgenommen Ein Zeiger auf eine [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) -Struktur, die die aktuelle Exception-klauselinstanz und den zugehörigen Frame beschreibt.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn eine Ausnahme Benachrichtigung empfangen wird, `GetNotifiedExceptionClauseInfo` kann verwendet werden, um die systemeigene Adresse und die Frame Informationen für die Ausnahmeklausel () zu erhalten, die `catch` / `finally` / `filter` ausgeführt werden soll ([ICorProfilerCallback:: exceptioncallcherenter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)oder [ICorProfilerCallback:: der ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) -Rückruf wird vom Profiler empfangen) oder gerade ausgeführt ([ICorProfilerCallback:: exceptioncallcherleave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)oder [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) -Rückruf wird vom Profiler empfangen).  
  
 Dieser Aufruf kann jederzeit nach einer der obigen Eingabe Rückrufe erfolgen, bis entweder der übereinstimmende Leave-Rückruf empfangen oder eine geschpostete Ausnahme in der aktuellen Klausel ausgelöst wird. in diesem Fall gibt es keine Benachrichtigung über die Überschreibung für diese Klausel. Beachten Sie, dass es für eine ausgelöste Ausnahme nicht möglich ist, eine Ausnahmeklausel mit Escapezeichen zu versehen `filter` , sodass es in diesem Fall immer eine Benachrichtigung zum verlassen gibt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
