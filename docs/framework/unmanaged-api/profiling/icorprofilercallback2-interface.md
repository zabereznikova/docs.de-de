---
title: ICorProfilerCallback2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7927d3b4d41731c9b69154fa8895a8f698f53e31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2-Schnittstelle
Enthält Methoden, die von der common Language Runtime (CLR) verwendet werden, um einen Codeprofiler benachrichtigt, wenn die Ereignisse, die der Profiler abonniert hat, auftreten. Die `ICorProfilerCallback2` Schnittstelle ist eine Erweiterung von der [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle. D. h., bietet es neue Rückrufe, die in .NET Framework, Version 2.0 eingeführt.  
  
> [!NOTE]
>  Jede Implementierung muss mit dem Wert S_OK bei einem Fehler auf Erfolg oder dem E_FAIL HRESULT zurück. Die CLR ignoriert derzeit das HRESULT, das von jedem Rückruf außer zurückgegeben wird [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[FinalizeableObjectQueued-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|Benachrichtigt den Profiler, dass ein Objekt mit einem Finalizer für im Finalizer-Thread für die Ausführung der in der Warteschlange wurde hat seine `Finalize` Methode.|  
|[GarbageCollectionFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|Benachrichtigt den Profiler, dass eine Garbagecollection abgeschlossen wurde und alle Garbage Collection-Rückrufe ausgegeben wurden.|  
|[GarbageCollectionStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|Benachrichtigt den Profiler, dass eine Garbagecollection gestartet wurde.|  
|[HandleCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|Benachrichtigt den Profiler, dass eine Garbage Collection-Handle erstellt wurde.|  
|[HandleDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|Benachrichtigt den Profiler, dass eine Garbage Collection-Handle zerstört wurde.|  
|[RootReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|Benachrichtigt den Profiler zu Stammverweisen, nach eine Garbagecollection aufgetreten ist. Diese Methode ist eine Erweiterung der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) Methode.|  
|[SurvivingReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|Benachrichtigt den Profiler über Objektverweise, die eine Garbagecollection noch vorhanden sind.|  
|[ThreadNameChanged-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|Benachrichtigt den Profiler, dass der Name eines Threads geändert wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft eine Methode in der `ICorProfilerCallback` (oder `ICorProfilerCallback2`) Schnittstelle, um den Profiler, wenn ein Ereignis zu benachrichtigen, die der Profiler abonniert hatten, tritt auf. Dies ist die primäre Rückrufschnittstelle, die über die CLR mit der Codeprofiler kommuniziert.  
  
 Ein Codeprofiler muss die Methoden implementieren die `ICorProfilerCallback` Schnittstelle. Der Profiler muss für die .NET Framework 2.0 und höheren Versionen lautet auch implementieren die `ICorProfilerCallback2` Methoden. Jede Implementierung muss mit dem Wert S_OK bei einem Fehler auf Erfolg oder dem E_FAIL HRESULT zurück. Die CLR ignoriert derzeit das HRESULT, das von jedem Rückruf außer zurückgegeben wird [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Ein Codeprofiler muss in der Microsoft Windows-Registrierung, die COM-Objekt, das implementiert Registrieren der `ICorProfilerCallback` und `ICorProfilerCallback2` Schnittstellen. Ein Codeprofiler abonniert die Ereignisse, die für die Benachrichtigung durch den Aufruf zugriffsdrosselung [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Dies erfolgt in der Regel in der Profiler-Implementierung von [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Der Profiler kann dann Benachrichtigung von der Runtime erhalten, wenn ein Ereignis ausgeführt wird oder nur in einer ausgeführten Laufzeitprozess Fehler.  
  
> [!NOTE]
>  Der Profiler registriert ein einzelnes COM-Objekt. Wenn der Profiler .NET Framework, Version 1.0 oder 1.1 abzielt, muss diese COM-Objekt nur die Methoden der implementieren `ICorProfilerCallback`. Wenn .NET Framework, Version 2.0 anvisierte und höher, muss das COM-Objekt auch die Methoden der implementieren `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
