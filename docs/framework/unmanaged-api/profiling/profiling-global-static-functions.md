---
title: Profilerstellung für globale statische Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 1b0ad42e6b34e99212e112f6a594b0a36b6715e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723076"
---
# <a name="profiling-global-static-functions"></a>Profilerstellung für globale statische Funktionen

In diesem Abschnitt werden die von der Profilerstellungs-API verwendeten nicht verwalteten API-Funktionen beschrieben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
## <a name="net-framework-version-1-profiling-functions"></a>Profil Erstellungs Funktionen der .NET Framework Version 1  

 [FunctionEnter-Funktion](functionenter-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird. Veraltet in .NET Framework 2,0.  
  
 [FunctionLeave-Funktion](functionleave-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren. Veraltet in .NET Framework 2,0.  
  
 [FunctionTailcall-Funktion](functiontailcall-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt. Veraltet in .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Profil Erstellungs Funktionen der .NET Framework Version 2  

 [FunctionIDMapper-Funktion](functionidmapper-function.md)  
 Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter2](functionenter2-function.md)-, [FunctionLeave2](functionleave2-function.md)-und [FunctionTailcall2](functiontailcall2-function.md) -Rückrufe für diese Funktion verwendet werden soll. Ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.  
  
 [FunctionEnter2-Funktion](functionenter2-function.md)  
 Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übermittelt wird, und stellt Informationen über den Stapel Rahmen und die Funktionsargumente bereit. In der .NET Framework 4 als veraltet markiert.  
  
 [FunctionLeave2-Funktion](functionleave2-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren, und stellt Informationen zum Stapel Rahmen und Funktionsrückgabewert bereit. In der .NET Framework 4 als veraltet markiert.  
  
 [FunctionTailcall2-Funktion](functiontailcall2-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt und Informationen über den Stapel Rahmen bereitstellt. In der .NET Framework 4 als veraltet markiert.  
  
 [StackSnapshotCallback-Funktion](stacksnapshotcallback-function.md)  
 Stellt dem Profiler Informationen über jeden verwalteten Frame und jede ausführen nicht verwalteter Frames auf dem Stapel während eines Stackwalk bereit, der von der [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode initiiert wird.  
  
## <a name="net-framework-version-4-profiling-functions"></a>Profil Erstellungs Funktionen der .NET Framework Version 4  

 [FunctionIDMapper2-Funktion](functionidmapper2-function.md)  
 Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter3](functionenter3-function.md)-, [FunctionLeave3](functionleave3-function.md)-und [FunctionTailcall3](functiontailcall3-function.md)-und[FunctionEnter3WithInfo](functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Rückrufe für diese Funktion verwendet werden kann. Ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.  
  
 `FunctionIDMapper2` erweitert die [FunctionIDMapper](functionidmapper-function.md) -Funktion mit einem `clientData` Parameter, den Profiler verwenden können, um die Unterschiede Zwischenlauf Zeiten zu unterscheiden.  
  
 [FunctionEnter3-Funktion](functionenter3-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird.  
  
 [FunctionEnter3WithInfo-Funktion](functionenter3withinfo-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) zum Abrufen des Stapel Rahmens und der Funktionsargumente übermittelt werden kann.  
  
 [FunctionLeave3-Funktion](functionleave3-function.md)  
 Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird.  
  
 [FunctionLeave3WithInfo-Funktion](functionleave3withinfo-function.md)  
 Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) zum Abrufen des Stapel Rahmens und des Rückgabewerts übermittelt werden kann.  
  
 [FunctionTailcall3-Funktion](functiontailcall3-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt.  
  
 [FunctionTailcall3WithInfo-Funktion](functiontailcall3withinfo-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Tail-Aufruf einer anderen Funktion ausführt, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen des Stapel Rahmens übermittelt werden kann.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Übersicht über die Profilerstellung](profiling-overview.md)  
  
 [Profilerstellungsschnittstellen](profiling-interfaces.md)  
  
 [Profilerstellungsenumerationen](profiling-enumerations.md)  
  
 [Profilerstellungsstrukturen](profiling-structures.md)
