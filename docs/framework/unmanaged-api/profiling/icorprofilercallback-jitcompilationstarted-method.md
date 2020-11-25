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
ms.openlocfilehash: 7ce100a68a3e2b8963ed14bbf044fa9ba11d629f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725516"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted-Methode

Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion gestartet hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter  

 `functionId`  
 in Die ID der Funktion, für die die Kompilierung gestartet wird.  
  
 `fIsSafeToBlock`  
 in Ein Wert, der angibt, ob die Blockierung den Lauf Zeitvorgang beeinträchtigt. Der Wert ist `true` , wenn die-Sperre bewirken kann, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet, andernfalls `false` .  
  
 Obwohl der Wert für `true` die Laufzeit nicht beeinträchtigt wird, kann er die Profil Erstellungs Ergebnisse verzerren.  
  
## <a name="remarks"></a>Hinweise  

 Es ist möglich, mehr als ein paar von `JITCompilationStarted` -und [ICorProfilerCallback:: jitcompilationabgeschlossene](icorprofilercallback-jitcompilationfinished-method.md) -aufrufen für jede Funktion zu erhalten, da die Laufzeit Klassenkonstruktoren verarbeitet. Beispielsweise beginnt die Laufzeit mit der JIT-Kompilierungs Methode A, aber der Klassenkonstruktor für Klasse B muss ausgeführt werden. Daher kompiliert die Runtime JIT den Konstruktor für Klasse B und führt Sie aus. Während der Konstruktor ausgeführt wird, ruft er die Methode a auf, die bewirkt, dass die Methode a erneut JIT-kompiliert wird. In diesem Szenario wird die erste JIT-Kompilierung der Methode A angehalten. Beide Versuche der JIT-Kompilierungs Methode A werden jedoch mit JIT-Kompilierungs Ereignissen gemeldet. Wenn der Profiler den MSIL-Code (Microsoft Intermediate Language) für Methode A durch Aufrufen der [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) -Methode ersetzen soll, muss er dies für beide `JITCompilationStarted` Ereignisse tun, er kann jedoch für beide Ereignisse denselben MSIL-Block verwenden.  
  
 Profiler müssen die Sequenz der JIT-Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe erstellen. Beispielsweise ruft Thread A auf `JITCompilationStarted` . Bevor Thread a aufruft `JITCompilationFinished` , ruft Thread B jedoch [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID aus dem Rückruf von Thread a auf `JITCompilationStarted` . Es kann vorkommen, dass die Funktions-ID noch nicht gültig ist, da ein-Aufrufwert `JITCompilationFinished` noch nicht vom Profiler empfangen wurde. In einem solchen Fall ist die Funktions-ID jedoch gültig.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [JITCompilationFinished-Methode](icorprofilercallback-jitcompilationfinished-method.md)
