---
title: ICorProfilerCallback4::ReJITCompilationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177082"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted-Methode
Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) mit der Neukompilierung einer Funktion begonnen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, mit deren Neukompilierung der JIT-Compiler begonnen hat.  
  
 `rejitId`  
 [in] Die Neukompilierungs-ID der neuen Version der Funktion.  
  
 `fIsSafeToBlock`  
 [in] `true` , um anzugeben, dass das Blockieren dazu führen kann, dass die Laufzeit darauf wartet, dass der aufrufende Thread von diesem Rückruf zurückkehrt. `false` , um anzugeben, dass die Blockierung den Betrieb der Laufzeit nicht beeinträchtigt. Ein Wert `true` von schadet der Laufzeit nicht, kann sich aber auf die Profilerstellungsergebnisse auswirken.  
  
## <a name="remarks"></a>Bemerkungen  
 Es ist möglich, mehr als `ReJITCompilationStarted` ein Paar von und [ReJITCompilationFinished-Methodenaufrufe](icorprofilercallback4-rejitcompilationfinished-method.md) für jede Funktion zu empfangen, da die Laufzeit Klassenkonstruktoren verarbeitet. Beispielsweise beginnt die Laufzeit mit der Neukompilierung von Methode A, aber der Klassenkonstruktor für Klasse B muss ausgeführt werden. Daher kompiliert die Laufzeit den Konstruktor für Klasse B neu und führt ihn aus. Während der Konstruktor ausgeführt wird, wird die Methode A aufaufruft, wodurch Methode A erneut kompiliert wird. In diesem Szenario wird die erste Neukompilierung von Methode A angehalten. Beide Versuche, Methode A neu zu kompilieren, werden jedoch mit JIT-Neukompilierungsereignissen gemeldet.  
  
 Profiler müssen die Reihenfolge der JIT-Neukompilierungsrückrufe unterstützen, wenn zwei Threads gleichzeitig Rückrufe ausführen. Thread A ruft `ReJITCompilationStarted`z. B. auf; Vor dem Aufruf von [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)ruft Thread B jedoch [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID aus dem `ReJITCompilationStarted` Rückruf für Thread A auf. Es könnte den Anschein haben, dass die Funktions-ID noch nicht gültig sein sollte, da ein Aufruf von [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) noch nicht vom Profiler empfangen wurde. In diesem Fall ist jedoch die Funktions-ID gültig.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](icorprofilercallback4-interface.md)
- [JITCompilationFinished-Methode](icorprofilercallback-jitcompilationfinished-method.md)
- [ReJITCompilationFinished-Methode](icorprofilercallback4-rejitcompilationfinished-method.md)
