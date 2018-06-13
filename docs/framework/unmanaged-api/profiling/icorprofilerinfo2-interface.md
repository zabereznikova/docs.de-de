---
title: ICorProfilerInfo2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2
helpviewer_keywords:
- ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8cec2a622a1a30881949ad5a9f2050077e195015
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461398"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2-Schnittstelle
Enthält Methoden, mit denen Codeprofiler mit der common Language Runtime (CLR), um die ereignisüberwachung zu steuern und Informationen zu kommunizieren. Die `ICorProfilerInfo2` Schnittstelle ist eine Erweiterung von der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstelle. D. h., bietet es neue Methoden, die in der .NET Framework Version 2.0 und höheren Versionen unterstützt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Führt den Stapel des angegebenen Threads Frames der verwaltete Aufruf an den Profiler zu melden.|  
|[EnumModuleFrozenObjects-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Gibt einen Enumerator zurück, der Iteration der fixierten Objekte im angegebenen Modul ermöglicht.|  
|[GetAppDomainStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Ruft die Adresse des Felds Domäne statische angegebenen Anwendung, die im Rahmen der angegebenen Anwendungsdomäne ab.|  
|[GetArrayObjectInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Ruft ausführliche Informationen zu einem Arrayobjekt.|  
|[GetBoxClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Ruft Informationen über das Klassenlayout für einen angegebenen Wert, der mittels Boxing konvertiert wird.|  
|[GetClassFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Ruft die `ClassID` eines Typs mit dem angegebenen Metadaten-Token und die `ClassID` Werte eines beliebigen Typargumente.|  
|[GetClassIDInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Ruft das übergeordnete Modul des angegebenen generischen Klasse, das Metadatentoken für die Klasse, die `ClassID` der übergeordneten Klasse und die `ClassID` für jedes Typargument, falls vorhanden, der-Klasse.|  
|[GetClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Ruft aus dem Arbeitsspeicher Informationen über das Layout der Felder ab, die durch die angegebene Klasse definiert sind . Das heißt, diese Methode ruft die Offsets der Felder der Klasse ab.|  
|[GetCodeInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Ruft die Wertebereiche von systemeigenem Code ab, der der angegebenen `FunctionID` zugeordnet ist.|  
|[GetContextStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Ruft die Adresse des angegebenen Felds in statischen Kontext, die im Bereich des angegebenen Kontexts ab.|  
|[GetFunctionFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Ruft die `FunctionID` einer Funktion mit dem angegebenen Metadaten-Token, mit der Klasse, und `ClassID` Werte eines beliebigen Typargumente.|  
|[GetFunctionInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Ruft die übergeordnete Klasse, das Metadatentoken und die `ClassID` jedes Typarguments einer Funktion ab, falls vorhanden.|  
|[GetGenerationBounds-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Ruft die Speicherbereiche (die Segmente des Heaps), die die dem Heap der Garbage Collection-Generationen bilden.|  
|[GetNotifiedExceptionClauseInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Der systemeigene Adresse und Rahmen für die Ausnahmeklausel abgerufen (`catch`/`finally`/`filter`), die auszuführende ist oder gerade ausgeführt wurde.|  
|[GetObjectGeneration-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Ruft das Segment des Heaps, die das angegebene Objekt enthält.|  
|[GetRVAStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Ruft die Adresse des angegebenen relativen virtuellen Adresse (RVA)-statischen Felds.|  
|[GetStaticFieldInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Ruft den Bereich, in dem das angegebene Feld statisch ist.|  
|[GetStringLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.|  
|[GetThreadAppDomain-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Ruft die ID der Anwendungsdomäne, in der der angegebene Thread gerade Code ausführt.|  
|[GetThreadStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Ruft die Adresse des angegebenen threadstatischen Felds, die im Bereich des angegebenen Threads ist.|  
|[SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Gibt Profiler implementierten Funktionen an, die für "eingeben", "Übernehmen" und "Tailcall" Hooks von verwalteten Funktionen aufgerufen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler Ruft eine Methode in der `ICorProfilerInfo2` Schnittstelle für die Kommunikation mit der CLR, die ereignisüberwachung zu steuern und Informationen anzufordern.  
  
 Die Methoden der `ICorProfilerInfo2` Schnittstelle werden von der CLR mithilfe des Freethread-Modells implementiert. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
 Die CLR übergibt eine `ICorProfilerInfo2` an jeden Codeprofiler während der Initialisierung des Profilers, der Implementierung der Schnittstelle [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Ein Codeprofiler kann dann Methoden von Aufrufen der `ICorProfilerInfo2` Schnittstelle zum Abrufen von Informationen über verwalteten Code unter der Kontrolle der CLR ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
