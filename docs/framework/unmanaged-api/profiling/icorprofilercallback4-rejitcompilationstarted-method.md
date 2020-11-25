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
ms.openlocfilehash: 43db4ce0ba7a95a029e6c4928f55a99df9085164
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730252"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted-Methode

Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion gestartet hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter  

 `functionId`  
 in Die ID der Funktion, für die der JIT-Compiler mit der erneuten Kompilierung begonnen hat.  
  
 `rejitId`  
 in Die neukompilierungs-ID der neuen Version der Funktion.  
  
 `fIsSafeToBlock`  
 [in] `true` , um anzugeben, dass das blockieren möglicherweise dazu führt, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false` , um anzugeben, dass die Blockierung den Lauf der Laufzeit nicht beeinträchtigt. Der Wert von `true` führt nicht zu einer Beeinträchtigung der Laufzeit, kann jedoch die Profil Erstellungs Ergebnisse beeinflussen.  
  
## <a name="remarks"></a>Hinweise  

 Es ist möglich, `ReJITCompilationStarted` aufgrund der Art und Weise, wie die Laufzeit Klassenkonstruktoren behandelt, mehr als ein paar von-und [rejitcompilationbeendete](icorprofilercallback4-rejitcompilationfinished-method.md) -Methoden aufrufen für jede Funktion zu empfangen. Die Laufzeit startet z. B. die Neukompilierung der Methode A, der Klassenkonstruktor für Klasse B muss jedoch ausgeführt werden. Daher kompiliert die Runtime den Konstruktor für Klasse B neu und führt Sie aus. Während der Konstruktor ausgeführt wird, ruft er die Methode a auf, die bewirkt, dass die Methode a erneut neu kompiliert wird. In diesem Szenario wird die erste Neukompilierung der Methode A angehalten. Beide Versuche, Methode A erneut zu kompilieren, werden jedoch mit JIT-neukompilierungs Ereignissen gemeldet.  
  
 Profiler müssen die Abfolge der JIT-neukompilierungs Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe erstellen. Beispielsweise ruft Thread a auf `ReJITCompilationStarted` . bevor Thread a [rejitcompilationbeendeten](icorprofilercallback4-rejitcompilationfinished-method.md)aufruft, ruft Thread B jedoch [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID aus dem `ReJITCompilationStarted` Rückruf für Thread a auf. Es kann vorkommen, dass die Funktions-ID noch nicht gültig ist, weil ein Aufruf von [rejitcompilationbeendeten](icorprofilercallback4-rejitcompilationfinished-method.md) noch nicht vom Profiler empfangen wurde. In diesem Fall ist die Funktions-ID jedoch gültig.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](icorprofilercallback4-interface.md)
- [JITCompilationFinished-Methode](icorprofilercallback-jitcompilationfinished-method.md)
- [ReJITCompilationFinished-Methode](icorprofilercallback4-rejitcompilationfinished-method.md)
