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
ms.openlocfilehash: 23b91a2a58c6e76b31b94e0fa3661dfbc8e18e33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712767"
---
# <a name="icorprofilercallback9-interface"></a>ICorProfilerCallback9-Schnittstelle

[Wird in der .NET Framework 4.7.2 und höheren Versionen unterstützt]  

 Eine Unterklasse von [ICorProfilerCallback8](icorprofilercallback8-interface.md) , die eine Rückruf Methode bereitstellt, die vom Common Language Runtime verwendet wird, um den Profiler zu benachrichtigen, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DynamicMethodUnloaded-Methode](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Benachrichtigt den Profiler, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerCallback8-Schnittstelle](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. dynamicmethodjitcompilationstarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. dynamicmethodjitcompilationabgeschlossene-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
