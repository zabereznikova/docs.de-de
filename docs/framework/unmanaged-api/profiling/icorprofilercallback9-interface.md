---
title: ICorProfilerCallback9-Schnittstelle
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452376"
---
# <a name="icorprofilercallback9-interface"></a>ICorProfilerCallback9-Schnittstelle
[Wird nur in .NET Framework 4.7.2 und höheren Versionen unterstützt]  

 Eine Unterklasse von [ICorProfilerCallback8](icorprofilercallback8-interface.md) , der eine Rückrufmethode, die von der common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass eine dynamische Methode eine Garbage Collection gesammelt und anschließend entladen wurde bereitstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DynamicMethodUnloaded-Methode](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Benachrichtigt den Profiler, dass eine dynamische Methode eine Garbage Collection gesammelt und anschließend entladen wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Siehe auch  
[Profilerstellungsschnittstellen](profiling-interfaces.md)   
[ICorProfilerCallback8-Schnittstelle](icorprofilercallback9-interface.md)   
[ICorProfilerCallback8.DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)   
[ICorProfilerCallback8.DynamicMethodJITCompilationFinished-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
