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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bcddc143cacc3df016e6b8dd7907a67354c4311
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455734"
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4-Schnittstelle
Stellt Rückrufmethoden, die die common Language Runtime (CLR) verwendet wird, um die Übermittlung von Informationen an den Profiler.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetReJITParameters-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|Ermöglicht die Codeprofiler, alternative codeerstellungskennzeichen für einen neuen Methodentext für die neu kompilierte festgelegt.|  
|[MovedReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|Meldet das neue Layout von Objekten im Heap als Folge einer komprimierenden Garbagecollection.|  
|[ReJITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler die Neukompilierung einer Funktion abgeschlossen wurde.|  
|[ReJITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler eine Funktion neu kompiliert gestartet wurde.|  
|[ReJITError-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|Meldet einen Fehler beim Verarbeiten einer Anforderung Recompile gefunden.|  
|[SurvivingReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
