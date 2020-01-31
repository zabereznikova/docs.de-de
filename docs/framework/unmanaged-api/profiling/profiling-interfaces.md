---
title: Profilerstellungsschnittstellen
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: 8b6b9acff2945e2d8fd684bfa31e4af086ea5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868147"
---
# <a name="profiling-interfaces"></a>Profilerstellungsschnittstellen
In diesem Abschnitt werden die nicht verwalteten Schnittstellen beschrieben, die die Profilerstellung eines Programms ermöglichen, das von der Common Language Runtime (CLR) ausgeführt wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ICLRProfiling-Schnittstelle](iclrprofiling-interface.md)  
 Stellt die [attachprofiler](iclrprofiling-attachprofiler-method.md) -Methode bereit, die einem Profiler das Anfügen an einen laufenden Prozess ermöglicht.  
  
 [ICorProfilerAssemblyReferenceProvider-Schnittstelle](icorprofilerassemblyreferenceprovider-interface.md)  
 Ermöglicht es dem Profiler, die CLR der Assemblyverweise zu informieren, die der Profiler im [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzufügt.  
  
 [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)  
 Stellt Methoden bereit, mit denen die CLR einen Codeprofiler benachrichtigt, wenn die abonnierten Ereignisse des Profilers auftreten.  
  
 [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)  
 Erweitert die `ICorProfilerCallback`-Schnittstelle um Rückrufe, die in .NET Framework 2.0 und höheren Versionen unterstützt werden.  
  
 [ICorProfilerCallback3-Schnittstelle](icorprofilercallback3-interface.md)  
 Stellt Rückrufmethoden bereit, die von der CLR verwendet werden, um an den Profiler Informationen zum Anfüge- und Trennzustand zu übermitteln.  
  
 [ICorProfilerCallback4-Schnittstelle](icorprofilercallback4-interface.md)  
 Stellt Rückrufmethoden bereit, die von der CLR verwendet werden, um an den Profiler Informationen zu übermitteln.  
  
 [ICorProfilerCallback5-Schnittstelle](icorprofilercallback5-interface.md)  
 Stellt eine Methode bereit, die den transitiven Abschluss von Objekten identifiziert, auf die durch den Garbage Collection-Stamm verwiesen wird.  
  
 [ICorProfilerCallback6-Schnittstelle](icorprofilercallback6-interface.md)  
 Stellt eine Rückrufmethode bereit, die von der CLR genutzt wird, um einen Profiler zu benachrichtigen, dass eine Assembly geladen wird.  
  
 [CorProfilerCallback7-Schnittstelle](icorprofilercallback7-interface.md)  
 Stellt eine Rückruf Methode bereit, die der-Common Language Runtime verwendet, um den Profiler zu benachrichtigen, dass der mit einem in-Memory-Modul verknüpfte Symbol Datenstrom aktualisiert wird.  

[ICorProfilerCallback8-Schnittstelle](icorprofilercallback8-interface.md)  
Stellt Rückruf Methoden bereit, die von der Common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass die JIT-Kompilierung einer dynamischen Methode gestartet und beendet wurde.

[ICorProfilerCallback9-Schnittstelle](icorprofilercallback9-interface.md)  
Stellt eine Rückruf Methode bereit, die der Common Language Runtime verwendet, um den Profiler zu benachrichtigen, dass eine dynamische Methode in eine Garbage Collection und anschließend entladen wird.

 [ICorProfilerFunctionControl-Schnittstelle](icorprofilerfunctioncontrol-interface.md)  
 Stellt Methoden bereit, die einem Codeprofiler ermöglichen, mit der CLR zu kommunizieren, um zu steuern, wie der JIT-Compiler Code generieren soll, wenn er eine bestimmte Methode neu kompiliert.  
  
 [ICorProfilerFunctionEnum-Schnittstelle](icorprofilerfunctionenum-interface.md)  
 Stellt Methoden bereit, um eine Auflistung von Funktionen in der CLR sequenziell zu durchlaufen.  
  
 [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)  
 Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern.  
  
 [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)  
 Erweitert die `ICorProfilerInfo`-Schnittstelle um Methoden, die in .NET Framework 2.0 und höheren Versionen unterstützt werden.  
  
 [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)  
 Erweitert die `ICorProfilerInfo2`-Schnittstelle um Methoden, die in der .NET Framework 4 und höheren Versionen unterstützt werden.  
  
 [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)  
 Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern.  
  
 [ICorProfilerInfo5-Schnittstelle](icorprofilerinfo5-interface.md)  
 Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern.  
  
 [ICorProfilerInfo6-Schnittstelle](icorprofilerinfo6-interface.md)  
 Stellt einen Enumerator für alle Methoden bereit, die zu einem angegebenen ngen-Modul gehören und im Text einer angegebenen Methode Inline sind.  
  
 [ICorProfilerInfo7-Schnittstelle](icorprofilerinfo7-interface.md)  
 Stellt eine Methode bereit, um neu definierte Metadaten auf ein Modul anzuwenden, das Zugriff auf einen in-Memory-symbolstream bereitstellt.  
  
 [ICorProfilerModuleEnum-Schnittstelle](icorprofilermoduleenum-interface.md)  
 Stellt Methoden bereit, um eine Auflistung von Modulen, die von der Anwendung oder dem Profiler geladen wurden, sequenziell zu durchlaufen.  
  
 [ICorProfilerObjectEnum-Schnittstelle](icorprofilerobjectenum-interface.md)  
 Stellt Methoden bereit, um eine Auflistung von fixierten Objekten sequenziell zu durchlaufen, die von [Ngen. exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)generiert werden.  
  
 [ICorProfilerThreadEnum-Schnittstelle](icorprofilerthreadenum-interface.md)  
 Stellt Methoden bereit, um eine Auflistung von Threads in der CLR sequenziell zu durchlaufen.  
  
 [IMethodMalloc-Schnittstelle](imethodmalloc-interface.md)  
 Stellt die [Alloc](imethodmalloc-alloc-method.md) -Methode bereit, um Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) zuzuweisen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Übersicht über die Profilerstellung](profiling-overview.md)  
  
 [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)  
  
 [Profilerstellungsenumerationen](profiling-enumerations.md)  
  
 [Profilerstellungsstrukturen](profiling-structures.md)
