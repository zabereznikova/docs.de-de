---
title: ICorProfilerCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback
helpviewer_keywords:
- ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2f474317493b3aac421ca1270ff461b97cfe027
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125936"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback-Schnittstelle
Bietet Methoden, die von der common Language Runtime (CLR) verwendet werden, um einen Codeprofiler benachrichtigt, wenn die Ereignisse, die der Profiler abonniert hat, auftreten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AppDomainCreationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Benachrichtigt den Profiler an, dass eine Anwendungsdomäne erstellt wurde.|  
|[AppDomainCreationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Benachrichtigt den Profiler an, dass eine Anwendungsdomäne erstellt wird.|  
|[AppDomainShutdownFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Benachrichtigt den Profiler an, eine Anwendungsdomäne von einem Prozess entladen wurde.|  
|[AppDomainShutdownStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Benachrichtigt den Profiler, dass von einem Prozess, eine Anwendungsdomäne entladen wird.|  
|[AssemblyLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Benachrichtigt den Profiler an, dass eine Assembly geladen wurde.|  
|[AssemblyLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Benachrichtigt den Profiler an, dass eine Assembly geladen wird.|  
|[AssemblyUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Benachrichtigt den Profiler an, dass eine Assembly entladen wurde.|  
|[AssemblyUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Assembly entladen wird.|  
|[ClassLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse vollständig geladen wurde.|  
|[ClassLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse geladen wird.|  
|[ClassUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse vollständig entladen wurde.|  
|[ClassUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse, entladen wird.|  
|[COMClassicVTableCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Benachrichtigt den Profiler an, ein Runtime callable Wrapper (RCW) für die angegebene IID und Klasse erstellt wurde.|  
|[COMClassicVTableDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Benachrichtigt den Profiler, ein RCW zerstört wird.|  
|[ExceptionCatcherEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Benachrichtigt den Profiler, das Steuerelement an den entsprechenden übergebenen `catch` Block.|  
|[ExceptionCatcherLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Benachrichtigt den Profiler, das Steuerelement aus der entsprechenden übergebenen `catch` Block.|  
|[ExceptionCLRCatcherExecute-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Veraltete in .NET Framework, Version 2.0.|  
|[ExceptionCLRCatcherFound-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|In .NET Framework 2.0 veraltet.|  
|[ExceptionOSHandlerEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Nicht implementiert. Ein Profiler, der nicht verwaltete Ausnahmeinformationen benötigt, muss diese Informationen mithilfe anderer Methoden abrufen.|  
|[ExceptionOSHandlerLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Nicht implementiert. Ein Profiler, der nicht verwaltete Ausnahmeinformationen benötigt, muss diese Informationen mithilfe anderer Methoden abrufen.|  
|[ExceptionSearchCatcherFound-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Benachrichtigt den Profiler, dass der Suchphase der Ausnahmebehandlung einen Handler für die Ausnahme gefunden, die ausgelöst wurde.|  
|[ExceptionSearchFilterEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Benachrichtigt den Profiler, dass ein Benutzerfilter ausgeführt wird.|  
|[ExceptionSearchFilterLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Benachrichtigt den Profiler, dass ein Benutzerfilter gerade beendet wurde.|  
|[ExceptionSearchFunctionEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Suchphase der Ausnahmebehandlung eine Funktion eingegeben hat.|  
|[ExceptionSearchFunctionLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Suchphase der Ausnahmebehandlung Suche in einer Funktion abgeschlossen ist.|  
|[ExceptionThrown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Benachrichtigt den Profiler an, dass eine Ausnahme ausgelöst wurde.|  
|[ExceptionUnwindFinallyEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Benachrichtigt den Profiler, die die Ausnahme behandeln Entladephase ist eine `finally` Klausel in der angegebenen Funktion enthalten.|  
|[ExceptionUnwindFinallyLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Benachrichtigt den Profiler, die der Entladephase der Behandlung verlassen hat eine `finally` Klausel.|  
|[ExceptionUnwindFunctionEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung eine Funktion eingegeben hat.|  
|[ExceptionUnwindFunctionLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung Entladung einer Funktion abgeschlossen ist.|  
|[FunctionUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit gestartet wurde, um eine Funktion zu entladen.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Wird aufgerufen, um den Profiler zu initialisieren, wenn eine neue CLR-Anwendung gestartet wird.|  
|[JITCachedFunctionSearchFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen ist, die zuvor mit NGen.exe kompiliert wurde.|  
|[JITCachedFunctionSearchStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion, die zuvor mit NGen.exe kompiliert wurde, gestartet wurde.|  
|[JITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler die Kompilierung einer Funktion abgeschlossen ist.|  
|[JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) gestartet wurde, mit der Kompilierung einer Funktion.|  
|[JITFunctionPitched-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Benachrichtigt den Profiler an, dass eine Funktion, die JIT-Kompilierung wurde aus dem Arbeitsspeicher entfernt wurde.|  
|[JITInlining-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler eine Funktion mit einer anderen Funktion eingefügt wird.|  
|[ManagedToUnmanagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Benachrichtigt den Profiler, dass ein Übergang aus verwaltetem Code an nicht verwalteten Code aufgetreten ist.|  
|[ModuleAttachedToAssembly-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Benachrichtigt den Profiler, dass ein Modul, dessen übergeordnete Assembly der angeschlossen ist.|  
|[ModuleLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul geladen wurde.|  
|[ModuleLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Benachrichtigt den Profiler, dass ein Modul geladen wird.|  
|[ModuleUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul entladen wurde.|  
|[ModuleUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Benachrichtigt den Profiler an, dass ein Modul entladen wird.|  
|[MovedReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Benachrichtigt den Profiler über Objektverweise, die während der Garbagecollection verschoben wurden.|  
|[ObjectAllocated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Benachrichtigt den Profiler, die für ein Objekt Speicher im Heap belegt wurde.|  
|[ObjectReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Benachrichtigt den Profiler zu Objekten im Arbeitsspeicher, die vom angegebenen Objekt verwiesen wird.|  
|[ObjectsAllocatedByClass-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Benachrichtigt den Profiler über die Anzahl der Instanzen der einzelnen angegebenen Klassen, die seit der letzten Garbagecollection erstellt wurden.|  
|[RemotingClientInvocationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Benachrichtigt den Profiler an, dass ein Remoteaufrufs bis zum Abschluss, auf dem Client ausgeführt wurde.|  
|[RemotingClientInvocationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Benachrichtigt den Profiler, dass ein Remoteaufrufs gestartet wurde.|  
|[RemotingClientReceivingReply-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Benachrichtigt den Profiler, die der serverseitigen Teil eines Remoteaufrufs abgeschlossen ist und der Client nun empfängt sowie über die Antwort zu verarbeiten.|  
|[RemotingClientSendingMessage-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.|  
|[RemotingServerInvocationReturned-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Benachrichtigt den Profiler, dass das Aufrufen einer Methode als Reaktion auf eine Remotemethode aufrufanforderung beendet hat.|  
|[RemotingServerInvocationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Benachrichtigt den Profiler, dass der Prozess eine Methode in der Antwort auf eine Remotemethode aufrufanforderung aufruft.|  
|[RemotingServerReceivingMessage-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Benachrichtigt den Profiler, dass der Prozess eine Remotemethode aufrufen oder die Aktivierung der Anforderung empfängt.|  
|[RemotingServerSendingReply-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Benachrichtigt den Profiler, dass der Prozess Verarbeitung eine Remotemethode aufrufen-Anforderung abgeschlossen hat und die Antwort über einen Kanal übertragen wird.|  
|[RootReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Benachrichtigt den Profiler mit Informationen über Stammverweise nach der Garbagecollection.|  
|[RuntimeResumeFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Benachrichtigt den Profiler, dass die Laufzeit verfügt über alle Common Language Runtime-Threads fortgesetzt und in den normalen Betrieb zurückgegeben hat.|  
|[RuntimeResumeStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Benachrichtigt den Profiler, dass die Runtime alle Threads der Laufzeit fortgesetzt wird.|  
|[RuntimeSuspendAborted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Benachrichtigt den Profiler, dass die Runtime die Runtime-Unterbrechung abgebrochen wurde, die aufgetreten ist.|  
|[RuntimeSuspendFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Benachrichtigt den Profiler an, die die Laufzeit Anhalten aller Threads der Laufzeit abgeschlossen wurde.|  
|[RuntimeSuspendStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Benachrichtigt den Profiler, dass die Runtime Begriff, alle Laufzeit Threads zu sperren.|  
|[RuntimeThreadResumed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Benachrichtigt den Profiler an, der angegebene Thread fortgesetzt wurde, nachdem er angehalten wurde.|  
|[RuntimeThreadSuspended-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Benachrichtigt, in denen der angegebene Thread wurde oder unterbrochen werden, den Profiler.|  
|[Shutdown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Benachrichtigt den Profiler an, dass die Anwendung heruntergefahren wird.|  
|[ThreadAssignedToOSThread-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Benachrichtigt den Profiler, dass ein verwalteter Thread mit der ein bestimmtes Betriebssystem (OS) Thread implementiert wird.|  
|[ThreadCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Benachrichtigt den Profiler an, dass ein Thread erstellt wurde.|  
|[ThreadDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Benachrichtigt den Profiler, dass ein Thread zerstört wurde.|  
|[UnmanagedToManagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Benachrichtigt den Profiler, dass ein Übergang von nicht verwaltetem Code an verwalteten Code aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft eine Methode in der `ICorProfilerCallback` (oder [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) Schnittstelle, um den Profiler, wenn ein Ereignis zu benachrichtigen, die der Profiler abonniert hat, erfolgt. Dies ist die primäre Rückrufschnittstelle, die über die CLR mit der Codeprofiler kommuniziert.  
  
 Ein Codeprofiler muss die Methoden implementieren die `ICorProfilerCallback` Schnittstelle. Für .NET Framework, Version 2.0 oder höher, der der Profiler muss auch implementieren die `ICorProfilerCallback2` Methoden. Jede Implementierung muss ein HRESULT, das den Wert S_OK bei Erfolg hat, oder E_FAIL bei einem Fehler zurückgeben. Die CLR ignoriert derzeit das HRESULT, der von jedem Rückruf mit Ausnahme zurückgegeben wird [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Ein Codeprofiler muss in der Microsoft Windows-Registrierung das Component Object Model (COM)-Objekt, das implementiert Registrieren der `ICorProfilerCallback` und `ICorProfilerCallback2` Schnittstellen. Ein Codeprofiler abonniert die Ereignisse, die für die sie die Benachrichtigung durch den Aufruf empfangen möchte [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Dies erfolgt in der Regel in der Profiler Implementierung von [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Der Profiler kann dann auf die Benachrichtigung von der Laufzeit, wenn ein Ereignis eintritt oder ist nur in einem ausgeführten Common Language Runtime-Prozess aufgetreten.  
  
> [!NOTE]
>  Der Profiler wird ein einzelnes COM-Objekt registriert. Wenn der Profiler wird auf .NET Framework, Version 1.0 oder 1.1, COM, muss das Objekt nur die Methoden implementieren `ICorProfilerCallback`. Wenn sie .NET Framework, Version 2.0 oder höher abzielt, muss das COM-Objekt auch die Methoden der implementieren `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
