---
title: COR_PRF_SUSPEND_REASON-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SUSPEND_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SUSPEND_REASON
helpviewer_keywords: COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713360b3cdc30ce7bca3e0df115016d66e59b0df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Die Common Language Runtime wird angehalten, um eine Garbage Collection-Anforderung zu bedienen.<br /><br /> Die Garbage Collection-bezogene Rückrufe treten zwischen den [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) und [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückrufe.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|Die Common Language Runtime wird angehalten, damit ein `AppDomain` heruntergefahren werden kann.<br /><br /> Während die Laufzeit angehalten ist, die Common Language Runtime bestimmen, welche Threads in werden die `AppDomain` also heruntergefahren wird, und richten sie abgebrochen wird, wenn sie fortsetzen. Es gibt keine `AppDomain`-spezifische Rückrufe während diese Unterbrechung.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|Die Common Language Runtime wird angehalten, sodass Codepitching auftreten kann.<br /><br /> Codepitching erfolgt nur, wenn der Just-in-Time (JIT)-Compiler aktiv ist und Codepitching aktiviert. Codepitchingrückrufe treten zwischen den `ICorProfilerCallback::RuntimeSuspendFinished` und `ICorProfilerCallback::RuntimeResumeStarted` Rückrufe. **Hinweis:** der CLR-JIT ist nicht der Verkaufspräsentation Funktionen in .NET Framework, Version 2.0, damit dieser Wert nicht in 2.0 verwendet wird.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|Die Common Language Runtime wird angehalten, sodass er heruntergefahren werden kann. Sie müssen alle Threads zum Abschließen des Vorgangs anzuhalten.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Die Laufzeit wird für prozessinternes Debuggen angehalten.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Die Common Language Runtime wird angehalten, um für eine Garbagecollection vorzubereiten.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Die Common Language Runtime ist für die JIT-Neukompilierung angehalten.|  
  
## <a name="remarks"></a>Hinweise  
 Weiter ausgeführt wird, bis sie versuchen, die Laufzeit erneut eingeben, an welchem, die Punkt sie auch angehalten werden, bis die Laufzeit fortgesetzt wird, sind alle Common Language Runtime-Threads, die in nicht verwaltetem Code sind zulässig. Dies gilt auch für neue Threads, die die Common Language Runtime eingeben. Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn der Code parallelisiert werden, oder aufgefordert, angehalten, wenn sie unterbrechbaren Code erreichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
