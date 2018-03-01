---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2208a1a1637b3bb8dd7d7963ab806aeae7921dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode
Benachrichtigt den Profiler, dass eine Suche für eine Funktion, die zuvor mit der Native Image Generator (NGen.exe) kompiliert wurde, gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion für die Suche durchgeführt wird.  
  
 `pbUseCachedFunction`  
 [out] `true` , wenn das Ausführungsmodul die zwischengespeicherte Version einer Funktion (falls vorhanden) verwenden soll; andernfalls `false`. Wenn der Wert `false`, das Ausführungsmodul JIT-kompiliert der Funktion statt mit einer Version, die keine JIT-kompiliert wird.  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 2.0 die `JITCachedFunctionSearchStarted` und [ICorProfilerCallback:: JITCachedFunctionSearchFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) Rückrufe werden nicht für alle Funktionen in regulären NGen-Images gestellt. Nur NGen-Images, die für ein Profil optimiert generiert Rückrufe für alle Funktionen in der Abbildung. Aufgrund der zusätzlichen Verwaltungsaufwand, sollte ein Profiler jedoch Profiler optimiert NGen-Images anfordern, nur, wenn sie beabsichtigt, diese Rückrufe verwenden, um eine Funktion zu kompilierten just-in-Time (JIT) zu erzwingen. Andernfalls sollte der Profiler eine Strategie für die verzögerte verwenden, für das Sammeln von Informationen.  
  
 Profiler müssen Fälle unterstützen, in denen mehrere Threads einer Anwendung mit Profil dieselbe Methode gleichzeitig aufgerufen werden. Beispielsweise ruft Thread A `JITCachedFunctionSearchStarted` und der Profiler reagiert durch Festlegen von *PbUseCachedFunction*auf "false", um JIT-Kompilierung zu erzwingen. Anschließend ruft Thread A [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) und [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Jetzt ruft thread B `JITCachedFunctionSearchStarted` für die gleiche Funktion. Auch wenn der Profiler die Absicht JIT-kompiliert die Funktion angegeben wurde, empfängt der Profiler die zweite Rückruf, weil Thread B den Rückruf sendet, bevor Sie der Profiler an Thread A Aufruf reagiert wurde `JITCachedFunctionSearchStarted`. Die Reihenfolge, in der die Threads Aufrufe ausführen, hängt davon ab, wie die Threads geplant werden.  
  
 Wenn der Profiler doppelte Rückrufe empfängt, muss er legen Sie den Wert verweist `pbUseCachedFunction` auf den gleichen Wert für alle doppelten Rückrufe. Das heißt, wenn `JITCachedFunctionSearchStarted` mehrere Male aufgerufen wird, mit dem gleichen `functionId` Wert, der Profiler muss die gleiche jedes Mal reagieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
