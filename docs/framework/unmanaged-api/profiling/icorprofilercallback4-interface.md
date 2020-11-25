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
ms.openlocfilehash: 942ee8234b79c6579acc009960f4571801fc3185
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730291"
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4-Schnittstelle

Stellt Rückruf Methoden bereit, die vom Common Language Runtime (CLR) zum Übermitteln von Informationen an den Profiler verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetReJITParameters-Methode](icorprofilercallback4-getrejitparameters-method.md)|Ermöglicht dem Codeprofiler das Festlegen von Flags für die Alternative Codegenerierung für einen neuen neu kompilierten Methoden Text.|  
|[MovedReferences2-Methode](icorprofilercallback4-movedreferences2-method.md)|Meldet das neue Layout von Objekten im Heap als Ergebnis einer komprimierenden Garbage Collection.|  
|[ReJITCompilationFinished-Methode](icorprofilercallback4-rejitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion abgeschlossen hat.|  
|[ReJITCompilationStarted-Methode](icorprofilercallback4-rejitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion gestartet hat.|  
|[ReJITError-Methode](icorprofilercallback4-rejiterror-method.md)|Meldet einen Fehler, der beim Verarbeiten einer Anforderung zum erneuten Kompilieren aufgetreten ist.|  
|[SurvivingReferences2-Methode](icorprofilercallback4-survivingreferences2-method.md)|Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
