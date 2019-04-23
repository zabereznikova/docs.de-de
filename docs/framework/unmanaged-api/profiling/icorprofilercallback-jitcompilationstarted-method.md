---
title: ICorProfilerCallback::JITCompilationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075320"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted-Methode
Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) gestartet wurde, mit der Kompilierung einer Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion für die die Kompilierung gestartet wird.  
  
 `fIsSafeToBlock`  
 [in] Ein Wert, der angibt, an den Profiler an, ob blockierende wirkt sich auf den Vorgang der Runtime. Der Wert ist `true` Wenn Blockierungen der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.  
  
 Obwohl ein Wert von `true` wird die Runtime nicht beschädigen, können sie die Ergebnisse der profilerstellung verzerren.  
  
## <a name="remarks"></a>Hinweise  
 Es ist möglich, erhalten mehr als ein Spaltenpaar `JITCompilationStarted` und [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) Ruft für jede Funktion aufgrund der Art und Weise die Laufzeit behandelt-Klasse, Konstruktoren. Z. B. die Laufzeit startet JIT-Kompilieren-Methode ein, aber der Klassenkonstruktor für Klasse B ausgeführt werden muss. Aus diesem Grund die Laufzeit-JIT-kompiliert wird der Konstruktor für die Klasse B und wird ausgeführt. Während der Konstruktor ausgeführt wird, ist es einen Aufruf der Methode A, die Methode ein JIT-kompilierten erneut werden kann. In diesem Szenario wird die erste JIT-Kompilierung der Methode ein angehalten. Allerdings werden beide versucht, ein JIT-Kompilieren-Methode mit JIT-Kompilierung Ereignisse gemeldet. Wenn der Profiler Microsoft intermediate Language (MSIL)-Code für die Methode A durch den Aufruf zu ersetzen ist die [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) -Methode, sie müssen dies für beide `JITCompilationStarted` Ereignisse, aber sie können den gleichen MSIL-Block für beides an.  
  
 Profiler müssen die Abfolge der JIT-Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen. Thread A ruft z. B. `JITCompilationStarted`. Jedoch vor dem Thread A ruft `JITCompilationFinished`, Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID von Thread A `JITCompilationStarted` Rückruf. Sie scheinen, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von `JITCompilationFinished` hatte noch nicht empfangen durch den Profiler. In einem Fall wie diesem ist jedoch die Funktions-ID gültig.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [JITCompilationFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
