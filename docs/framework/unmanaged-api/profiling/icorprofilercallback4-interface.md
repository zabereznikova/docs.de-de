---
title: ICorProfilerCallback4-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: 1b85c48859ac29738347d112dd0466a76bfdfd2c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865336"
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4-Schnittstelle
Stellt Rückruf Methoden bereit, die vom Common Language Runtime (CLR) zum Übermitteln von Informationen an den Profiler verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetReJITParameters-Methode](icorprofilercallback4-getrejitparameters-method.md)|Ermöglicht dem Codeprofiler das Festlegen von Flags für die Alternative Codegenerierung für einen neuen neu kompilierten Methoden Text.|  
|[MovedReferences2-Methode](icorprofilercallback4-movedreferences2-method.md)|Meldet das neue Layout von Objekten im Heap als Ergebnis einer komprimierenden Garbage Collection.|  
|[ReJITCompilationFinished-Methode](icorprofilercallback4-rejitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion abgeschlossen hat.|  
|[ReJITCompilationStarted-Methode](icorprofilercallback4-rejitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion gestartet hat.|  
|[ReJITError-Methode](icorprofilercallback4-rejiterror-method.md)|Meldet einen Fehler, der beim Verarbeiten einer Anforderung zum erneuten Kompilieren aufgetreten ist.|  
|[SurvivingReferences2-Methode](icorprofilercallback4-survivingreferences2-method.md)|Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
