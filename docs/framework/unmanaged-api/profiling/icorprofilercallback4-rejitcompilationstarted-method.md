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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8f2ada73686dfbe5629e21cfc6468becbd4ccc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075898"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted-Methode
Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) gestartet wurde, eine Funktion neu kompiliert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die der JIT-Compiler gestartet wurde, neu kompilieren.  
  
 `rejitId`  
 [in] Die Neukompilierung-ID der neuen Version der Funktion.  
  
 `fIsSafeToBlock`  
 [in] `true` um anzugeben, dass blockiert die Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten verursachen `false` um anzugeben, dass die Blockierung der Vorgang der Laufzeit nicht beeinflusst wird. Der Wert `true` kompatibilitätsgesichtspunkten sich nicht auf die Laufzeit nimmt allerdings die Ergebnisse der profilerstellung.  
  
## <a name="remarks"></a>Hinweise  
 Es ist möglich, erhalten mehr als ein Spaltenpaar `ReJITCompilationStarted` und [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) Methodenaufrufe für jede Funktion aufgrund der Art und Weise der Common Language Runtime behandelt-Klasse, Konstruktoren. Beispielsweise Starten der Laufzeit Methode A Methode neu kompiliert, aber der Klassenkonstruktor für Klasse B ausgeführt werden muss. Aus diesem Grund die Laufzeit den Konstruktor für die Klasse B kompiliert und ausgeführt. Während der Konstruktor ausgeführt wird, ist es einen Aufruf der Methode ein, die bewirkt, dass die Methode A erneut kompiliert werden muss. In diesem Szenario wird die erste Neukompilierung der Methode ein angehalten. Allerdings beide versucht, Kompilieren die Methode, die einer mit JIT-Neukompilierung-Ereignisse gemeldet.  
  
 Profiler müssen die Abfolge der JIT-Neukompilierung Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen. Thread A ruft z. B. `ReJITCompilationStarted`; allerdings vor dem Thread A ruft [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID von der `ReJITCompilationStarted` Rückruf für den Thread A. Sie scheinen, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) hatte noch nicht empfangen durch den Profiler. In diesem Fall jedoch ist die Funktions-ID gültig.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [JITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [ReJITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
