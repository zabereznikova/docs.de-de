---
title: COR_PRF_SUSPEND_REASON-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
ms.openlocfilehash: f7d76c72ed5db95425f5b1fa2db5e4346983daa4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696673"
---
# <a name="cor_prf_suspend_reason-enumeration"></a>COR_PRF_SUSPEND_REASON-Enumeration

Gibt den Grund an, warum die Laufzeit angehalten wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|Die Laufzeit wird aus einem nicht angegebenen Grund angehalten.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Die Laufzeit wird angehalten, um eine Garbage Collection Anforderung zu bedienen.<br /><br /> Die Garbage Collection bezogenen Rückrufe treten zwischen den Rückrufe [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendfinished-method.md) und [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) auf.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|Die Laufzeit wird angehalten, sodass ein `AppDomain` heruntergefahren werden kann.<br /><br /> Während die Laufzeit angehalten wird, bestimmt die Common Language Runtime, welche Threads in der `AppDomain` heruntergefahren sind, und legt Sie fest, wenn Sie fortgesetzt werden. Während dieser Unterbrechung sind keine-spezifischen Rückrufe vorhanden `AppDomain` .|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|Die Laufzeit wird angehalten, sodass Code-Codepitching erfolgen kann.<br /><br /> Code-Codepitching verläuft nur, wenn der JIT-Compiler (Just-in-Time) aktiv ist und die Code-Codepitching aktiviert ist. Code-Codepitching-Rückrufe erfolgen zwischen den Rückrufen `ICorProfilerCallback::RuntimeSuspendFinished` und `ICorProfilerCallback::RuntimeResumeStarted` . **Hinweis:**  Die CLR-JIT stellt keine Funktionen in der .NET Framework Version 2,0 dar, daher wird dieser Wert nicht in 2,0 verwendet.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|Die Laufzeit wird angehalten, sodass Sie heruntergefahren werden kann. Alle Threads müssen angehalten werden, um den Vorgang abzuschließen.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Die Laufzeit wird für das Prozess interne Debuggen angehalten.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Die Laufzeit wird angehalten, um eine Garbage Collection vorzubereiten.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Die Laufzeit wird bei der JIT-Neukompilierung angehalten.|  
  
## <a name="remarks"></a>Hinweise  

 Alle Laufzeitthreads in nicht verwaltetem Code können weiter ausgeführt werden, bis Sie versuchen, die Laufzeit erneut einzugeben. an diesem Punkt werden Sie auch angehalten, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die zur Laufzeit gelangen. Alle Threads innerhalb der Laufzeit werden entweder sofort angehalten, wenn Sie sich in unter Brechungs barem Code befinden oder angehalten werden, wenn Sie unter brechbaren Code erreichen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsenumerationen](profiling-enumerations.md)
