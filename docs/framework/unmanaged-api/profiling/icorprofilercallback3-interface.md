---
title: ICorProfilerCallback3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 567f124b0a0066f355d057406291e6b3a7f9428d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727923"
---
# <a name="icorprofilercallback3-interface"></a>ICorProfilerCallback3-Schnittstelle
Stellt Rückrufmethoden bereit, die common Language Runtime (CLR) verwendet wird, für die Kommunikation, Anfügen und Trennen von Zustandsinformationen an den Profiler an.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[InitializeForAttach-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|Wird aufgerufen, von der CLR, die der Profiler das Initialisieren seines Zustands nach einem Anfügevorgang zu ermöglichen.|  
|[ProfilerAttachComplete-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|Wird aufgerufen, von der CLR, um anzugeben, dass der Profiler jetzt die-Ausgleichsmethode aufrufen kann.|  
|[ProfilerDetachSucceeded-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|Benachrichtigt den Profiler, dass die CLR (Common Language Runtime) die Profiler-DLL entladen wird.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
