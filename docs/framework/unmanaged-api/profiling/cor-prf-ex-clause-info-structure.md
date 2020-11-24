---
title: COR_PRF_EX_CLAUSE_INFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: e8dd9f21803021975f4651ba3e6e5f4d3da0ea82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674995"
---
# <a name="cor_prf_ex_clause_info-structure"></a>COR_PRF_EX_CLAUSE_INFO-Struktur

Speichert Informationen über eine bestimmte Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`clauseType`|Ein Wert der [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) -Enumeration, die den Typ der Ausnahmeklausel angibt, den der Code soeben eingegeben oder Links eingegeben hat.|  
|`programCounter`|Der Native Einstiegspunkt des Klauselhandlers – z. b. der Inhalt des x86 EIP-Registers.|  
|`framePointer`|Der Zeiger auf den logischen Frame für den klauselhandler – z. b. der Inhalt des x86-EBP-Registers.|  
|`shadowStackPointer`|Der Zeiger auf den Schatten Stapel. Dieser Wert ist der Inhalt des BSP-Registers und gilt nur für ia64.|  
  
## <a name="remarks"></a>Hinweise  

 Wenn eine Ausnahme Benachrichtigung empfangen wird, kann [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) verwendet werden, um die nativen Adress-und Frame Informationen für die Ausnahmeklausel (/Filter) zu erhalten, die `catch` / `finally` gerade ausgeführt wird oder gerade ausgeführt wurde.  
  
 Die Ausführung einer Exception-Klausel umfasst diese Rückrufe vom Common Language Runtime (CLR):  
  
- [ICorProfilerCallback:: exceptioncallcherenter](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [ICorProfilerCallback:: ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [ICorProfilerCallback:: exceptioncallcherleave](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsstrukturen](profiling-structures.md)
