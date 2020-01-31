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
ms.openlocfilehash: 01989812b85cf98aedfd8855bee7b2dfbfd375f4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790064"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode
Benachrichtigt den Profiler, dass eine Suche für eine Funktion gestartet wurde, die zuvor mit dem Native Image Generator (Ngen. exe) kompiliert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Parameters

- `functionId`

  \[in] die ID der Funktion, für die die Suche ausgeführt wird.

- `pbUseCachedFunction`

  \[out] `true`, wenn die Ausführungs-Engine die zwischengespeicherte Version einer Funktion (falls verfügbar) verwenden soll. Andernfalls `false`. Wenn der Wert `false`ist, kompiliert die Ausführungs-Engine die Funktion, anstatt eine Version zu verwenden, die nicht JIT-kompiliert ist.

## <a name="remarks"></a>Hinweise  
 In der .NET Framework Version 2,0 werden die Methoden Rückrufe `JITCachedFunctionSearchStarted` und [ICorProfilerCallback:: jitcachedfunctionsearchfertige](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) nicht für alle Funktionen in regulären NGen-Images erstellt. Nur NGen-Images, die für ein Profil optimiert werden, generieren Rückrufe für alle Funktionen im Image. Aufgrund des zusätzlichen Aufwands sollte ein Profiler jedoch nur Profiler-optimierte NGen-Images anfordern, wenn er diese Rückrufe verwenden soll, um zu erzwingen, dass eine Funktion Just-in-time (JIT) kompiliert wird. Andernfalls sollte der Profiler eine verzögerte Strategie zum Sammeln von Funktions Informationen verwenden.  
  
 Profiler müssen Fälle unterstützen, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode gleichzeitig aufrufen. Thread A ruft z. b. `JITCachedFunctionSearchStarted` auf, und der Profiler antwortet durch Festlegen von *pbUseCachedFunction*auf false, um die JIT-Kompilierung zu erzwingen. Thread A ruft dann [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) und [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)auf.  
  
 Nun ruft Thread B `JITCachedFunctionSearchStarted` für dieselbe Funktion auf. Obwohl der Profiler seine Absicht zur JIT-Kompilierung der Funktion angegeben hat, empfängt der Profiler den zweiten Rückruf, da Thread B den Rückruf sendet, bevor der Profiler auf den `JITCachedFunctionSearchStarted`von Thread A geantwortet hat. Die Reihenfolge, in der die Threads Aufrufe ausführen, hängt davon ab, wie die Threads geplant werden.  
  
 Wenn der Profiler doppelte Rückrufe empfängt, muss der Wert, auf den durch `pbUseCachedFunction` verwiesen wird, auf denselben Wert für alle doppelten Rückrufe festgelegt werden. Das heißt, wenn `JITCachedFunctionSearchStarted` mehrmals mit dem gleichen `functionId` Wert aufgerufen wird, muss der Profiler jedes Mal gleich reagieren.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
