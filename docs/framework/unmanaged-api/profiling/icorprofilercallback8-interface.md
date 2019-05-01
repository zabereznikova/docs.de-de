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
ms.openlocfilehash: e536e61a8d812e442e1e54188c99d6a1d4586757
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049725"
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8-Schnittstelle
[Wird nur in der .NET Framework 4.7 und höheren Versionen unterstützt]  

 Eine Unterklasse von [ICorProfilerCallback7](icorprofilercallback7-interface.md) , die Rückrufmethoden, die von der common Language Runtime verwendet wird, um den Profiler zu benachrichtigen, die JIT-Kompilierung einer dynamischen Methode gestartet und beendet bereitstellt. 
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Benachrichtigt den Profiler an, dass JIT-Kompilierung einer dynamischen Methode gestartet wurde.|  
|[DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Benachrichtigt den Profiler an, die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerCallback9-Schnittstelle](icorprofilercallback9-interface.md)
