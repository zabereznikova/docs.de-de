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
ms.openlocfilehash: fdac9eedb0ae442d6dd2646859cab13398020a87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449774"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2-Schnittstelle
Stellt Methoden bereit, die Code Profiler für die Kommunikation mit dem Common Language Runtime (CLR) verwenden, um die Ereignisüberwachung und Anforderungs Informationen zu steuern. Die `ICorProfilerInfo2`-Schnittstelle ist eine Erweiterung der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) -Schnittstelle. Das heißt, es werden neue Methoden bereitstellt, die in der .NET Framework Version 2,0 und höheren Versionen unterstützt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Führt den Stapel des angegebenen Threads aus, um verwaltete Aufrufframes an den Profiler zu melden.|  
|[EnumModuleFrozenObjects-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Ruft einen Enumerator ab, der die iterierung der fixierten Objekte im angegebenen Modul zulässt.|  
|[GetAppDomainStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Ruft die Adresse des angegebenen Anwendungs Domänen statischen Felds ab, das sich im Gültigkeitsbereich der angegebenen Anwendungsdomäne befindet.|  
|[GetArrayObjectInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Ruft ausführliche Informationen zu einem Array Objekt ab.|  
|[GetBoxClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Ruft Informationen über das Klassen Layout für einen angegebenen Werttyp ab, der gekapselt wird.|  
|[GetClassFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Ruft den `ClassID` eines Typs unter Verwendung des angegebenen Metadatentokens und der `ClassID` Werte beliebiger Typargumente ab.|  
|[GetClassIDInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Ruft das übergeordnete Modul der angegebenen generischen Klasse, das Metadatentoken für die Klasse, den `ClassID` der übergeordneten Klasse und die `ClassID` für jedes Typargument (sofern vorhanden) der Klasse ab.|  
|[GetClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Ruft aus dem Arbeitsspeicher Informationen über das Layout der Felder ab, die durch die angegebene Klasse definiert sind . Das heißt, diese Methode ruft die Offsets der Felder der Klasse ab.|  
|[GetCodeInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Ruft die Wertebereiche von nativem Code ab, der der angegebenen `FunctionID` zugeordnet ist.|  
|[GetContextStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Ruft die Adresse des angegebenen Kontext statischen Felds ab, das sich im Gültigkeitsbereich des angegebenen Kontexts befindet.|  
|[GetFunctionFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Ruft den `FunctionID` einer Funktion mit dem angegebenen Metadatentoken, der enthaltenden Klasse und `ClassID` Werten beliebiger Typargumente ab.|  
|[GetFunctionInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Ruft die übergeordnete Klasse, das Metadatentoken und die `ClassID` jedes Typarguments einer Funktion ab, falls vorhanden.|  
|[GetGenerationBounds-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Ruft die Speicherbereiche (die Segmente des Heaps) ab, die die Generationen des Heap der Garbage Collection bilden.|  
|[GetNotifiedExceptionClauseInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Ruft die nativen Adress-und Frame Informationen für die Ausnahmeklausel (`catch`/`finally`/`filter`) ab, die gerade ausgeführt oder gerade ausgeführt wird.|  
|[GetObjectGeneration-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Ruft das Segment des Heaps ab, das das angegebene-Objekt enthält.|  
|[GetRVAStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Ruft die Adresse des angegebenen RVA (Relative Virtual Address)-statischen Felds ab.|  
|[GetStaticFieldInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Ruft den Bereich ab, in dem das angegebene Feld statisch ist.|  
|[GetStringLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.|  
|[GetThreadAppDomain-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Ruft die ID der Anwendungsdomäne ab, in der der angegebene Thread aktuell Code ausführt.|  
|[GetThreadStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Ruft die Adresse des angegebenen Thread statischen Felds ab, das sich im Gültigkeitsbereich des angegebenen Threads befindet.|  
|[SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Gibt vom Profiler implementierte Funktionen an, die für die "Enter"-, "Leave"-und "Tailcall"-Hooks von verwalteten Funktionen aufgerufen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler Ruft eine Methode in der `ICorProfilerInfo2`-Schnittstelle auf, um mit der CLR zu kommunizieren, um die Ereignisüberwachung und Anforderungs Informationen zu steuern.  
  
 Die Methoden der `ICorProfilerInfo2`-Schnittstelle werden von der CLR mithilfe des frei Hand Thread Modells implementiert. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
 Die CLR übergibt während der Initialisierung mithilfe der Implementierung von [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)des Profilers eine `ICorProfilerInfo2`-Schnittstelle an jeden Codeprofiler. Ein Codeprofiler kann dann Methoden der `ICorProfilerInfo2`-Schnittstelle aufgerufen werden, um Informationen zu verwaltetem Code abzurufen, der unter der Steuerung der CLR ausgeführt wird.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
