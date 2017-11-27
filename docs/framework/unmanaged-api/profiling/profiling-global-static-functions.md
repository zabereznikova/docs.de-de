---
title: "Profilerstellung für globale statische Funktionen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4da4509a6e8b87490cee076b403f3fa525de91e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-global-static-functions"></a>Profilerstellung für globale statische Funktionen
In diesem Abschnitt wird beschrieben, die nicht verwalteten API-Funktionen, die die profilerstellungs-API verwendet wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
## <a name="net-framework-version-1-profiling-functions"></a>Profilerstellung für .NET Framework Version 1-Funktionen  
 [FunctionEnter-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben wird. In .NET Framework 2.0 veraltet.  
  
 [FunctionLeave-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion an den Aufrufer zurückgegeben wird. In .NET Framework 2.0 veraltet.  
  
 [FunctionTailcall-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen. In .NET Framework 2.0 veraltet.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Profilerstellung für .NET Framework Version 2-Funktionen  
 [FunctionIDMapper-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückrufe für diese Funktion. Außerdem ermöglicht es dem Profiler, um anzugeben, ob er Rückrufe für diese Funktion empfangen will  
  
 [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben werden und Informationen über den Stapelrahmen und die Funktionsargumente bietet. Als veraltet markierte in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Benachrichtigt den Profiler, dass eine Funktion an den Aufrufer zurückgegeben wird, und Informationen über den Stapel und -Rückgabewert enthält. Als veraltet markierte in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen und enthält Informationen über den Stapelrahmen. Als veraltet markierte in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StackSnapshotCallback-Funktion](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Stellt Informationen über jeden verwalteten Frame und jeder Ausführung von nicht verwalteten Frames auf dem Stapel während ein Stackwalk, die von initiiert wird der Profiler die [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.  
  
## <a name="net-framework-version-4-profiling-functions"></a>Profilerstellung für .NET Framework Version 4-Funktionen  
 [FunctionIDMapper2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), oder[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Rückrufe für diese Funktion. Außerdem ermöglicht es dem Profiler, um anzugeben, ob er Rückrufe für diese Funktion empfangen will aus.  
  
 `FunctionIDMapper2`Erweitert die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Funktion mit einem `clientData` Parameter, den Profiler verwenden können, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.  
  
 [FunctionEnter3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben wird.  
  
 [FunctionEnter3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übergeben wird, und stellt ein Handle, das übergeben werden kann [ICorProfilerInfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) auf den Stapel und die Funktionsargumente abzurufen.  
  
 [FunctionLeave3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Benachrichtigt den Profiler, Steuerung von einer Funktion zurückgegeben wird.  
  
 [FunctionLeave3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Benachrichtigt den Profiler, Steuerung von einer Funktion zurückgegeben wird, und stellt ein Handle, das übergeben werden kann [ICorProfilerInfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) auf den Stapelrahmen und den Rückgabewert abzurufen.  
  
 [FunctionTailcall3-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen.  
  
 [FunctionTailcall3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Benachrichtigt den Profiler, die aktuell ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen, und stellt ein Handle, das übergeben werden kann [ICorProfilerInfo3:: Getfunctiontailcall3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen des Stapelrahmens.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Übersicht über die profilerstellung](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
