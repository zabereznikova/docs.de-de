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
ms.openlocfilehash: bb3e382a93f28ea99c66268e6e402ea275961047
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43798832"
---
# <a name="corprofeunsupportedcallsequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
Die CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT wurde in .NET Framework, Version 2.0 eingeführt. Die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] gibt dieses HRESULT in zwei Szenarien:  
  
-   Ein Profiler Hijacking Erzwingen eines Threads zurückgesetzt registrieren Sie Kontext zu einem beliebigen Zeitpunkt ein, sodass der Thread versucht, Strukturen, die sich in einem inkonsistenten Zustand befinden, Zugriff auf.  
  
-   Wenn ein Profiler mit dem versucht, die eine Informationsmethode aufrufen, die Garbagecollection von eine Rückrufmethode auslöst, die Garbagecollection verbietet.  
  
 Diese beiden Szenarien werden in den folgenden Abschnitten erläutert.  
  
## <a name="hijacking-profilers"></a>Hijacking-Profiler  
 (Dieses Szenario ist in erster Linie auf ein Problem mit Profiler hijacking, obwohl es gibt Fälle, in denen angriffslose Profiler dieses HRESULT sehen können.)  
  
 In diesem Szenario ein Profiler Hijacking erzwungen setzt Registerkontext des Threads zu einem beliebigen Zeitpunkt so, dass der Thread kann Profilercode eingeben, oder geben Sie erneut die common Language Runtime (CLR) über eine [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Methode.  
  
 Viele der, dass die profilerstellungs-API, zeigen Sie auf die Datenstrukturen in der CLR bietet-IDs. Viele `ICorProfilerInfo` Aufrufe lediglich Lesen von Informationen aus diesen Datenstrukturen, und geben sie zurück. Die CLR kann jedoch Elemente in diesen Strukturen ändern, wie er ausgeführt wird, und es Sperren zu diesem Zweck verwenden. Angenommen, die CLR wurde bereits enthält (oder Versuch zu erhalten) eine Sperre, die zum Zeitpunkt gehackt der Profiler den Thread an. Wenn der Thread wieder von der CLR wird und versucht, mehr Sperren, oder Überprüfen von Strukturen, die gerade geändert wurden, können diese Strukturen in einem inkonsistenten Zustand sein. Deadlocks und zugriffsverletzungen können problemlos in solchen Situationen auftreten.  
  
 Im Allgemeinen ein Profiler angriffslose Ausführung Code in eine [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) -Methode und ruft in einem `ICorProfilerInfo` Methode mit gültigen Parametern wäre nicht zu einem deadlock, oder Sie erhalten eine zugriffsverletzung. Z. B. ausgeführter Profilercode die [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) Methode kann durch Aufrufen von Informationen zu der Klasse Anfordern der [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) -Methode. Der Code wird möglicherweise ein HRESULT CORPROF_E_DATAINCOMPLETE, um anzugeben, dass Informationen nicht verfügbar ist; Es wird jedoch nicht zu einem deadlock oder erhalten eine zugriffsverletzung. Diese Klasse von Aufrufen an `ICorProfilerInfo` werden synchron, bezeichnet, da sie erfolgen eine `ICorProfilerCallback` Methode.  
  
 Allerdings einen verwalteten Thread, der Code ausführt, die nicht innerhalb einer `ICorProfilerCallback` Methode wird angenommen, dass einen asynchronen Aufruf ausführt. In .NET Framework, Version 1 war es schwierig zu bestimmen, was in einem asynchronen Aufruf passieren kann. Der Aufruf konnte zu einem deadlock, stürzt ab, oder eine ungültige Antwort erhalten. .NET Framework, Version 2.0 eingeführt, einige einfache Prüfungen aus, um dieses Problem zu vermeiden. In .NET Framework 2.0, wenn Sie eine unsichere Aufrufen `ICorProfilerInfo` asynchron funktionieren, schlägt Sie mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Asynchrone Aufrufe sind in der Regel nicht sicher. Allerdings werden die folgenden Methoden sind sicher und insbesondere asynchrone Aufrufe unterstützen:  
  
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
  
 Weitere Informationen finden Sie im Eintrag [warum wir CORPROF_E_UNSUPPORTED_CALL_SEQUENCE haben](https://go.microsoft.com/fwlink/?LinkId=169156) im CLR-Profilerstellungs-API-Blog.  
  
## <a name="triggering-garbage-collections"></a>Auslösen von Garbage Collections  
 Dieses Szenario umfasst einen Profiler, der in eine Callback-Methode ausgeführt wird (z. B. eine von der `ICorProfilerCallback` Methoden), die automatische speicherbereinigung verbietet. Wenn der Profiler versucht, die eine Informationsmethode aufrufen (z. B. eine Methode für die `ICorProfilerInfo` Schnittstelle), die möglicherweise eine Garbagecollection auslösen, die nur zu Informationszwecken-Methode, die mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT schlägt fehl.  
  
 In der folgende Tabelle zeigt die Rückrufmethoden, die Garbage Collection zu verbieten, und nur zu Informationszwecken Methoden, die Garbage Collection auslösen können. Wenn der Profiler wird innerhalb eines der aufgeführten Rückrufmethoden ausgeführt und eine der aufgeführten Methoden nur zu Informationszwecken Ruft, kann diese Methode nur zu Informationszwecken mit einem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Rückrufmethoden bereit, die Garbage Collections verbieten|Nur zu Informationszwecken Methoden, die Garbage Collection auslösen.|  
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
