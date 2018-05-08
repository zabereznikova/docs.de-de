---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6cce181037ee4f4db3a828f98cc3e07dfb45aff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corprofeunsupportedcallsequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
Die CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT wurde in .NET Framework, Version 2.0 eingeführt. Die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] gibt dieses HRESULT in zwei Szenarien:  
  
-   Ein Profiler Hijacking zwangsweise eines Threads zurückgesetzt registrieren Sie Kontext zu einem beliebigen Zeitpunkt so, dass der Thread versucht, die Strukturen zugreifen, die sich in einem inkonsistenten Status befinden.  
  
-   Wenn ein Profiler versucht, eine Informationsmethode aufrufen, die Garbagecollection von eine Rückrufmethode auslöst, die Garbagecollection verbietet.  
  
 In den folgenden Abschnitten werden diese beiden Szenarien erläutert.  
  
## <a name="hijacking-profilers"></a>Hijacking-Profiler  
 (Dieses Szenario ist in erster Linie auf ein Problem mit der Profiler hijacking, obwohl es gibt Fälle, in dem nicht-Hijacking Profiler dieses HRESULT sehen können.)  
  
 In diesem Szenario ein Profiler Hijacking erzwungen setzt Registerkontext einen Thread zu einem beliebigen Zeitpunkt, damit der Thread Profilercode eingeben, oder geben die common Language Runtime (CLR) kann über eine [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Methode.  
  
 Viele der IDs, dass die profilerstellungs-API, zeigen Sie auf die Datenstrukturen in der CLR zur Verfügung. Viele `ICorProfilerInfo` Aufrufe lediglich Lesen von Informationen aus diesen Datenstrukturen und zurück zu übergeben. Die CLR kann jedoch Elemente in diesen Strukturen ändern, wie er ausgeführt wird, und es möglicherweise Sperren zu diesem Zweck. Angenommen, die CLR wurde bereits halten (oder erwerben möchten) eine Sperre, die zum Zeitpunkt übernommen der Profiler den Thread an. Wenn der Thread die CLR erneut eingegeben und versucht, mehr Sperren oder Überprüfen von Strukturen, die gerade geändert wurden, können diese Strukturen in einem inkonsistenten Zustand sein. Deadlocks und zugriffsverletzungen können problemlos in solchen Situationen auftreten.  
  
 Im Allgemeinen bei ein nicht-Hijacking Profiler führt Code innerhalb einer [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) -Methode und Aufrufe an eine `ICorProfilerInfo` Methode mit gültigen Parametern es nicht zu einem deadlock oder eine zugriffsverletzung. Z. B. ausgeführter Profilercode die [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) Methode möglicherweise Fragen Sie nach Informationen zur Klasse durch Aufrufen der [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) Methode. Der Code wird möglicherweise ein CORPROF_E_DATAINCOMPLETE HRESULT, um anzugeben, dass Informationen nicht verfügbar ist; Es wird jedoch nicht zu einem deadlock oder eine zugriffsverletzung. Diese Klasse von Aufrufen in `ICorProfilerInfo` werden synchron bezeichnet, da sie erfolgen eine `ICorProfilerCallback` Methode.  
  
 Allerdings einen verwalteten Thread, der Code ausführt, die nicht innerhalb einer `ICorProfilerCallback` Methode betrachtet wird, um einen asynchronen Aufruf ausführt. In .NET Framework, Version 1 wurde es möglicherweise schwierig festzustellen, was in einem asynchronen Aufruf passieren kann. Der Aufruf konnte zu einem deadlock, stürzt ab, oder eine ungültige Antwort erhalten. .NET Framework, Version 2.0 eingeführten einige einfache Überprüfungen aus, um dieses Problem zu vermeiden. In .NET Framework 2.0, wenn Sie eine unsichere Aufruf `ICorProfilerInfo` -Funktion asynchron, schlägt Sie mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Asynchrone Aufrufe sind im Allgemeinen nicht sicher. Allerdings wird die folgenden Methoden sicher sind, und insbesondere asynchrone Aufrufe unterstützen:  
  
-   [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
-   [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
-   [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
-   [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
-   [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
-   [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
-   [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
-   [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
-   [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
-   [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
-   [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
-   [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
-   [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
-   [IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
-   [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
-   [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Weitere Informationen finden Sie im Eintrag [wir CORPROF_E_UNSUPPORTED_CALL_SEQUENCE haben](http://go.microsoft.com/fwlink/?LinkId=169156) im CLR Profiling-API-Blog.  
  
## <a name="triggering-garbage-collections"></a>Auslösen von Garbage Collections  
 Dieses Szenario umfasst einen Profiler, die innerhalb einer Rückrufmethode ausgeführt wird (z. B. eine von der `ICorProfilerCallback` Methoden), die Garbagecollection verbietet. Wenn der Profiler versucht, eine Informationsmethode aufrufen (z. B. eine Methode für die `ICorProfilerInfo` Schnittstelle), die möglicherweise eine Garbagecollection auslösen, schlägt die Informationsmethode mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Die folgende Tabelle enthält die Rückrufmethoden, die Ausführung von Garbage Collections sind nicht zulässig, und nur zu Informationszwecken Methoden, die Garbage Collection auslösen können. Wenn der Profiler innerhalb eines der aufgelisteten Rückrufmethoden ausführt und eine der aufgelisteten nur zu Informationszwecken Methoden aufruft, schlägt diese Informationsmethode mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Rückrufmethoden, die Ausführung von Garbage Collections sind nicht zulässig|Nur zu Informationszwecken Methoden, durch die Garbage Collection ausgelöst|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [ICorProfilerCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
