---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: d6cba2ec3e82c07ce60f0f2b2199cc97e31a000b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555548"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT

Der CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT wurde in .NET Framework Version 2,0 eingeführt. .NET Framework 4 gibt dieses HRESULT in zwei Szenarien zurück:  
  
- Wenn ein Hijacking-Profiler erzwungen hat, dass der Registrierungs Kontext eines Threads zu einem beliebigen Zeitpunkt zurückgesetzt wird, damit der Thread versucht, auf Strukturen zuzugreifen, die in einem inkonsistenten Zustand sind.  
  
- Wenn ein Profiler versucht, eine informationsmethode aufzurufen, die Garbage Collection aus einer Rückruf Methode auslöst, die Garbage Collection verbietet.  
  
Diese beiden Szenarien werden in den folgenden Abschnitten erläutert.  
  
## <a name="hijacking-profilers"></a>Hijacking-Profiler  

  (Dieses Szenario stellt in erster Linie ein Problem mit dem Hijacking-Profiler dar, obwohl es Fälle gibt, in denen nicht-Hijacking-Profiler dieses HRESULT sehen können.)  
  
 In diesem Szenario setzt ein Hijacking-Profiler den Registrierungs Kontext eines Threads zu einem beliebigen Zeitpunkt zurück, damit der Thread Profiler-Code eingeben oder die Common Language Runtime (CLR) über eine [ICorProfilerInfo](icorprofilerinfo-interface.md) -Methode erneut eingeben kann.  
  
 Viele der IDs, die die Profilerstellungs-API bereitstellt, zeigen auf Datenstrukturen in der CLR. Viele `ICorProfilerInfo` Rufen lediglich Informationen aus diesen Datenstrukturen auf und übergeben Sie zurück. Die CLR ändert jedoch möglicherweise die Elemente in diesen Strukturen, während Sie ausgeführt wird, und verwendet ggf. sperren. Angenommen, die CLR war bereits in der Lage, eine Sperre zu dem Zeitpunkt, an dem der Profiler den Thread übernommen hat, zu speichern (oder zu erwerben) Wenn der Thread die CLR wieder eingibt und versucht, weitere Sperren zu übernehmen oder Strukturen zu überprüfen, die gerade geändert wurden, können sich diese Strukturen in einem inkonsistenten Zustand befinden. Deadlocks und Zugriffs Verletzungen können in solchen Situationen problemlos auftreten.  
  
 Im Allgemeinen gilt: Wenn ein nicht-Hijacking-Profiler Code innerhalb einer [ICorProfilerCallback](icorprofilercallback-interface.md) -Methode ausführt und eine- `ICorProfilerInfo` Methode mit gültigen Parametern aufruft, sollte er keinen Deadlock oder eine Zugriffsverletzung erhalten. Beispielsweise kann der Profiler-Code, der in der [ICorProfilerCallback:: classloadabgeschlossene](icorprofilercallback-classloadfinished-method.md) -Methode ausgeführt wird, Informationen über die Klasse durch Aufrufen der [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) -Methode anfordern. Der Code empfängt möglicherweise eine CORPROF_E_DATAINCOMPLETE HRESULT, um anzugeben, dass Informationen nicht verfügbar sind. Es wird jedoch kein Deadlock oder eine Zugriffsverletzung auftreten. Diese Aufrufe in `ICorProfilerInfo` werden als synchron angesehen, da Sie aus einer- `ICorProfilerCallback` Methode erstellt werden.  
  
 Ein verwalteter Thread, der Code ausführt, der nicht in einer Methode ausgeführt wird, `ICorProfilerCallback` wird jedoch als asynchroner Rückruf angesehen. In .NET Framework Version 1 war es schwierig, herauszufinden, was bei einem asynchronen-Befehl passieren könnte. Der Anruf könnte einen Deadlock, einen Absturz oder eine ungültige Antwort erhalten. In .NET Framework Version 2,0 wurden einige einfache Überprüfungen eingeführt, die Ihnen helfen, dieses Problem zu vermeiden. Wenn Sie in .NET Framework 2,0 eine unsichere `ICorProfilerInfo` Funktion asynchron aufzurufen, schlägt Sie mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT fehl.  
  
 Im Allgemeinen sind asynchrone Aufrufe nicht sicher. Die folgenden Methoden sind jedoch sicher und unterstützen asynchrone Aufrufe:  
  
- [GetEventMask](icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](icorprofilerinfo-getthreadcontext-method.md)  
  
- [GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)  
  
- [GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [IsArrayClass](icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Weitere Informationen finden Sie im Eintrag Grund für die [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) im Blog zur CLR-Profilerstellungs-API.  
  
## <a name="triggering-garbage-collections"></a>Auslösen von Garbage Collections  
 Dieses Szenario umfasst einen Profiler, der innerhalb einer Rückruf Methode (z. b. einer der- `ICorProfilerCallback` Methoden) ausgeführt wird, die Garbage Collection verbietet. Wenn der Profiler versucht, eine informationsmethode (z. b. eine Methode für die `ICorProfilerInfo` Schnittstelle) aufzurufen, die möglicherweise eine Garbage Collection auslöst, schlägt die informationsmethode mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT fehl.  
  
 In der folgenden Tabelle werden die Rückruf Methoden angezeigt, mit denen Garbage Collections untersagt werden, und Informationsmethoden, die möglicherweise Garbage Collections auslöst. Wenn der Profiler innerhalb einer der aufgelisteten Rückruf Methoden ausgeführt wird und eine der aufgelisteten Informationsmethoden aufruft, schlägt diese informationsmethode mit einer CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT fehl.  
  
|Rückruf Methoden zum verbieten von Garbage Collections|Informationsmethoden zum auslöst von Garbage Collections|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
- [ICorProfilerCallback3-Schnittstelle](icorprofilercallback3-interface.md)
- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
