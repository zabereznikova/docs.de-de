---
title: ICorProfilerCallback2-Schnittstelle
ms.date: 03/30/2017
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
ms.openlocfilehash: a7867c63f76db38a16784c03fadd9fc917ecc4e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439682"
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2-Schnittstelle
Stellt Methoden bereit, die vom Common Language Runtime (CLR) verwendet werden, um einen Codeprofiler zu benachrichtigen, wenn die Ereignisse, die der Profiler abonniert hat, auftreten. Die `ICorProfilerCallback2`-Schnittstelle ist eine Erweiterung der [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) -Schnittstelle. Das heißt, es werden neue Rückrufe bereitstellt, die in der .NET Framework Version 2,0 eingeführt wurden.  
  
> [!NOTE]
> Jede Methoden Implementierung muss ein HRESULT mit dem Wert S_OK bei Erfolg oder E_FAIL bei einem Fehler zurückgeben. Derzeit ignoriert die CLR das HRESULT, das von jedem Rückruf zurückgegeben wird, mit Ausnahme von [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[FinalizeableObjectQueued-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|Benachrichtigt den Codeprofiler, dass ein Objekt mit einem Finalizer für die Ausführung seiner `Finalize` Methode in die Warteschlange für den Finalizerthread eingereiht wurde.|  
|[GarbageCollectionFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|Benachrichtigt den Profiler, dass ein Garbage Collection abgeschlossen wurde und alle Garbage Collection Rückrufe dafür ausgegeben wurden.|  
|[GarbageCollectionStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|Benachrichtigt den Codeprofiler, dass ein Garbage Collection gestartet wurde.|  
|[HandleCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|Benachrichtigt den Codeprofiler, dass ein Garbage Collection Handle erstellt wurde.|  
|[HandleDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|Benachrichtigt den Codeprofiler, dass ein Garbage Collection Handle zerstört wurde.|  
|[RootReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|Benachrichtigt den Profiler über Stamm Verweise, nachdem ein Garbage Collection aufgetreten ist. Diese Methode ist eine Erweiterung der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) -Methode.|  
|[SurvivingReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|Benachrichtigt den Profiler über Objekt Verweise, die eine Garbage Collection noch nicht vorhanden sind.|  
|[ThreadNameChanged-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|Benachrichtigt den Codeprofiler, dass sich der Name eines Threads geändert hat.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft eine Methode in der `ICorProfilerCallback` (oder `ICorProfilerCallback2`)-Schnittstelle auf, um den Profiler zu benachrichtigen, wenn ein Ereignis auftritt, das der Profiler abonniert hat. Dies ist die primäre Rückruf Schnittstelle, über die die CLR mit dem Codeprofiler kommuniziert.  
  
 Ein Codeprofiler muss die Methoden der `ICorProfilerCallback`-Schnittstelle implementieren. Für den .NET Framework 2,0 und höhere Versionen muss der Profiler auch die `ICorProfilerCallback2`-Methoden implementieren. Jede Methoden Implementierung muss ein HRESULT mit dem Wert S_OK bei Erfolg oder E_FAIL bei einem Fehler zurückgeben. Derzeit ignoriert die CLR das HRESULT, das von jedem Rückruf zurückgegeben wird, mit Ausnahme von [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Ein Codeprofiler muss sich in der Microsoft Windows-Registrierung, seinem com-Objekt, das die `ICorProfilerCallback`-und `ICorProfilerCallback2` Schnittstellen implementiert, registrieren. Ein Codeprofiler abonniert die Ereignisse, für die er eine Benachrichtigung erhalten möchte, indem er [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)anfordert. Dies erfolgt in der Regel in der Implementierung von [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)durch den Profiler. Der Profiler kann dann eine Benachrichtigung von der Laufzeit empfangen, wenn ein Ereignis im Begriff ist oder gerade in einem ausgeführten Lauf Zeit Prozess aufgetreten ist.  
  
> [!NOTE]
> Der Profiler registriert ein einzelnes COM-Objekt. Wenn der Profiler .NET Framework Version 1,0 oder 1,1 als Ziel verwendet, muss dieses COM-Objekt nur die Methoden von `ICorProfilerCallback`implementieren. Wenn .NET Framework Version 2,0 und höher als Zielversion verwendet wird, muss das COM-Objekt auch die Methoden von `ICorProfilerCallback2`implementieren.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
