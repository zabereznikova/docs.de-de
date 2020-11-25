---
title: ICorProfilerInfo3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3
helpviewer_keywords:
- ICorProfilerInfo3 interface [.NET Framework profiling]
ms.assetid: 044a262f-0fa7-485d-b0c1-64cdc359c654
topic_type:
- apiref
ms.openlocfilehash: 9944234da1677608aec10066b61bfc6a6cb72bcb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697856"
---
# <a name="icorprofilerinfo3-interface"></a>ICorProfilerInfo3-Schnittstelle

Stellt Methoden bereit, mit denen Codeprofiler mit der CLR (Common Language Runtime) kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern. Die- `ICorProfilerInfo3` Schnittstelle ist eine Erweiterung der [ICorProfilerInfo2](icorprofilerinfo2-interface.md) -Schnittstelle. Es stellt neue Methoden bereit, die in den .NET Framework 4 und höheren Versionen unterstützt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumJITedFunctions-Methode](icorprofilerinfo3-enumjitedfunctions-method.md)|Gibt einen Enumerator für alle zuvor mit JIT kompilierten Funktionen zurück.|  
|[EnumModules-Methode](icorprofilerinfo3-enummodules-method.md)|Gibt einen Enumerator zurück, der Methoden zum sequenziellen Iterieren durch eine Auflistung von verwalteten Modulen bereitstellt, die in die Anwendung geladen werden.|  
|[GetAppDomainsContainingModule-Methode](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Ruft die Bezeichner der Anwendungsdomänen ab, in denen das angegebene Modul geladen wurde.|  
|[GetFunctionEnter3Info-Methode](icorprofilerinfo3-getfunctionenter3info-method.md)|Stellt den Stapel Rahmen und die Argument Informationen der Funktion bereit, die dem Profiler von der [FunctionEnter3WithInfo](functionenter3withinfo-function.md) -Funktion gemeldet wird. kann nur während des- `FunctionEnter3WithInfo` Rückrufs aufgerufen werden.|  
|[GetFunctionLeave3Info-Methode](icorprofilerinfo3-getfunctionleave3info-method.md)|Stellt den Stapel Rahmen und den Rückgabewert der Funktion bereit, die dem Profiler von der Funktion der [FunctionLeave3WithInfo-Funktion](functionleave3withinfo-function.md) gemeldet wird. kann nur während des- `FunctionLeave3WithInfo` Rückrufs aufgerufen werden.|  
|[GetFunctionTailcall3Info-Methode](icorprofilerinfo3-getfunctiontailcall3info-method.md)|Stellt den Stapel Rahmen der Funktion bereit, die dem Profiler von der [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Funktion gemeldet wird. kann nur während des- `FunctionTailcall3WithInfo` Rückrufs aufgerufen werden.|  
|[GetModuleInfo2-Methode](icorprofilerinfo3-getmoduleinfo2-method.md)|Gibt bei Angabe einer Modul-ID den Dateinamen des Moduls, die ID der übergeordneten Assembly des Moduls und eine Bitmaske zurück, die die Eigenschaften des Moduls beschreibt.|  
|[GetRuntimeInformation-Methode](icorprofilerinfo3-getruntimeinformation-method.md)|Stellt die Versionsinformationen zum Laufzeitmodul bereit, für das ein Profil erstellt wird.|  
|[GetStringLayout2-Methode](icorprofilerinfo3-getstringlayout2-method.md)|Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.|  
|[GetThreadStaticAddress2-Methode](icorprofilerinfo3-getthreadstaticaddress2-method.md)|Ruft die Adresse des angegebenen threadstatischen Felds im Bereich des angegebenen Threads und der Anwendungsdomäne ab.|  
|[RequestProfilerDetach-Methode](icorprofilerinfo3-requestprofilerdetach-method.md)|Weist das Laufzeitmodul an, den Profiler zu trennen.|  
|[SetEnterLeaveFunctionHooks3-Methode](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Gibt die vom Profiler implementierten Funktionen an, die für die Funktionen [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)und [FunctionTailcall3](functiontailcall3-function.md) aufgerufen werden.|  
|[SetEnterLeaveFunctionHooks3WithInfo-Methode](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Gibt die vom Profiler implementierten Funktionen an, die für die [FunctionEnter3WithInfo](functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Hooks von verwalteten Funktionen aufgerufen werden.|  
|[SetFunctionIDMapper2-Methode](icorprofilerinfo3-setfunctionidmapper2-method.md)|Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden. Diese Methode erweitert [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) mit einem Parameter, den Profiler verwenden können, um die Unterscheidung Zwischenlauf Zeiten zu unterscheiden.|  
  
## <a name="remarks"></a>Hinweise  

 Die CLR implementiert die Methoden der `ICorProfilerInfo3`-Schnittstelle mithilfe des Freethreadmodells. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
 Die CLR übergibt `ICorProfilerInfo3` während der Initialisierung eine Schnittstelle an jeden Codeprofiler, wobei die Profiler-Implementierung der [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Methode oder der [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) -Methode verwendet wird. Ein Codeprofiler kann dann die `ICorProfilerInfo3`-Methoden aufrufen, um Informationen zu verwaltetem Code abzurufen, der unter der Kontrolle der CLR ausgeführt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
