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
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136563"
---
# <a name="icorprofilercallback9-interface"></a>ICorProfilerCallback9-Schnittstelle
[Wird in der .NET Framework 4.7.2 und höheren Versionen unterstützt]  

 Eine Unterklasse von [ICorProfilerCallback8](icorprofilercallback8-interface.md) , die eine Rückruf Methode bereitstellt, die vom Common Language Runtime verwendet wird, um den Profiler zu benachrichtigen, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DynamicMethodUnloaded-Methode](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Benachrichtigt den Profiler, dass eine dynamische Methode in eine Garbage Collection aufgenommen und anschließend entladen wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerCallback8-Schnittstelle](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. dynamicmethodjitcompilationstarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. dynamicmethodjitcompilationabgeschlossene-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
