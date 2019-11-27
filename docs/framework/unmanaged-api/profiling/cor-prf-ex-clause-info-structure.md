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
ms.openlocfilehash: df4bfe69b22439073342693a03376a0b506f9c70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428376"
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`clauseType`|Ein Wert der [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) -Enumeration, die den Typ der Ausnahmeklausel angibt, den der Code soeben eingegeben oder Links eingegeben hat.|  
|`programCounter`|Der Native Einstiegspunkt des Klauselhandlers – z. b. der Inhalt des x86 EIP-Registers.|  
|`framePointer`|Der Zeiger auf den logischen Frame für den klauselhandler – z. b. der Inhalt des x86-EBP-Registers.|  
|`shadowStackPointer`|Der Zeiger auf den Schatten Stapel. Dieser Wert ist der Inhalt des BSP-Registers und gilt nur für ia64.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Ausnahme Benachrichtigung empfangen wird, kann [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) verwendet werden, um die nativen Adress-und Frame Informationen für die Ausnahmeklausel (`catch`/`finally`) zu erhalten, die gerade ausgeführt wird oder gerade ausgeführt wurde.  
  
 Die Ausführung einer Exception-Klausel umfasst diese Rückrufe vom Common Language Runtime (CLR):  
  
- [ICorProfilerCallback:: exceptioncallcherenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [ICorProfilerCallback:: ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [ICorProfilerCallback:: exceptioncallcherleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
