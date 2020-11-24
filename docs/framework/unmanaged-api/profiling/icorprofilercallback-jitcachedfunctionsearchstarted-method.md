---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
ms.openlocfilehash: 938da4e3b7cc45c24dcac872ab504755116197a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684030"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode

Benachrichtigt den Profiler, dass eine Suche für eine Funktion gestartet wurde, die zuvor mit dem Native Image Generator (NGen.exe) kompiliert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Parameter

- `functionId`

  \[in] die ID der Funktion, für die die Suche ausgeführt wird.

- `pbUseCachedFunction`

  \[out] `true` , wenn die Ausführungs-Engine die zwischengespeicherte Version einer Funktion (falls verfügbar) verwenden soll, andernfalls `false` . Wenn der Wert ist `false` , kompiliert die Ausführungs-Engine die Funktion, anstatt eine Version zu verwenden, die nicht JIT-kompiliert ist.

## <a name="remarks"></a>Hinweise  

 In der .NET Framework Version 2,0 werden die `JITCachedFunctionSearchStarted` Methoden Rückrufe und [ICorProfilerCallback:: jitcachedfunctionsearchbeendeten](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) nicht für alle Funktionen in regulären NGen-Images erstellt. Nur NGen-Images, die für ein Profil optimiert werden, generieren Rückrufe für alle Funktionen im Image. Aufgrund des zusätzlichen Aufwands sollte ein Profiler jedoch nur Profiler-optimierte NGen-Images anfordern, wenn er diese Rückrufe verwenden soll, um zu erzwingen, dass eine Funktion Just-in-time (JIT) kompiliert wird. Andernfalls sollte der Profiler eine verzögerte Strategie zum Sammeln von Funktions Informationen verwenden.  
  
 Profiler müssen Fälle unterstützen, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode gleichzeitig aufrufen. Beispielsweise ruft Thread A auf, `JITCachedFunctionSearchStarted` und der Profiler antwortet, indem *pbUseCachedFunction* auf false festgelegt wird, um die JIT-Kompilierung zu erzwingen. Thread A ruft dann [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) und [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationfinished-method.md)auf.  
  
 Nun ruft Thread B `JITCachedFunctionSearchStarted` für dieselbe Funktion auf. Obwohl der Profiler seine Absicht zur JIT-Kompilierung der Funktion angegeben hat, empfängt der Profiler den zweiten Rückruf, da Thread B den Rückruf sendet, bevor der Profiler auf den Aufrufe von Thread A geantwortet hat `JITCachedFunctionSearchStarted` . Die Reihenfolge, in der die Threads Aufrufe ausführen, hängt davon ab, wie die Threads geplant werden.  
  
 Wenn der Profiler doppelte Rückrufe empfängt, muss der Wert, auf den von verwiesen wird, `pbUseCachedFunction` auf denselben Wert für alle doppelten Rückrufe festgelegt werden. Das heißt, wenn `JITCachedFunctionSearchStarted` mehrmals mit demselben Wert aufgerufen wird `functionId` , muss der Profiler jedes Mal gleich reagieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
