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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175095"
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8-Schnittstelle
[Unterstützt in .NET Framework 4.7 und neueren Versionen]  

 Eine Unterklasse von [ICorProfilerCallback7,](icorprofilercallback7-interface.md) die Rückrufmethoden bereitstellt, die von der Common Language Runtime verwendet werden, um den Profiler darüber zu informieren, dass die JIT-Kompilierung einer dynamischen Methode gestartet und abgeschlossen wurde.
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode gestartet wurde.|  
|[DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerCallback9-Schnittstelle](icorprofilercallback9-interface.md)
