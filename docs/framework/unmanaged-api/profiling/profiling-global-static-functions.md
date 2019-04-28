---
title: Profilerstellung für globale statische Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bb5d93c91de857ebbee63009cad73fba7e1d284
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758248"
---
# <a name="profiling-global-static-functions"></a>Profilerstellung für globale statische Funktionen
In diesem Abschnitt wird beschrieben, die nicht verwalteten API-Funktionen, die die profilerstellungs-API verwendet wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
## <a name="net-framework-version-1-profiling-functions"></a>Profilerstellung für .NET Framework Version 1-Funktionen  
 [FunctionEnter-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird. In .NET Framework 2.0 veraltet.  
  
 [FunctionLeave-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion zum an den Aufrufer zurückgeben. In .NET Framework 2.0 veraltet.  
  
 [FunctionTailcall-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen. In .NET Framework 2.0 veraltet.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Profilerstellung für .NET Framework Version 2-Funktionen  
 [FunctionIDMapper-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Benachrichtigt Sie den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückrufe für diese Funktion. Außerdem ermöglicht es dem Profiler, um anzugeben, ob er Rückrufe für diese Funktion empfangen will.  
  
 [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Benachrichtigt den Profiler an, dass Steuerelement an eine Funktion übergeben wird und Informationen über den Stapelrahmen und die Funktionsargumente enthält. In als veraltet markiert die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion an den Aufrufer zurückgegeben wird, und Informationen über den Stapel Frame und Funktion-Rückgabewert enthält. In als veraltet markiert die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Benachrichtigt den Profiler an, die gerade ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen und enthält Informationen zu den Stapelrahmen. In als veraltet markiert die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StackSnapshotCallback-Funktion](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Stellt Informationen über jeden verwalteten Frame und die Ausführung von nicht verwalteten Frames im Stapel während eines Stackwalks, der von initiiert wird der Profiler die [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.  
  
## <a name="net-framework-version-4-profiling-functions"></a>Profilerstellung für .NET Framework Version 4-Funktionen  
 [FunctionIDMapper2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Benachrichtigt Sie den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), oder[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Rückrufe für diese Funktion. Außerdem ermöglicht es dem Profiler, um anzugeben, ob er Rückrufe für diese Funktion empfangen will ein.  
  
 `FunctionIDMapper2` Erweitert die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Funktion mit einem `clientData` -Parameter, der Profiler verwenden, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.  
  
 [FunctionEnter3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird.  
  
 [FunctionEnter3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben wird, und stellt ein Handle, das übergeben werden kann [ICorProfilerInfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) zum Abrufen der Stapel und die Funktionsargumente.  
  
 [FunctionLeave3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Benachrichtigt den Profiler, dass das Steuerelement aus einer Funktion zurückgegeben werden.  
  
 [FunctionLeave3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Benachrichtigt den Profiler, dass Steuerelement aus einer Funktion zurückgegeben werden, und stellt ein Handle, das übergeben werden kann [ICorProfilerInfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) den Stapelrahmen und den Rückgabewert abrufen.  
  
 [FunctionTailcall3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen.  
  
 [FunctionTailcall3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Benachrichtigt den Profiler, der aktuell ausgeführte Funktion einen Endeaufruf an eine andere Funktion auszuführen, und stellt ein Handle, das übergeben werden kann [ICorProfilerInfo3:: Getfunctiontailcall3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen des Stapelrahmens.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Übersicht über die Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
