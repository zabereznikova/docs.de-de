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
ms.openlocfilehash: 487f347c19ab513f328a9f1a02601fc72c233eb5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449929"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback-Schnittstelle
Stellt Methoden bereit, die vom Common Language Runtime (CLR) verwendet werden, um einen Codeprofiler zu benachrichtigen, wenn die Ereignisse, die der Profiler abonniert hat, auftreten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AppDomainCreationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.|  
|[AppDomainCreationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wird.|  
|[AppDomainShutdownFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wurde.|  
|[AppDomainShutdownStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wird.|  
|[AssemblyLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Assembly den Ladevorgang abgeschlossen hat.|  
|[AssemblyLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Assembly geladen wird.|  
|[AssemblyUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Assembly entladen wurde.|  
|[AssemblyUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Assembly entladen wird.|  
|[ClassLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse den Ladevorgang abgeschlossen hat.|  
|[ClassLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse geladen wird.|  
|[ClassUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse das entladen abgeschlossen hat.|  
|[ClassUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse entladen wird.|  
|[COMClassicVTableCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Benachrichtigt den Profiler, dass ein Runtime Callable Wrapper (RCW) für die angegebene IID und die angegebene Klasse erstellt wurde.|  
|[COMClassicVTableDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Benachrichtigt den Profiler, dass ein RCW zerstört wird.|  
|[ExceptionCatcherEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Benachrichtigt den Profiler, dass das Steuerelement an den entsprechenden `catch`-Block übermittelt wird.|  
|[ExceptionCatcherLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Benachrichtigt den Profiler, dass das Steuerelement aus dem entsprechenden `catch`-Block herausgegeben wird.|  
|[ExceptionCLRCatcherExecute-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Veraltet in der .NET Framework Version 2,0.|  
|[ExceptionCLRCatcherFound-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Veraltet in .NET Framework 2,0.|  
|[ExceptionOSHandlerEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Nicht implementiert. Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.|  
|[ExceptionOSHandlerLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Nicht implementiert. Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.|  
|[ExceptionSearchCatcherFound-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung einen Handler für die ausgelöste Ausnahme gefunden hat.|  
|[ExceptionSearchFilterEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Benachrichtigt den Profiler, dass ein Benutzer Filter ausgeführt wird.|  
|[ExceptionSearchFilterLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Benachrichtigt den Profiler, dass die Ausführung eines Benutzer Filters soeben abgeschlossen ist.|  
|[ExceptionSearchFunctionEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung in eine Funktion eingetreten ist.|  
|[ExceptionSearchFunctionLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung das Durchsuchen einer Funktion abgeschlossen hat.|  
|[ExceptionThrown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Benachrichtigt den Profiler, dass eine Ausnahme ausgelöst wurde.|  
|[ExceptionUnwindFinallyEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung in eine `finally`-Klausel wechselt, die in der angegebenen Funktion enthalten ist.|  
|[ExceptionUnwindFinallyLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung eine `finally`-Klausel hinterlassen hat.|  
|[ExceptionUnwindFunctionEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung in eine Funktion eingetreten ist.|  
|[ExceptionUnwindFunctionLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung das Entladen einer Funktion abgeschlossen hat.|  
|[FunctionUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit begonnen hat, eine Funktion zu entladen.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Wird aufgerufen, um den Profiler zu initialisieren, wenn eine neue CLR-Anwendung gestartet wird.|  
|[JITCachedFunctionSearchFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen wurde, die zuvor mithilfe von "ngen. exe" kompiliert wurde.|  
|[JITCachedFunctionSearchStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion gestartet wurde, die zuvor mithilfe von "ngen. exe" kompiliert wurde.|  
|[JITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler die Kompilierung einer Funktion abgeschlossen hat.|  
|[JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion gestartet hat.|  
|[JITFunctionPitched-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Benachrichtigt den Profiler, dass eine JIT-kompilierte Funktion aus dem Arbeitsspeicher entfernt wurde.|  
|[JITInlining-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler im Begriff ist, eine Funktion in einer anderen Funktion einzufügen.|  
|[ManagedToUnmanagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Benachrichtigt den Profiler, dass ein Übergang von verwaltetem Code zu nicht verwaltetem Code erfolgt ist.|  
|[ModuleAttachedToAssembly-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Benachrichtigt den Profiler, dass ein Modul an die übergeordnete Assembly angefügt wird.|  
|[ModuleLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul den Ladevorgang abgeschlossen hat.|  
|[ModuleLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Benachrichtigt den Profiler, dass ein Modul geladen wird.|  
|[ModuleUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul das entladen abgeschlossen hat.|  
|[ModuleUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Benachrichtigt den Profiler, dass ein Modul entladen wird.|  
|[MovedReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Benachrichtigt den Profiler über Objekt Verweise, die während Garbage Collection verschoben wurden.|  
|[ObjectAllocated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Benachrichtigt den Profiler, dass der Arbeitsspeicher im Heap für ein Objekt zugeordnet wurde.|  
|[ObjectReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Benachrichtigt den Profiler über Objekte im Speicher, auf die vom angegebenen-Objekt verwiesen wird.|  
|[ObjectsAllocatedByClass-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Benachrichtigt den Profiler über die Anzahl von Instanzen der angegebenen Klasse, die seit dem vorherigen Garbage Collection erstellt wurden.|  
|[RemotingClientInvocationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Benachrichtigt den Profiler, dass ein Remotingaufrufe auf dem Client ausgeführt werden muss.|  
|[RemotingClientInvocationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Benachrichtigt den Profiler, dass ein remotingbefehl gestartet wurde.|  
|[RemotingClientReceivingReply-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Benachrichtigt den Profiler, dass der serverseitige Teil eines remotingaufrufes abgeschlossen wurde und der Client die Antwort nun empfängt und verarbeitet.|  
|[RemotingClientSendingMessage-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.|  
|[RemotingServerInvocationReturned-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Benachrichtigt den Profiler, dass der Prozess den Aufruf einer Methode als Reaktion auf eine Anforderung für eine Remote Methodenaufruf abgeschlossen hat.|  
|[RemotingServerInvocationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Benachrichtigt den Profiler, dass der Prozess eine Methode als Reaktion auf eine Aufruf Anforderung für eine Remote Methode aufruft.|  
|[RemotingServerReceivingMessage-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Benachrichtigt den Profiler, dass der Prozess eine Remote Methodenaufruf-oder Aktivierungs Anforderung empfängt.|  
|[RemotingServerSendingReply-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Benachrichtigt den Profiler, dass der Prozess die Verarbeitung einer Remote Methodenaufruf Anforderung abgeschlossen hat und die Antwort über einen Kanal überträgt.|  
|[RootReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Benachrichtigt den Profiler über Informationen über Stamm Verweise nach Garbage Collection.|  
|[RuntimeResumeFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortgesetzt hat und an den normalen Vorgang zurückgegeben wurde.|  
|[RuntimeResumeStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortsetzt.|  
|[RuntimeSuspendAborted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit die ausgeführte Lauf Zeit Unterbrechung abgebrochen hat.|  
|[RuntimeSuspendFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads angehalten hat.|  
|[RuntimeSuspendStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads aussetzen soll.|  
|[RuntimeThreadResumed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Benachrichtigt den Profiler, dass der angegebene Thread nach dem aussetzen fortgesetzt wurde.|  
|[RuntimeThreadSuspended-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Benachrichtigt den Profiler, dass der angegebene Thread angehalten wurde oder gerade angehalten wird.|  
|[Shutdown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.|  
|[ThreadAssignedToOSThread-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Benachrichtigt den Profiler, dass ein verwalteter Thread mit einem bestimmten Betriebssystem Thread (OS) implementiert wird.|  
|[ThreadCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Benachrichtigt den Profiler, dass ein Thread erstellt wurde.|  
|[ThreadDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Benachrichtigt den Profiler, dass ein Thread zerstört wurde.|  
|[UnmanagedToManagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Benachrichtigt den Profiler, dass ein Übergang von nicht verwaltetem Code zu verwaltetem Code erfolgt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft eine Methode in der `ICorProfilerCallback`-Schnittstelle (oder [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) auf, um den Profiler zu benachrichtigen, wenn ein Ereignis auftritt, das der Profiler abonniert hat. Dies ist die primäre Rückruf Schnittstelle, über die die CLR mit dem Codeprofiler kommuniziert.  
  
 Ein Codeprofiler muss die Methoden der `ICorProfilerCallback`-Schnittstelle implementieren. Für den .NET Framework, Version 2,0 oder höher, muss der Profiler auch die `ICorProfilerCallback2`-Methoden implementieren. Jede Methoden Implementierung muss ein HRESULT zurückgeben, das bei Erfolg oder E_FAIL bei einem Fehler den Wert S_OK hat. Derzeit ignoriert die CLR das HRESULT, das von jedem Rückruf zurückgegeben wird, mit Ausnahme von [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 In der Microsoft Windows-Registrierung muss ein Codeprofiler sein Component Object Model (com)-Objekt registrieren, das die Schnittstellen `ICorProfilerCallback` und `ICorProfilerCallback2` implementiert. Ein Codeprofiler abonniert die Ereignisse, für die er eine Benachrichtigung erhalten möchte, indem er [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)anfordert. Dies erfolgt in der Regel in der Implementierung von [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)durch den Profiler. Der Profiler kann dann eine Benachrichtigung von der Laufzeit empfangen, wenn ein Ereignis im Begriff ist oder gerade in einem ausgeführten Lauf Zeit Prozess aufgetreten ist.  
  
> [!NOTE]
> Der Profiler registriert ein einzelnes COM-Objekt. Wenn der Profiler auf die .NET Framework Version 1,0 oder 1,1 abzielt, muss dieses COM-Objekt nur die Methoden von `ICorProfilerCallback`implementieren. Wenn .NET Framework Version 2,0 oder höher als Zielversion verwendet wird, muss das COM-Objekt auch die Methoden von `ICorProfilerCallback2`implementieren.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
