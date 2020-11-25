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
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732384"
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8-Schnittstelle

[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]  

 Eine Unterklasse von [ICorProfilerCallback7](icorprofilercallback7-interface.md) , die Rückruf Methoden bereitstellt, die vom Common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass die JIT-Kompilierung einer dynamischen Methode gestartet und beendet wurde.
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode gestartet wurde.|  
|[DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerCallback9-Schnittstelle](icorprofilercallback9-interface.md)
