---
title: ICorProfilerInfo-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo
helpviewer_keywords:
- ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: eb4e4ce0-06e7-4469-bbc4-edc2eb5da4b1
topic_type:
- apiref
ms.openlocfilehash: b8cba2b1a1f206392a59f8bc9b968e725e0ce6ee
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869290"
---
# <a name="icorprofilerinfo-interface"></a>ICorProfilerInfo-Schnittstelle
Stellt Methoden bereit, mit denen Codeprofiler mit der Common Language Runtime (CLR) kommunizieren können, um die Ereignisüberwachung und Anforderungs Informationen zu steuern.  
  
> [!NOTE]
> Jede Methode in der `ICorProfilerInfo`-Schnittstelle gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie unter CorError. h.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[BeginInprocDebugging-Methode](icorprofilerinfo-begininprocdebugging-method.md)|Initialisiert die Prozess interne Debugunterstützung. Diese Methode ist in der .NET Framework Version 2,0 veraltet.|  
|[EndInprocDebugging-Methode](icorprofilerinfo-endinprocdebugging-method.md)|Beendet eine in-Process-Debuggingsitzung. Diese Methode ist in der .NET Framework Version 2,0 veraltet.|  
|[ForceGC-Methode](icorprofilerinfo-forcegc-method.md)|Erzwingt, dass Garbage Collection innerhalb der Laufzeit auftritt.|  
|[GetAppDomainInfo-Methode](icorprofilerinfo-getappdomaininfo-method.md)|Ruft Informationen über die angegebene Anwendungsdomäne ab.|  
|[GetAssemblyInfo-Methode](icorprofilerinfo-getassemblyinfo-method.md)|Ruft Informationen über die angegebene Assembly ab.|  
|[GetClassFromObject-Methode](icorprofilerinfo-getclassfromobject-method.md)|Ruft den `ClassID` einer ab.<br /><br /> Objekt, bei Angabe seines `ObjectID`.|  
|[GetClassFromToken-Methode](icorprofilerinfo-getclassfromtoken-method.md)|Ruft die ID der Klasse ab, wenn das Metadatentoken angegeben wird. Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen die [ICorProfilerInfo2:: getclassfromdekenandtypeargs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) -Methode.|  
|[GetClassIDInfo-Methode](icorprofilerinfo-getclassidinfo-method.md)|Ruft das übergeordnete Modul und das Metadatentoken für die angegebene Klasse ab.|  
|[GetCodeInfo-Methode](icorprofilerinfo-getcodeinfo-method.md)|Ruft den Wertebereich des nativen Codes ab, der der angegebenen Funktions-ID zugeordnet ist. Diese Methode ist veraltet. Verwenden Sie stattdessen die [ICorProfilerInfo2:: GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) -Methode.|  
|[GetCurrentThreadID-Methode](icorprofilerinfo-getcurrentthreadid-method.md)|Ruft die ID des aktuellen Threads ab, wenn es sich um einen verwalteten Thread handelt.|  
|[GetEventMask-Methode](icorprofilerinfo-geteventmask-method.md)|Ruft die aktuellen Ereignis Kategorien ab, für die der Profiler Ereignis Benachrichtigungen von der CLR empfangen möchte.|  
|[GetFunctionFromIP-Methode](icorprofilerinfo-getfunctionfromip-method.md)|Ordnet einen Anweisungs Zeiger für verwalteten Code einem `FunctionID`zu.|  
|[GetFunctionFromToken-Methode](icorprofilerinfo-getfunctionfromtoken-method.md)|Ruft die ID einer Funktion ab. Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen die [ICorProfilerInfo2:: getfunctionfromdekenandtypeargs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) -Methode.|  
|[GetFunctionInfo-Methode](icorprofilerinfo-getfunctioninfo-method.md)|Ruft die übergeordnete Klasse und das Metadatentoken für die angegebene Funktion ab.|  
|[GetHandleFromThread-Methode](icorprofilerinfo-gethandlefromthread-method.md)|Ordnet die ID eines Threads einem Win32-Thread Handle zu.|  
|[GetILFunctionBody-Methode](icorprofilerinfo-getilfunctionbody-method.md)|Ruft einen Zeiger auf den Text einer Methode im MSIL-Code (Microsoft Intermediate Language) ab, beginnend bei der Kopfzeile.|  
|[GetILFunctionBodyAllocator-Methode](icorprofilerinfo-getilfunctionbodyallocator-method.md)|Ruft eine-Schnittstelle ab, die eine Methode zum Zuordnen von Arbeitsspeicher bereitstellt, der zum Austauschen des Texts einer Methode im MSIL-Code verwendet werden soll.|  
|[GetILToNativeMapping-Methode](icorprofilerinfo-getiltonativemapping-method.md)|Ruft eine Zuordnung von MSIL-Offsets zu systemeigenen Offsets für den Code ab, der in der angegebenen Funktion enthalten ist.|  
|[GetInprocInspectionInterface-Methode](icorprofilerinfo-getinprocinspectioninterface-method.md)|Ruft ein Objekt ab, das für eine ICorDebugProcess-Schnittstelle abgefragt werden kann. Diese Methode ist in der .NET Framework Version 2,0 veraltet.|  
|[GetInprocInspectionIThisThread-Methode](icorprofilerinfo-getinprocinspectionithisthread-method.md)|Ruft ein Objekt ab, das für die ICorDebugThread-Schnittstelle abgefragt werden kann. Diese Methode ist in der .NET Framework Version 2,0 veraltet.|  
|[GetModuleInfo-Methode](icorprofilerinfo-getmoduleinfo-method.md)|Gibt für die übergebene Modul-ID den Dateinamen des Moduls und die ID der übergeordneten Assembly des Moduls zurück.|  
|[GetModuleMetaData-Methode](icorprofilerinfo-getmodulemetadata-method.md)|Ruft eine Instanz der Metadatenschnittstelle ab, die dem angegebenen Modul zugeordnet wird.|  
|[GetObjectSize-Methode](icorprofilerinfo-getobjectsize-method.md)|Ruft die Größe eines angegebenen-Objekts ab.|  
|[GetThreadContext-Methode](icorprofilerinfo-getthreadcontext-method.md)|Ruft die Kontext Identität ab, die dem angegebenen Thread zurzeit zugeordnet ist.|  
|[GetThreadInfo-Methode](icorprofilerinfo-getthreadinfo-method.md)|Ruft die aktuelle Win32-Thread Identität für den angegebenen Thread ab.|  
|[GetTokenAndMetadataFromFunction-Methode](icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Ruft das Metadatentoken und eine Instanz der Metadatenschnittstelle ab, die für das Token für die angegebene Funktion verwendet werden kann.|  
|[IsArrayClass-Methode](icorprofilerinfo-isarrayclass-method.md)|Bestimmt, ob die angegebene Klasse eine Array Klasse ist.|  
|[SetEnterLeaveFunctionHooks-Methode](icorprofilerinfo-setenterleavefunctionhooks-method.md)|Gibt vom Profiler implementierte Funktionen an, die für die "Enter"-, "Leave"-und "Tailcall"-Hooks von verwalteten Funktionen aufgerufen werden.|  
|[SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md)|Legt einen Wert fest, der die Ereignis Typen angibt, für die der Profiler Benachrichtigungen von der CLR empfangen möchte.|  
|[SetFunctionIDMapper-Methode](icorprofilerinfo-setfunctionidmapper-method.md)|Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden.|  
|[SetFunctionReJIT-Methode](icorprofilerinfo-setfunctionrejit-method.md)|Nicht implementiert. Nicht verwenden.|  
|[SetILFunctionBody-Methode](icorprofilerinfo-setilfunctionbody-method.md)|Ersetzt den Text der angegebenen Funktion im angegebenen Modul.|  
|[SetILInstrumentedCodeMap-Methode](icorprofilerinfo-setilinstrumentedcodemap-method.md)|Gibt an, wie die Offsets der ursprünglichen MSIL einer angegebenen Funktion den neuen Offsets der vom Profiler geänderten MSIL der Funktion zugeordnet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler Ruft eine Methode in der `ICorProfilerInfo`-Schnittstelle auf, um mit der CLR zu kommunizieren, um die Ereignisüberwachung und Anforderungs Informationen zu steuern.  
  
 Die Methoden der `ICorProfilerInfo`-Schnittstelle werden von der CLR mithilfe des frei Hand Thread Modells implementiert. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie unter CorError. h.  
  
 Die CLR übergibt mithilfe der Profiler-Implementierung von [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md), eine `ICorProfilerInfo`-Schnittstelle für jeden Codeprofiler während der Initialisierung. Ein Codeprofiler kann dann Methoden der `ICorProfilerInfo`-Schnittstelle aufgerufen werden, um Informationen zu verwaltetem Code abzurufen, der unter der Steuerung der CLR ausgeführt wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
