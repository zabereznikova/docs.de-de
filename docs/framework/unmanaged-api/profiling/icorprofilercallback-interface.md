---
title: ICorProfilerCallback-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback
helpviewer_keywords: ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type: apiref
caps.latest.revision: "29"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4a53687c473a87edae38207c44f89f0140f8ccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback-Schnittstelle
Enthält Methoden, die von der common Language Runtime (CLR) verwendet werden, um einen Codeprofiler benachrichtigt, wenn die Ereignisse, die der Profiler abonniert hat, auftreten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AppDomainCreationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.|  
|[AppDomainCreationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wird.|  
|[AppDomainShutdownFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Benachrichtigt den Profiler, dass eine Anwendungsdomäne aus einem Prozess entladen wurde.|  
|[AppDomainShutdownStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Benachrichtigt den Profiler, dass von einem Prozess eine Anwendungsdomäne entladen wird.|  
|[AssemblyLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Assembly geladen wurde.|  
|[AssemblyLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Assembly geladen wird.|  
|[AssemblyUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Assembly entladen wurde.|  
|[AssemblyUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Assembly entladen wird.|  
|[ClassLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse vollständig geladen wurde.|  
|[ClassLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse geladen wird.|  
|[ClassUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Benachrichtigt den Profiler, dass eine Klasse entladen wurde.|  
|[ClassUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Benachrichtigt den Profiler, dass eine Klasse entladen wird.|  
|[COMClassicVTableCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Benachrichtigt den Profiler, dass ein Runtime callable Wrapper (RCW) für die angegebene IID und Klasse erstellt wurde.|  
|[COMClassicVTableDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Benachrichtigt den Profiler, ein RCW zerstört wird.|  
|[ExceptionCatcherEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Benachrichtigt den Profiler, der in das entsprechende Steuerelement übergeben wird `catch` Block.|  
|[ExceptionCatcherLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Benachrichtigt den Profiler, der aus der entsprechenden Steuerelement übergeben wird `catch` Block.|  
|[ExceptionCLRCatcherExecute-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Veraltet in .NET Framework, Version 2.0.|  
|[ExceptionCLRCatcherFound-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Veraltet in .NET Framework 2.0.|  
|[ExceptionOSHandlerEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Nicht implementiert. Ein Profiler, der nicht verwaltete Ausnahmeinformationen benötigt, muss diese Informationen mithilfe anderer Methoden abrufen.|  
|[ExceptionOSHandlerLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Nicht implementiert. Ein Profiler, der nicht verwaltete Ausnahmeinformationen benötigt, muss diese Informationen mithilfe anderer Methoden abrufen.|  
|[ExceptionSearchCatcherFound-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Benachrichtigt den Profiler, dass die Suchphase der Ausnahmebehandlung an einen Handler für die Ausnahme gefunden, die ausgelöst wurde.|  
|[ExceptionSearchFilterEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Benachrichtigt den Profiler, dass ein Benutzerfilter ausgeführt wird.|  
|[ExceptionSearchFilterLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Benachrichtigt den Profiler, dass ein Benutzerfilter gerade beendet wurde.|  
|[ExceptionSearchFunctionEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Suchphase der Ausnahmebehandlung eine Funktion eingegeben hat.|  
|[ExceptionSearchFunctionLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Suchphase der Ausnahmebehandlung Suche in einer Funktion abgeschlossen wurde.|  
|[ExceptionThrown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Benachrichtigt den Profiler, dass eine Ausnahme ausgelöst wurde.|  
|[ExceptionUnwindFinallyEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Benachrichtigt den Profiler, die die Ausnahme behandeln Entladephase ist eine `finally` Klausel in der angegebenen Funktion enthalten.|  
|[ExceptionUnwindFinallyLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Benachrichtigt den Profiler, die der Entladephase der Behandlung verlassen hat eine `finally` Klausel.|  
|[ExceptionUnwindFunctionEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung eine Funktion eingegeben hat.|  
|[ExceptionUnwindFunctionLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung Entladung einer funktionsrückgabewerts abgeschlossen wurde.|  
|[FunctionUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit gestartet wurde, um eine Funktion zu entladen.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Wird aufgerufen, um den Profiler zu initialisieren, wenn eine neue CLR-Anwendung gestartet wird.|  
|[JITCachedFunctionSearchFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen ist, die vorher mit NGen.exe kompiliert wurde.|  
|[JITCachedFunctionSearchStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Benachrichtigt den Profiler, dass eine Suche für eine Funktion, die vorher mit NGen.exe kompiliert wurde, gestartet wurde.|  
|[JITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Benachrichtigt den Profiler, dass der JIT-Compiler Kompilieren eine Funktion abgeschlossen wurde.|  
|[JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler zum Kompilieren einer funktionsrückgabewerts gestartet wurde.|  
|[JITFunctionPitched-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Benachrichtigt den Profiler, dass eine Funktion, die JIT-kompiliert wurde aus dem Arbeitsspeicher entfernt wurde.|  
|[JITInlining-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Benachrichtigt den Profiler, wie der JIT-Compiler eine Funktion mit einer anderen Funktion einfügen.|  
|[ManagedToUnmanagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Benachrichtigt den Profiler, dass Übergang von verwaltetem Code in nicht verwaltetem Code aufgetreten ist.|  
|[ModuleAttachedToAssembly-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Benachrichtigt den Profiler, dass ein Modul an seine übergeordnete Assembly verbunden ist.|  
|[ModuleLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul geladen wurde.|  
|[ModuleLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Benachrichtigt den Profiler, dass ein Modul geladen wird.|  
|[ModuleUnloadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Benachrichtigt den Profiler, dass ein Modul entladen wurde.|  
|[ModuleUnloadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Benachrichtigt den Profiler, dass ein Modul entladen wird.|  
|[MovedReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Benachrichtigt den Profiler über Objektverweise, die während der Garbagecollection verschoben wurden.|  
|[ObjectAllocated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Benachrichtigt den Profiler, der Speicher im Heap für ein Objekt zugewiesen wurde.|  
|[ObjectReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Benachrichtigt den Profiler zu Objekten im Arbeitsspeicher, die vom angegebenen Objekt verwiesen wird.|  
|[ObjectsAllocatedByClass-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Benachrichtigt den Profiler über die Anzahl der Instanzen jeder angegebenen Klasse, die seit der letzten Garbagecollection erstellt wurden.|  
|[RemotingClientInvocationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Benachrichtigt den Profiler, dass ein Remotingaufruf auf dem Client bis zum Abschluss ausgeführt wurde.|  
|[RemotingClientInvocationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Benachrichtigt den Profiler, ein Remotingaufruf gestartet hat.|  
|[RemotingClientReceivingReply-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Benachrichtigt den Profiler, die der serverseitigen Teil eines Remotingaufrufs abgeschlossen ist und der Client ist jetzt empfängt und verarbeitet die Antwort.|  
|[RemotingClientSendingMessage-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server gesendet wird.|  
|[RemotingServerInvocationReturned-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Benachrichtigt den Profiler, dass das Aufrufen einer Methode als Reaktion auf eine Remotemethode Aufruf-Anforderung abgeschlossen wurde.|  
|[RemotingServerInvocationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Benachrichtigt den Profiler, dass der Prozess eine Methode als Reaktion auf eine Remotemethode Aufruf Anforderung aufruft.|  
|[RemotingServerReceivingMessage-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Benachrichtigt den Profiler, dass der Prozess eine remote-Methode aufrufen oder die Aktivierung der Anforderung empfängt.|  
|[RemotingServerSendingReply-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Benachrichtigt den Profiler, dass der Prozess die Verarbeitung einer Remotemethode Aufruf-Anforderung abgeschlossen und die Antwort über einen Kanal übertragen wird hat.|  
|[RootReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Benachrichtigt den Profiler mit Informationen zu Stammverweisen nach der Garbagecollection.|  
|[RuntimeResumeFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Benachrichtigt den Profiler, dass die Common Language Runtime alle Runtime Threads fortgesetzt wurde und zu einem normalen Betrieb zurückgegeben hat.|  
|[RuntimeResumeStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Benachrichtigt den Profiler, dass die Common Language Runtime alle zur Laufzeit Threads fortgesetzt wird.|  
|[RuntimeSuspendAborted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Benachrichtigt den Profiler, dass die Common Language Runtime die Aussetzung der Run-Time abgebrochen wurde, die aufgetreten ist.|  
|[RuntimeSuspendFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Benachrichtigt den Profiler an, die die Common Language Runtime Anhalten des Threads für alle zur Laufzeit abgeschlossen ist.|  
|[RuntimeSuspendStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Benachrichtigt den Profiler, dass die Laufzeit alle zur Laufzeit Threads anhalten.|  
|[RuntimeThreadResumed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Benachrichtigt den Profiler an, der angegebene Thread fortgesetzt wurde, nachdem er angehalten wurde.|  
|[RuntimeThreadSuspended-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Benachrichtigt den Profiler an, der angegebene Thread wurde oder angehalten werden soll, ist.|  
|[Shutdown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.|  
|[ThreadAssignedToOSThread-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Benachrichtigt den Profiler, dass ein verwalteter Thread mit einem bestimmten Betriebssystem (BS)-Thread implementiert wird.|  
|[ThreadCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Benachrichtigt den Profiler, dass ein Thread erstellt wurde.|  
|[ThreadDestroyed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Benachrichtigt den Profiler, dass ein Thread zerstört wurden.|  
|[UnmanagedToManagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Benachrichtigt den Profiler, dass ein Übergang zwischen nicht verwaltetem Code zu verwaltetem Code aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft eine Methode in der `ICorProfilerCallback` (oder [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) Schnittstelle, um den Profiler, wenn ein Ereignis benachrichtigt, die der Profiler abonniert hat, tritt auf. Dies ist die primäre Rückrufschnittstelle, die über die CLR mit der Codeprofiler kommuniziert.  
  
 Ein Codeprofiler muss die Methoden implementieren die `ICorProfilerCallback` Schnittstelle. Der Profiler muss für .NET Framework, Version 2.0 oder höher, auch implementieren die `ICorProfilerCallback2` Methoden. Jede Implementierung muss ein HRESULT, dessen Wert bei Erfolg S_OK oder E_FAIL bei einem Fehler zurückgeben. Die CLR ignoriert derzeit das HRESULT, das von jedem Rückruf außer zurückgegeben wird [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Ein Codeprofiler muss in der Microsoft Windows-Registrierung ein Component Object Model (COM)-Objekt, das implementiert Registrieren der `ICorProfilerCallback` und `ICorProfilerCallback2` Schnittstellen. Ein Codeprofiler abonniert die Ereignisse, die für die Benachrichtigung durch den Aufruf zugriffsdrosselung [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Dies erfolgt in der Regel in der Profiler-Implementierung von [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Der Profiler kann dann Benachrichtigung von der Runtime erhalten, wenn ein Ereignis ausgeführt wird oder nur in einer ausgeführten Laufzeitprozess Fehler.  
  
> [!NOTE]
>  Der Profiler registriert ein einzelnes COM-Objekt. Wenn der Profiler auf .NET Framework, Version 1.0 oder 1.1, COM, muss das Objekt nur die Methoden implementieren `ICorProfilerCallback`. Wenn sie .NET Framework, Version 2.0 oder höher abzielt, muss das COM-Objekt auch die Methoden der implementieren `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [ICorProfilerCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
