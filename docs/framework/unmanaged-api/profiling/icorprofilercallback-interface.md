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
ms.openlocfilehash: 6a53b9b1b061c2ca07a469abc78c07ed9e710069
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500090"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback-Schnittstelle
Stellt Methoden bereit, die vom Common Language Runtime (CLR) verwendet werden, um einen Codeprofiler zu benachrichtigen, wenn die Ereignisse, die der Profiler abonniert hat, auftreten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[AppDomainCreationFinished-Methode](icorprofilercallback-appdomaincreationfinished-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.|  
|[AppDomainCreationStarted-Methode](icorprofilercallback-appdomaincreationstarted-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wird.|  
|[AppDomainShutdownFinished-Methode](icorprofilercallback-appdomainshutdownfinished-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wurde.|  
|[AppDomainShutdownStarted-Methode](icorprofilercallback-appdomainshutdownstarted-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wird.|  
|[AssemblyLoadFinished-Methode](icorprofilercallback-assemblyloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Assembly den Ladevorgang abgeschlossen hat.|  
|[AssemblyLoadStarted-Methode](icorprofilercallback-assemblyloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Assembly geladen wird.|  
|[AssemblyUnloadFinished-Methode](icorprofilercallback-assemblyunloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Assembly entladen wurde.|  
|[AssemblyUnloadStarted-Methode](icorprofilercallback-assemblyunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Assembly entladen wird.|  
|[ClassLoadFinished-Methode](icorprofilercallback-classloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse den Ladevorgang abgeschlossen hat.|  
|[ClassLoadStarted-Methode](icorprofilercallback-classloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse geladen wird.|  
|[ClassUnloadFinished-Methode](icorprofilercallback-classunloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse das entladen abgeschlossen hat.|  
|[ClassUnloadStarted-Methode](icorprofilercallback-classunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse entladen wird.|  
|[COMClassicVTableCreated-Methode](icorprofilercallback-comclassicvtablecreated-method.md)|Benachrichtigt den Profiler, dass ein Runtime Callable Wrapper (RCW) für die angegebene IID und die angegebene Klasse erstellt wurde.|  
|[COMClassicVTableDestroyed-Methode](icorprofilercallback-comclassicvtabledestroyed-method.md)|Benachrichtigt den Profiler, dass ein RCW zerstört wird.|  
|[ExceptionCatcherEnter-Methode](icorprofilercallback-exceptioncatcherenter-method.md)|Benachrichtigt den Profiler, dass das Steuerelement an den entsprechenden-Block übermittelt wird `catch` .|  
|[ExceptionCatcherLeave-Methode](icorprofilercallback-exceptioncatcherleave-method.md)|Benachrichtigt den Profiler, dass das Steuerelement aus dem entsprechenden-Block herausgegeben wird `catch` .|  
|[ExceptionCLRCatcherExecute-Methode](icorprofilercallback-exceptionclrcatcherexecute-method.md)|Veraltet in der .NET Framework Version 2,0.|  
|[ExceptionCLRCatcherFound-Methode](icorprofilercallback-exceptionclrcatcherfound-method.md)|Veraltet in .NET Framework 2,0.|  
|[ExceptionOSHandlerEnter-Methode](icorprofilercallback-exceptionoshandlerenter-method.md)|Nicht implementiert. Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.|  
|[ExceptionOSHandlerLeave-Methode](icorprofilercallback-exceptionoshandlerleave-method.md)|Nicht implementiert. Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.|  
|[ExceptionSearchCatcherFound-Methode](icorprofilercallback-exceptionsearchcatcherfound-method.md)|Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung einen Handler für die ausgelöste Ausnahme gefunden hat.|  
|[ExceptionSearchFilterEnter-Methode](icorprofilercallback-exceptionsearchfilterenter-method.md)|Benachrichtigt den Profiler, dass ein Benutzer Filter ausgeführt wird.|  
|[ExceptionSearchFilterLeave-Methode](icorprofilercallback-exceptionsearchfilterleave-method.md)|Benachrichtigt den Profiler, dass die Ausführung eines Benutzer Filters soeben abgeschlossen ist.|  
|[ExceptionSearchFunctionEnter-Methode](icorprofilercallback-exceptionsearchfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung in eine Funktion eingetreten ist.|  
|[ExceptionSearchFunctionLeave-Methode](icorprofilercallback-exceptionsearchfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung das Durchsuchen einer Funktion abgeschlossen hat.|  
|[ExceptionThrown-Methode](icorprofilercallback-exceptionthrown-method.md)|Benachrichtigt den Profiler, dass eine Ausnahme ausgelöst wurde.|  
|[ExceptionUnwindFinallyEnter-Methode](icorprofilercallback-exceptionunwindfinallyenter-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung in eine `finally` in der angegebenen Funktion enthaltene Klausel eintritt.|  
|[ExceptionUnwindFinallyLeave-Methode](icorprofilercallback-exceptionunwindfinallyleave-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung eine-Klausel hinterlassen hat `finally` .|  
|[ExceptionUnwindFunctionEnter-Methode](icorprofilercallback-exceptionunwindfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung in eine Funktion eingetreten ist.|  
|[ExceptionUnwindFunctionLeave-Methode](icorprofilercallback-exceptionunwindfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung das Entladen einer Funktion abgeschlossen hat.|  
|[FunctionUnloadStarted-Methode](icorprofilercallback-functionunloadstarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit begonnen hat, eine Funktion zu entladen.|  
|[Initialize-Methode](icorprofilercallback-initialize-method.md)|Wird aufgerufen, um den Profiler zu initialisieren, wenn eine neue CLR-Anwendung gestartet wird.|  
|[JITCachedFunctionSearchFinished-Methode](icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen wurde, die zuvor mithilfe von "ngen. exe" kompiliert wurde.|  
|[JITCachedFunctionSearchStarted-Methode](icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion gestartet wurde, die zuvor mithilfe von "ngen. exe" kompiliert wurde.|  
|[JITCompilationFinished-Methode](icorprofilercallback-jitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler die Kompilierung einer Funktion abgeschlossen hat.|  
|[JITCompilationStarted-Methode](icorprofilercallback-jitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion gestartet hat.|  
|[JITFunctionPitched-Methode](icorprofilercallback-jitfunctionpitched-method.md)|Benachrichtigt den Profiler, dass eine JIT-kompilierte Funktion aus dem Arbeitsspeicher entfernt wurde.|  
|[JITInlining-Methode](icorprofilercallback-jitinlining-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler im Begriff ist, eine Funktion in einer anderen Funktion einzufügen.|  
|[ManagedToUnmanagedTransition-Methode](icorprofilercallback-managedtounmanagedtransition-method.md)|Benachrichtigt den Profiler, dass ein Übergang von verwaltetem Code zu nicht verwaltetem Code erfolgt ist.|  
|[ModuleAttachedToAssembly-Methode](icorprofilercallback-moduleattachedtoassembly-method.md)|Benachrichtigt den Profiler, dass ein Modul an die übergeordnete Assembly angefügt wird.|  
|[ModuleLoadFinished-Methode](icorprofilercallback-moduleloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul den Ladevorgang abgeschlossen hat.|  
|[ModuleLoadStarted-Methode](icorprofilercallback-moduleloadstarted-method.md)|Benachrichtigt den Profiler, dass ein Modul geladen wird.|  
|[ModuleUnloadFinished-Methode](icorprofilercallback-moduleunloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul das entladen abgeschlossen hat.|  
|[ModuleUnloadStarted-Methode](icorprofilercallback-moduleunloadstarted-method.md)|Benachrichtigt den Profiler, dass ein Modul entladen wird.|  
|[MovedReferences-Methode](icorprofilercallback-movedreferences-method.md)|Benachrichtigt den Profiler über Objekt Verweise, die während Garbage Collection verschoben wurden.|  
|[ObjectAllocated-Methode](icorprofilercallback-objectallocated-method.md)|Benachrichtigt den Profiler, dass der Arbeitsspeicher im Heap für ein Objekt zugeordnet wurde.|  
|[ObjectReferences-Methode](icorprofilercallback-objectreferences-method.md)|Benachrichtigt den Profiler über Objekte im Speicher, auf die vom angegebenen-Objekt verwiesen wird.|  
|[ObjectsAllocatedByClass-Methode](icorprofilercallback-objectsallocatedbyclass-method.md)|Benachrichtigt den Profiler über die Anzahl von Instanzen der angegebenen Klasse, die seit dem vorherigen Garbage Collection erstellt wurden.|  
|[RemotingClientInvocationFinished-Methode](icorprofilercallback-remotingclientinvocationfinished-method.md)|Benachrichtigt den Profiler, dass ein Remotingaufrufe auf dem Client ausgeführt werden muss.|  
|[RemotingClientInvocationStarted-Methode](icorprofilercallback-remotingclientinvocationstarted-method.md)|Benachrichtigt den Profiler, dass ein remotingbefehl gestartet wurde.|  
|[RemotingClientReceivingReply-Methode](icorprofilercallback-remotingclientreceivingreply-method.md)|Benachrichtigt den Profiler, dass der serverseitige Teil eines remotingaufrufes abgeschlossen wurde und der Client die Antwort nun empfängt und verarbeitet.|  
|[RemotingClientSendingMessage-Methode](icorprofilercallback-remotingclientsendingmessage-method.md)|Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.|  
|[RemotingServerInvocationReturned-Methode](icorprofilercallback-remotingserverinvocationreturned-method.md)|Benachrichtigt den Profiler, dass der Prozess den Aufruf einer Methode als Reaktion auf eine Anforderung für eine Remote Methodenaufruf abgeschlossen hat.|  
|[RemotingServerInvocationStarted-Methode](icorprofilercallback-remotingserverinvocationstarted-method.md)|Benachrichtigt den Profiler, dass der Prozess eine Methode als Reaktion auf eine Aufruf Anforderung für eine Remote Methode aufruft.|  
|[RemotingServerReceivingMessage-Methode](icorprofilercallback-remotingserverreceivingmessage-method.md)|Benachrichtigt den Profiler, dass der Prozess eine Remote Methodenaufruf-oder Aktivierungs Anforderung empfängt.|  
|[RemotingServerSendingReply-Methode](icorprofilercallback-remotingserversendingreply-method.md)|Benachrichtigt den Profiler, dass der Prozess die Verarbeitung einer Remote Methodenaufruf Anforderung abgeschlossen hat und die Antwort über einen Kanal überträgt.|  
|[RootReferences-Methode](icorprofilercallback-rootreferences-method.md)|Benachrichtigt den Profiler über Informationen über Stamm Verweise nach Garbage Collection.|  
|[RuntimeResumeFinished-Methode](icorprofilercallback-runtimeresumefinished-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortgesetzt hat und an den normalen Vorgang zurückgegeben wurde.|  
|[RuntimeResumeStarted-Methode](icorprofilercallback-runtimeresumestarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortsetzt.|  
|[RuntimeSuspendAborted-Methode](icorprofilercallback-runtimesuspendaborted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit die ausgeführte Lauf Zeit Unterbrechung abgebrochen hat.|  
|[RuntimeSuspendFinished-Methode](icorprofilercallback-runtimesuspendfinished-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads angehalten hat.|  
|[RuntimeSuspendStarted-Methode](icorprofilercallback-runtimesuspendstarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads aussetzen soll.|  
|[RuntimeThreadResumed-Methode](icorprofilercallback-runtimethreadresumed-method.md)|Benachrichtigt den Profiler, dass der angegebene Thread nach dem aussetzen fortgesetzt wurde.|  
|[RuntimeThreadSuspended-Methode](icorprofilercallback-runtimethreadsuspended-method.md)|Benachrichtigt den Profiler, dass der angegebene Thread angehalten wurde oder gerade angehalten wird.|  
|[Shutdown-Methode](icorprofilercallback-shutdown-method.md)|Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.|  
|[ThreadAssignedToOSThread-Methode](icorprofilercallback-threadassignedtoosthread-method.md)|Benachrichtigt den Profiler, dass ein verwalteter Thread mit einem bestimmten Betriebssystem Thread (OS) implementiert wird.|  
|[ThreadCreated-Methode](icorprofilercallback-threadcreated-method.md)|Benachrichtigt den Profiler, dass ein Thread erstellt wurde.|  
|[ThreadDestroyed-Methode](icorprofilercallback-threaddestroyed-method.md)|Benachrichtigt den Profiler, dass ein Thread zerstört wurde.|  
|[UnmanagedToManagedTransition-Methode](icorprofilercallback-unmanagedtomanagedtransition-method.md)|Benachrichtigt den Profiler, dass ein Übergang von nicht verwaltetem Code zu verwaltetem Code erfolgt ist.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR ruft eine Methode in der- `ICorProfilerCallback` Schnittstelle (oder der [ICorProfilerCallback2](icorprofilercallback2-interface.md)) auf, um den Profiler zu benachrichtigen, wenn ein Ereignis auftritt, das der Profiler abonniert hat. Dies ist die primäre Rückruf Schnittstelle, über die die CLR mit dem Codeprofiler kommuniziert.  
  
 Ein Codeprofiler muss die Methoden der- `ICorProfilerCallback` Schnittstelle implementieren. Für den .NET Framework, Version 2,0 oder höher, muss der Profiler auch die- `ICorProfilerCallback2` Methoden implementieren. Jede Methoden Implementierung muss ein HRESULT zurückgeben, das bei Erfolg oder E_FAIL bei einem Fehler den Wert S_OK hat. Derzeit ignoriert die CLR das HRESULT, das von jedem Rückruf zurückgegeben wird, mit Ausnahme von [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
 In der Microsoft Windows-Registrierung muss ein Codeprofiler sein Component Object Model (com)-Objekt registrieren, das die `ICorProfilerCallback` -Schnittstelle und die-Schnittstelle implementiert `ICorProfilerCallback2` . Ein Codeprofiler abonniert die Ereignisse, für die er eine Benachrichtigung erhalten möchte, indem er [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)anfordert. Dies erfolgt in der Regel in der Implementierung von [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)durch den Profiler. Der Profiler kann dann eine Benachrichtigung von der Laufzeit empfangen, wenn ein Ereignis im Begriff ist oder gerade in einem ausgeführten Lauf Zeit Prozess aufgetreten ist.  
  
> [!NOTE]
> Der Profiler registriert ein einzelnes COM-Objekt. Wenn der Profiler auf die .NET Framework Version 1,0 oder 1,1 abzielt, muss dieses COM-Objekt nur die Methoden von implementieren `ICorProfilerCallback` . Wenn .NET Framework Version 2,0 oder höher als Zielversion verwendet wird, muss das COM-Objekt auch die Methoden von implementieren `ICorProfilerCallback2` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
- [ICorProfilerCallback3-Schnittstelle](icorprofilercallback3-interface.md)
- [ICorProfilerCallback4-Schnittstelle](icorprofilercallback4-interface.md)
