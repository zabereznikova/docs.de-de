---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: 0cf3e05a0353a17541ee890f0871d694acac09fd
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116559"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT

Der CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT wurde in .NET Framework Version 2,0 eingeführt. .NET Framework 4 gibt dieses HRESULT in zwei Szenarien zurück:  
  
- Wenn ein Hijacking-Profiler erzwungen hat, dass der Registrierungs Kontext eines Threads zu einem beliebigen Zeitpunkt zurückgesetzt wird, damit der Thread versucht, auf Strukturen zuzugreifen, die in einem inkonsistenten Zustand sind.  
  
- Wenn ein Profiler versucht, eine informationsmethode aufzurufen, die Garbage Collection aus einer Rückruf Methode auslöst, die Garbage Collection verbietet.  
  
Diese beiden Szenarien werden in den folgenden Abschnitten erläutert.  
  
## <a name="hijacking-profilers"></a>Hijacking-Profiler  

  (Dieses Szenario stellt in erster Linie ein Problem mit dem Hijacking-Profiler dar, obwohl es Fälle gibt, in denen nicht-Hijacking-Profiler dieses HRESULT sehen können.)  
  
 In diesem Szenario setzt ein Hijacking-Profiler den Registrierungs Kontext eines Threads zu einem beliebigen Zeitpunkt zurück, damit der Thread Profiler-Code eingeben oder die Common Language Runtime (CLR) über eine [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) -Methode erneut eingeben kann.  
  
 Viele der IDs, die die Profilerstellungs-API bereitstellt, zeigen auf Datenstrukturen in der CLR. Viele `ICorProfilerInfo` rufen lediglich Informationen aus diesen Datenstrukturen auf und übergeben Sie zurück. Die CLR ändert jedoch möglicherweise die Elemente in diesen Strukturen, während Sie ausgeführt wird, und verwendet ggf. sperren. Angenommen, die CLR war bereits in der Lage, eine Sperre zu dem Zeitpunkt, an dem der Profiler den Thread übernommen hat, zu speichern (oder zu erwerben) Wenn der Thread die CLR wieder eingibt und versucht, weitere Sperren zu übernehmen oder Strukturen zu überprüfen, die gerade geändert wurden, können sich diese Strukturen in einem inkonsistenten Zustand befinden. Deadlocks und Zugriffs Verletzungen können in solchen Situationen problemlos auftreten.  
  
 Im Allgemeinen gilt: Wenn ein nicht-Hijacking-Profiler Code innerhalb einer [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) -Methode ausführt und eine `ICorProfilerInfo` Methode mit gültigen Parametern aufruft, sollte er keinen Deadlock oder eine Zugriffsverletzung erhalten. Beispielsweise kann der Profiler-Code, der in der [ICorProfilerCallback:: classloadabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) -Methode ausgeführt wird, Informationen über die Klasse durch Aufrufen der [ICorProfilerInfo2:: GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) -Methode anfordern. Der Code empfängt möglicherweise eine CORPROF_E_DATAINCOMPLETE HRESULT, um anzugeben, dass Informationen nicht verfügbar sind. Es wird jedoch kein Deadlock oder eine Zugriffsverletzung auftreten. Diese Aufrufe in `ICorProfilerInfo` gelten als synchron, da Sie über eine `ICorProfilerCallback` Methode erstellt werden.  
  
 Ein verwalteter Thread, der Code ausführt, der nicht in einer `ICorProfilerCallback` Methode ausgeführt wird, wird jedoch als asynchroner Rückruf angesehen. In .NET Framework Version 1 war es schwierig, herauszufinden, was bei einem asynchronen-Befehl passieren könnte. Der Anruf könnte einen Deadlock, einen Absturz oder eine ungültige Antwort erhalten. In .NET Framework Version 2,0 wurden einige einfache Überprüfungen eingeführt, die Ihnen helfen, dieses Problem zu vermeiden. Wenn Sie in .NET Framework 2,0 eine unsichere `ICorProfilerInfo` Funktion asynchron aufzurufen, schlägt Sie mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT fehl.  
  
 Im Allgemeinen sind asynchrone Aufrufe nicht sicher. Die folgenden Methoden sind jedoch sicher und unterstützen asynchrone Aufrufe:  
  
- [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
- [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
- [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Weitere Informationen finden Sie im Eintrag Grund für die [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) im Blog zur CLR-Profilerstellungs-API.  
  
## <a name="triggering-garbage-collections"></a>Auslösen von Garbage Collections  
 Dieses Szenario umfasst einen Profiler, der innerhalb einer Rückruf Methode ausgeführt wird (z. b. eine der `ICorProfilerCallback` Methoden), die Garbage Collection verbietet. Wenn der Profiler versucht, eine informationsmethode (z. b. eine Methode für die `ICorProfilerInfo`-Schnittstelle) aufzurufen, die möglicherweise eine Garbage Collection auslöst, schlägt die informationsmethode mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT fehl.  
  
 In der folgenden Tabelle werden die Rückruf Methoden angezeigt, mit denen Garbage Collections untersagt werden, und Informationsmethoden, die möglicherweise Garbage Collections auslöst. Wenn der Profiler innerhalb einer der aufgelisteten Rückruf Methoden ausgeführt wird und eine der aufgelisteten Informationsmethoden aufruft, schlägt diese informationsmethode mit einer CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT fehl.  
  
|Rückruf Methoden zum verbieten von Garbage Collections|Informationsmethoden zum auslöst von Garbage Collections|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
