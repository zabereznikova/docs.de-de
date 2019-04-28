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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3550f4da497574ea5076766ad201e9431af52e4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598018"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode
Benachrichtigt den Profiler, dass eine Suche für eine Funktion, die vorher mit dem Native Image Generator (NGen.exe) kompiliert wurde, gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion für die Suche ausgeführt wird.  
  
 `pbUseCachedFunction`  
 [out] `true` , wenn die ausführungs-Engine die zwischengespeicherte Version einer Funktion (falls verfügbar) verwenden soll, andernfalls `false`. Wenn der Wert ist `false`, das Ausführungsmodul JIT-kompiliert wird die Funktion anstelle einer Version, die keine JIT-kompiliert wird.  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 2.0 der `JITCachedFunctionSearchStarted` und [ICorProfilerCallback:: JITCachedFunctionSearchFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) Rückrufe kommt nicht zustande, für alle Funktionen in reguläre NGen-Images. Nur NGen-Images, die für ein Profil optimiert generiert Rückrufe für alle Funktionen in der Abbildung. Aufgrund der zusätzlichen Aufwand, sollte ein Profiler jedoch optimierten Profiler der NGen-Images anfordern, nur dann, wenn diese Rückrufe verwendet, eine Funktion, die kompilierten just-in-Time (JIT) werden erzwungen werden soll. Andernfalls sollte der Profiler eine Strategie für die verzögerte verwenden, zum Erfassen von Funktionsinformationen.  
  
 Profiler müssen Fällen unterstützen, in denen mehrere Threads einer Anwendung ein Profil erstellt wurde gleichzeitig die gleiche Methode aufrufen. Thread A ruft z. B. `JITCachedFunctionSearchStarted` und der Profiler reagiert durch Festlegen von *PbUseCachedFunction*auf "false", um JIT-Kompilierung zu erzwingen. Anschließend ruft Thread A [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) und [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Jetzt thread B ruft `JITCachedFunctionSearchStarted` für die gleiche Funktion. Auch wenn der Profiler die Absicht zu JIT-Kompilieren der Funktion angegeben hat, empfängt der Profiler den zweiten Rückruf an, daran, dass Thread B den Rückruf sendet, bevor Sie der Profiler auf Thread A-Aufruf geantwortet hat `JITCachedFunctionSearchStarted`. Die Reihenfolge, in der die Threads aufrufen, hängt davon ab, wie die Threads geplant werden.  
  
 Wenn der Profiler doppelte Rückrufe empfängt, muss er legen Sie den Wert verweist `pbUseCachedFunction` auf den gleichen Wert für alle doppelten Rückrufe. Das heißt, wenn `JITCachedFunctionSearchStarted` mehrmals aufgerufen wird, mit dem gleichen `functionId` Wert, der Profiler muss die gleiche jedes Mal reagieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
