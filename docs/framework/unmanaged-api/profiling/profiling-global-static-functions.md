---
title: Profilerstellung für globale statische Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: d1d9b0a4c61ce7c3f8f9792046fb4bddf0fdfa05
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447431"
---
# <a name="profiling-global-static-functions"></a>Profilerstellung für globale statische Funktionen
In diesem Abschnitt werden die von der Profilerstellungs-API verwendeten nicht verwalteten API-Funktionen beschrieben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
## <a name="net-framework-version-1-profiling-functions"></a>Profil Erstellungs Funktionen der .NET Framework Version 1  
 [FunctionEnter-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird. Veraltet in .NET Framework 2,0.  
  
 [FunctionLeave-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren. Veraltet in .NET Framework 2,0.  
  
 [FunctionTailcall-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt. Veraltet in .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Profil Erstellungs Funktionen der .NET Framework Version 2  
 [FunctionIDMapper-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)-, [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)-und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) -Rückrufe für diese Funktion verwendet werden soll. Ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.  
  
 [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übermittelt wird, und stellt Informationen über den Stapel Rahmen und die Funktionsargumente bereit. In der .NET Framework 4 als veraltet markiert.  
  
 [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren, und stellt Informationen zum Stapel Rahmen und Funktionsrückgabewert bereit. In der .NET Framework 4 als veraltet markiert.  
  
 [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt und Informationen über den Stapel Rahmen bereitstellt. In der .NET Framework 4 als veraltet markiert.  
  
 [StackSnapshotCallback-Funktion](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Stellt dem Profiler Informationen über jeden verwalteten Frame und jede ausführen nicht verwalteter Frames auf dem Stapel während eines Stackwalk bereit, der von der [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) -Methode initiiert wird.  
  
## <a name="net-framework-version-4-profiling-functions"></a>Profil Erstellungs Funktionen der .NET Framework Version 4  
 [FunctionIDMapper2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)-, [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)-und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)-und[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) -Rückrufe für diese Funktion verwendet werden kann. Ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.  
  
 `FunctionIDMapper2` erweitert die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Funktion mit einem `clientData` Parameter, den Profiler verwenden können, um die Unterschiede Zwischenlauf Zeiten zu unterscheiden.  
  
 [FunctionEnter3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird.  
  
 [FunctionEnter3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) zum Abrufen des Stapel Rahmens und der Funktionsargumente übermittelt werden kann.  
  
 [FunctionLeave3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird.  
  
 [FunctionLeave3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) zum Abrufen des Stapel Rahmens und des Rückgabewerts übermittelt werden kann.  
  
 [FunctionTailcall3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt.  
  
 [FunctionTailcall3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Tail-Aufruf einer anderen Funktion ausführt, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen des Stapel Rahmens übermittelt werden kann.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Übersicht über die Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
