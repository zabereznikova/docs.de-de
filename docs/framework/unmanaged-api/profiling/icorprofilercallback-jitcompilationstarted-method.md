---
title: ICorProfilerCallback::JITCompilationStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12ae3e33d5553ed99a5a26b8fc872f0d07de81e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted-Methode
Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler zum Kompilieren einer funktionsrückgabewerts gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion für die die Kompilierung gestartet wird.  
  
 `fIsSafeToBlock`  
 [in] Ein Wert, der angibt, an den Profiler an, ob blockierende wird die Funktion der Laufzeit beeinflussen. Der Wert ist `true` Wenn blockiert die Common Language Runtime von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.  
  
 Obwohl ein Wert von `true` wird nicht auf die Common Language Runtime Schaden anrichten, sie können die Profilerstellungsergebnisse verzerren.  
  
## <a name="remarks"></a>Hinweise  
 Es ist möglich, mehr als ein Spaltenpaar empfangen `JITCompilationStarted` und [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) Ruft für jede Funktion aufgrund der Art und Weise die Laufzeit Klassenkonstruktoren Handles. Z. B. die Common Language Runtime beginnt JIT-kompiliert Methode A, aber den Konstruktor der Klasse für die Klasse B ausgeführt werden muss. Aus diesem Grund die Laufzeit-JIT-kompiliert der Konstruktor für die Klasse B und wird ausgeführt. Während der Konstruktor ausgeführt wird, wird einen Aufruf der Methode ein, wodurch ein JIT-kompilierte erneut werden-Methode wird vereinfacht. In diesem Szenario wird die erste JIT-Kompilierung der Methode A angehalten. Allerdings werden beide Versuche einer JIT-Kompilierung Methode A mit JIT-Kompilierung Ereignisse gemeldet. Wenn der Profiler mit der Microsoft intermediate Language (MSIL)-Code für die Methode A Ersetzen Sie durch Aufrufen der [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) -Methode, sie müssen dazu für beide `JITCompilationStarted` Ereignisse, aber sie können die gleichen MSIL-Block für beide.  
  
 Profiler müssen die Sequenz von JIT-Rückrufen in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen. Beispielsweise ruft Thread A `JITCompilationStarted`. Jedoch vor dem Thread A ruft `JITCompilationFinished`, Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit dem Funktions-ID von Thread A `JITCompilationStarted` Rückruf. Es scheint, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von `JITCompilationFinished` wurde noch nicht empfangen vom Profiler. In einem Fall wie diesem ist jedoch die Funktions-ID gültig.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [JITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
