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
ms.openlocfilehash: a3394820f673e35777e1749229d4f8319841ca58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439390"
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4-Schnittstelle
Stellt Rückruf Methoden bereit, die vom Common Language Runtime (CLR) zum Übermitteln von Informationen an den Profiler verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetReJITParameters-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|Ermöglicht dem Codeprofiler das Festlegen von Flags für die Alternative Codegenerierung für einen neuen neu kompilierten Methoden Text.|  
|[MovedReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|Meldet das neue Layout von Objekten im Heap als Ergebnis einer komprimierenden Garbage Collection.|  
|[ReJITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion abgeschlossen hat.|  
|[ReJITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion gestartet hat.|  
|[ReJITError-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|Meldet einen Fehler, der beim Verarbeiten einer Anforderung zum erneuten Kompilieren aufgetreten ist.|  
|[SurvivingReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
