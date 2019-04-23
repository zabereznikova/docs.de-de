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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21533b5173bcd91d0c944fbde4eafc9817de8315
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220057"
---
# <a name="corprfsuspendreason-enumeration"></a>COR_PRF_SUSPEND_REASON-Enumeration
Gibt den Grund, dass die Laufzeit angehalten wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|Die Laufzeit ist aus Unbekannter Ursache unterbrochen.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Die Laufzeit wird angehalten, um eine Garbage Collection-Anforderung zu bedienen.<br /><br /> Die Rückrufe für die Garbage Collection-bezogene treten zwischen den [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) und [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückrufe.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|Die Laufzeit wird angehalten, damit ein `AppDomain` heruntergefahren werden kann.<br /><br /> Während die Laufzeit angehalten ist, die Laufzeit wird festzulegen, welche Threads im werden die `AppDomain` , heruntergefahren wird, und legen Sie sie Abbrechen, wenn sie fortsetzen. Es gibt keine `AppDomain`-spezifische Rückrufe während dieses Aussetzens.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|Die Laufzeit wird unterbrochen, sodass Codepitching auftreten kann.<br /><br /> Codepitching erfolgt nur, wenn der just-in-Time-Compiler (JIT) aktiv ist und Codepitching aktiviert. Codepitchingrückrufe treten zwischen den `ICorProfilerCallback::RuntimeSuspendFinished` und `ICorProfilerCallback::RuntimeResumeStarted` Rückrufe. **Hinweis**:  Die CLR-JIT ist nicht Funktionen in .NET Framework, Version 2.0, präsentieren, damit dieser Wert nicht in 2.0 verwendet wird.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|Die Laufzeit wird unterbrochen, sodass er heruntergefahren werden kann. Sie müssen alle Threads zum Abschließen des Vorgangs anzuhalten.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Die Laufzeit wird für das prozessinterne Debuggen angehalten.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Die Laufzeit wird angehalten, um für eine Garbagecollection vorzubereiten.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Die Laufzeit wird für die JIT-Neukompilierung unterbrochen.|  
  
## <a name="remarks"></a>Hinweise  
 Alle Threads mit Common Language Runtime, die in nicht verwaltetem Code dürfen weiterhin ausgeführt, bis sie versuchen, die Runtime erneut eingeben, an welcher, die Stelle sie auch angehalten werden, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die die Laufzeit eingeben. Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn sie in der unterbrechbare Code sind, oder aufgefordert, anhalten, wenn sie unterbrechbaren Code erreichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
