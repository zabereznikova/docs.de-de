---
title: ICorProfilerCallback4::ReJITCompilationStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted-Methode
Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler eine Funktion neu kompiliert gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die der JIT-Compiler gestartet wurde, neu kompilieren.  
  
 `rejitId`  
 [in] Die ID der Neukompilierung der neuen Version der Funktion.  
  
 `fIsSafeToBlock`  
 [in] `true` um anzugeben, dass die Blockierung der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten verursachen `false` um anzugeben, dass blockiert die Ausführung von der Laufzeit nicht beeinflusst. Ein Wert von `true` ist nicht auf die Common Language Runtime Schaden anrichten, jedoch können die Profilerstellungsergebnisse auswirken.  
  
## <a name="remarks"></a>Hinweise  
 Es ist möglich, mehr als ein Spaltenpaar empfangen `ReJITCompilationStarted` und [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) Methodenaufrufe für jede Funktion aufgrund der Art und Weise der Common Language Runtime Klassenkonstruktoren Handles. Z. B. die Common Language Runtime beginnt Methode A Methode neu kompiliert, aber der Klassenkonstruktor für Klasse B ausgeführt werden muss. Aus diesem Grund die Common Language Runtime den Konstruktor für die Klasse B kompiliert und ausgeführt. Während der Konstruktor ausgeführt wird, macht es einen Aufruf der Methode ein, die bewirkt, dass die Methode A erneut kompiliert werden müssen. In diesem Szenario wird die erste Neukompilierung Methode A angehalten. Beide jedoch so kompilieren Sie die Methode einer mit JIT-Neukompilierung-Ereignisse gemeldet, dass versucht.  
  
 Profiler müssen die Sequenz der JIT-Neukompilierung Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen. Beispielsweise ruft Thread A `ReJITCompilationStarted`; jedoch vor dem Thread A ruft [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit dem Funktions-ID aus der `ReJITCompilationStarted` Rückruf für Thread A. Es scheint, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) wurde noch nicht empfangen vom Profiler. Allerdings ist in diesem Fall die Funktions-ID gültig.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [ReJITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
