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
ms.openlocfilehash: e05cb944ea4f3a9ca718dc22c6cd726b6a516ea9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866233"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted-Methode
Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion gestartet hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 in Die ID der Funktion, für die die Kompilierung gestartet wird.  
  
 `fIsSafeToBlock`  
 in Ein Wert, der angibt, ob die Blockierung den Lauf Zeitvorgang beeinträchtigt. Der Wert ist `true`, wenn eine Blockierung bewirkt, dass die Laufzeit darauf wartet, dass der aufrufenden Thread von diesem Rückruf zurückgegeben wird. Andernfalls `false`.  
  
 Obwohl der Wert `true` die Laufzeit nicht beeinträchtigt, kann er die Profil Erstellungs Ergebnisse verzerren.  
  
## <a name="remarks"></a>Hinweise  
 Es ist möglich, mehr als ein paar von `JITCompilationStarted` und [ICorProfilerCallback:: jitcompilationabgeschlossene](icorprofilercallback-jitcompilationfinished-method.md) Aufrufe für jede Funktion zu erhalten, da die Laufzeit Klassenkonstruktoren verarbeitet. Beispielsweise beginnt die Laufzeit mit der JIT-Kompilierungs Methode A, aber der Klassenkonstruktor für Klasse B muss ausgeführt werden. Daher kompiliert die Runtime JIT den Konstruktor für Klasse B und führt Sie aus. Während der Konstruktor ausgeführt wird, ruft er die Methode a auf, die bewirkt, dass die Methode a erneut JIT-kompiliert wird. In diesem Szenario wird die erste JIT-Kompilierung der Methode A angehalten. Beide Versuche der JIT-Kompilierungs Methode A werden jedoch mit JIT-Kompilierungs Ereignissen gemeldet. Wenn der Profiler Microsoft Intermediate Language (MSIL)-Code durch Aufrufen der [ICorProfilerInfo:: SetILFunctionBody-Methode durch Aufrufen der ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) -Methode ersetzen soll, `JITCompilationStarted` muss er den gleichen MSIL-Block für beide Ereignisse verwenden.  
  
 Profiler müssen die Sequenz der JIT-Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe erstellen. Thread A ruft z. b. `JITCompilationStarted`auf. Bevor Thread a jedoch `JITCompilationFinished`aufruft, ruft Thread B [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID aus dem `JITCompilationStarted` Rückruf von Thread a auf. Es kann vorkommen, dass die Funktions-ID noch nicht gültig ist, weil ein `JITCompilationFinished` noch nicht vom Profiler empfangen wurde. In einem solchen Fall ist die Funktions-ID jedoch gültig.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [JITCompilationFinished-Methode](icorprofilercallback-jitcompilationfinished-method.md)
