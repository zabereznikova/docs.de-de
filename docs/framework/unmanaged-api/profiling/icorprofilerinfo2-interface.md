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
ms.openlocfilehash: 3476a338191a4af9cc01b7e44456f1bd20f52a10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179009"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2-Schnittstelle
Enthält Methoden, mit denen Codeprofiler mit der common Language Runtime (CLR), um die ereignisüberwachung zu steuern und Informationen zu kommunizieren. Die `ICorProfilerInfo2` Schnittstelle ist eine Erweiterung von der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstelle. Das heißt, stellt es neue Methoden, die in der .NET Framework, Version 2.0 und höheren Versionen unterstützt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Führt den Stapel von den angegebenen Thread zum verwalteten Aufrufframes an den Profiler zu melden.|  
|[EnumModuleFrozenObjects-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Ruft einen Enumerator, der Iteration der fixierten Objekte im angegebenen Modul ermöglicht.|  
|[GetAppDomainStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Ruft die Adresse des angegebenen Anwendung Domäne statischen Felds, das im Bereich der angegebenen Anwendungsdomäne.|  
|[GetArrayObjectInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Ruft detaillierte Informationen zu einem Arrayobjekt.|  
|[GetBoxClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Ruft Informationen über das Klassenlayout für einen angegebenen Wert, der mittels Boxing konvertiert wird.|  
|[GetClassFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Ruft die `ClassID` eines Typs mit dem Token der angegebenen Metadaten und die `ClassID` Werte aller Typargumente.|  
|[GetClassIDInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Ruft das übergeordnete Modul des angegebenen generischen Klasse, das Metadatentoken für die Klasse, die `ClassID` der übergeordneten Klasse, und die `ClassID` für jedes Typargument, falls vorhanden, der-Klasse.|  
|[GetClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Ruft aus dem Arbeitsspeicher Informationen über das Layout der Felder ab, die durch die angegebene Klasse definiert sind . Das heißt, diese Methode ruft die Offsets der Felder der Klasse ab.|  
|[GetCodeInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Ruft die Wertebereiche von nativem Code ab, der der angegebenen `FunctionID` zugeordnet ist.|  
|[GetContextStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Ruft die Adresse des angegebenen Felds kontextstatische, die im Rahmen des angegebenen Kontexts.|  
|[GetFunctionFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Ruft die `FunctionID` einer Funktion mit dem angegebenen Metadaten-Token, mit der Klasse, und `ClassID` Werte aller Typargumente.|  
|[GetFunctionInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Ruft die übergeordnete Klasse, das Metadatentoken und die `ClassID` jedes Typarguments einer Funktion ab, falls vorhanden.|  
|[GetGenerationBounds-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Ruft ab, die Arbeitsspeicherbereiche (die Segmente des Heaps), die die dem Heap der Garbage Collection-Generationen bilden.|  
|[GetNotifiedExceptionClauseInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Ruft die systemeigenen und der Framezeiger Informationen für die Ausnahmeklausel ab (`catch`/`finally`/`filter`), wird gleich ausgeführt werden oder gerade ausgeführt wurde.|  
|[GetObjectGeneration-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Ruft ab, das Segment des Heaps, die das angegebene Objekt enthält.|  
|[GetRVAStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Ruft die Adresse die angegebene relative virtuelle Adresse (RVA) ab – statische Feld.|  
|[GetStaticFieldInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Ruft den Bereich, in dem das angegebene Feld statisch ist.|  
|[GetStringLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.|  
|[GetThreadAppDomain-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Ruft die ID der Anwendungsdomäne, in der Code derzeit von der angegebene Thread ausgeführt wird.|  
|[GetThreadStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Ruft die Adresse des angegebenen threadstatischen Felds, das in den Bereich des angegebenen Threads ist.|  
|[SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Gibt an, Profiler implementierten Funktionen in "eingeben", "verlassen" und "Tailcall" Hooks von verwalteten Funktionen aufgerufen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler Ruft eine Methode in der `ICorProfilerInfo2` Schnittstelle für die Kommunikation mit der CLR-ereignisüberwachung zu steuern und Informationen anfordern.  
  
 Die Methoden der `ICorProfilerInfo2` Schnittstelle werden von der CLR, die mit dem Freethread-Modell implementiert. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
 Die CLR übergibt eine `ICorProfilerInfo2` -Schnittstelle an jeden Codeprofiler während der Initialisierung wird mit der Profiler Implementierung des [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Ein Codeprofiler kann dann Methoden zum Aufrufen der `ICorProfilerInfo2` Schnittstelle zum Abrufen von Informationen zu verwaltetem Code unter der Kontrolle der CLR ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
