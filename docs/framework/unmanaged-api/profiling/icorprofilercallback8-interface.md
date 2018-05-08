---
title: ICorProfilerCallback8-Schnittstelle
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8-Schnittstelle
[Wird nur in .NET Framework 4.7 und höheren Versionen unterstützt]  

 Eine Unterklasse von [ICorProfilerCallback7](icorprofilercallback7-interface.md) Rückrufmethoden, die von der common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, die gestartet und beendet JIT-Kompilierung einer dynamischen Methode bereitstellt. 
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass JIT-Kompilierung einer dynamischen Methode gestartet wurde.|  
|[DynamicMethodJITCompilationFinished-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass JIT-Kompilierung einer dynamischen Methode abgeschlossen ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch  
[Profilerstellungsschnittstellen](profiling-interfaces.md)   
[ICorProfilerCallback9-Schnittstelle](icorprofilercallback9-interface.md)
