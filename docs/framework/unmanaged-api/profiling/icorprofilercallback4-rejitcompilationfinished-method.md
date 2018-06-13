---
title: ICorProfilerCallback4::ReJITCompilationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf2e1be735150dfb006e2274c79c25649d0271d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455356"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a>ICorProfilerCallback4::ReJITCompilationFinished-Methode
Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler Kompilieren eine Funktion abgeschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die neu kompiliert wurde.  
  
 `rejitId`  
 [in] Die Identität der erneut JIT-kompilierten Funktion.  
  
 `hrStatus`  
 [in] Ein Wert, der angibt, ob der JIT-Neukompilierung erfolgreich war.  
  
 `fIsSafeToBlock`  
 [in] `true` um anzugeben, dass die Blockierung der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten verursachen `false` um anzugeben, dass blockiert die Ausführung von der Laufzeit nicht beeinflusst.  
  
 Ein Wert von `true` ist nicht auf die Common Language Runtime Schaden anrichten, jedoch können die Profilerstellungsergebnisse auswirken.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [ReJITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
