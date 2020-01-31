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
ms.openlocfilehash: 23fd44a6865b0487296f3ade37c1219e8feba288
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862580"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2-Schnittstelle
Stellt Methoden bereit, die Code Profiler für die Kommunikation mit dem Common Language Runtime (CLR) verwenden, um die Ereignisüberwachung und Anforderungs Informationen zu steuern. Die `ICorProfilerInfo2`-Schnittstelle ist eine Erweiterung der [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstelle. Das heißt, es werden neue Methoden bereitstellt, die in der .NET Framework Version 2,0 und höheren Versionen unterstützt werden.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[DoStackSnapshot-Methode](icorprofilerinfo2-dostacksnapshot-method.md)|Führt den Stapel des angegebenen Threads aus, um verwaltete Aufrufframes an den Profiler zu melden.|  
|[EnumModuleFrozenObjects-Methode](icorprofilerinfo2-enummodulefrozenobjects-method.md)|Ruft einen Enumerator ab, der die iterierung der fixierten Objekte im angegebenen Modul zulässt.|  
|[GetAppDomainStaticAddress-Methode](icorprofilerinfo2-getappdomainstaticaddress-method.md)|Ruft die Adresse des angegebenen Anwendungs Domänen statischen Felds ab, das sich im Gültigkeitsbereich der angegebenen Anwendungsdomäne befindet.|  
|[GetArrayObjectInfo-Methode](icorprofilerinfo2-getarrayobjectinfo-method.md)|Ruft ausführliche Informationen zu einem Array Objekt ab.|  
|[GetBoxClassLayout-Methode](icorprofilerinfo2-getboxclasslayout-method.md)|Ruft Informationen über das Klassen Layout für einen angegebenen Werttyp ab, der gekapselt wird.|  
|[GetClassFromTokenAndTypeArgs-Methode](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Ruft den `ClassID` eines Typs unter Verwendung des angegebenen Metadatentokens und der `ClassID` Werte beliebiger Typargumente ab.|  
|[GetClassIDInfo2-Methode](icorprofilerinfo2-getclassidinfo2-method.md)|Ruft das übergeordnete Modul der angegebenen generischen Klasse, das Metadatentoken für die Klasse, den `ClassID` der übergeordneten Klasse und die `ClassID` für jedes Typargument (sofern vorhanden) der Klasse ab.|  
|[GetClassLayout-Methode](icorprofilerinfo2-getclasslayout-method.md)|Ruft aus dem Arbeitsspeicher Informationen über das Layout der Felder ab, die durch die angegebene Klasse definiert sind . Das heißt, diese Methode ruft die Offsets der Felder der Klasse ab.|  
|[GetCodeInfo2-Methode](icorprofilerinfo2-getcodeinfo2-method.md)|Ruft die Wertebereiche von nativem Code ab, der der angegebenen `FunctionID` zugeordnet ist.|  
|[GetContextStaticAddress-Methode](icorprofilerinfo2-getcontextstaticaddress-method.md)|Ruft die Adresse des angegebenen Kontext statischen Felds ab, das sich im Gültigkeitsbereich des angegebenen Kontexts befindet.|  
|[GetFunctionFromTokenAndTypeArgs-Methode](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Ruft den `FunctionID` einer Funktion mit dem angegebenen Metadatentoken, der enthaltenden Klasse und `ClassID` Werten beliebiger Typargumente ab.|  
|[GetFunctionInfo2-Methode](icorprofilerinfo2-getfunctioninfo2-method.md)|Ruft die übergeordnete Klasse, das Metadatentoken und die `ClassID` jedes Typarguments einer Funktion ab, falls vorhanden.|  
|[GetGenerationBounds-Methode](icorprofilerinfo2-getgenerationbounds-method.md)|Ruft die Speicherbereiche (die Segmente des Heaps) ab, die die Generationen des Heap der Garbage Collection bilden.|  
|[GetNotifiedExceptionClauseInfo-Methode](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Ruft die nativen Adress-und Frame Informationen für die Ausnahmeklausel (`catch`/`finally`/`filter`) ab, die gerade ausgeführt oder gerade ausgeführt wird.|  
|[GetObjectGeneration-Methode](icorprofilerinfo2-getobjectgeneration-method.md)|Ruft das Segment des Heaps ab, das das angegebene-Objekt enthält.|  
|[GetRVAStaticAddress-Methode](icorprofilerinfo2-getrvastaticaddress-method.md)|Ruft die Adresse des angegebenen RVA (Relative Virtual Address)-statischen Felds ab.|  
|[GetStaticFieldInfo-Methode](icorprofilerinfo2-getstaticfieldinfo-method.md)|Ruft den Bereich ab, in dem das angegebene Feld statisch ist.|  
|[GetStringLayout-Methode](icorprofilerinfo2-getstringlayout-method.md)|Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.|  
|[GetThreadAppDomain-Methode](icorprofilerinfo2-getthreadappdomain-method.md)|Ruft die ID der Anwendungsdomäne ab, in der der angegebene Thread aktuell Code ausführt.|  
|[GetThreadStaticAddress-Methode](icorprofilerinfo2-getthreadstaticaddress-method.md)|Ruft die Adresse des angegebenen Thread statischen Felds ab, das sich im Gültigkeitsbereich des angegebenen Threads befindet.|  
|[SetEnterLeaveFunctionHooks2-Methode](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Gibt vom Profiler implementierte Funktionen an, die für die "Enter"-, "Leave"-und "Tailcall"-Hooks von verwalteten Funktionen aufgerufen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler Ruft eine Methode in der `ICorProfilerInfo2`-Schnittstelle auf, um mit der CLR zu kommunizieren, um die Ereignisüberwachung und Anforderungs Informationen zu steuern.  
  
 Die Methoden der `ICorProfilerInfo2`-Schnittstelle werden von der CLR mithilfe des frei Hand Thread Modells implementiert. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
 Die CLR übergibt während der Initialisierung mithilfe der Implementierung von [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)des Profilers eine `ICorProfilerInfo2`-Schnittstelle an jeden Codeprofiler. Ein Codeprofiler kann dann Methoden der `ICorProfilerInfo2`-Schnittstelle aufgerufen werden, um Informationen zu verwaltetem Code abzurufen, der unter der Steuerung der CLR ausgeführt wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
