---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de225a0d4855cbd3f8a46787c2472ca727558fc9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669652"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode
Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen ist, die vorher mit dem Native Image Generator (NGen.exe) kompiliert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion für die Suche ausgeführt wurde.  
  
 `result`  
 [in] Der Wert der [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) -Enumeration, der das Ergebnis der Suche angibt.  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 2.0 der [ICorProfilerCallback:: JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) und `JITCachedFunctionSearchFinished` Rückrufe kommt nicht zustande, für alle Funktionen in reguläre NGen-Images. Nur NGen-Images, die für ein Profiler optimiert generiert Rückrufe für alle Funktionen in der Abbildung. Aufgrund der zusätzlichen Aufwand, sollte ein Profiler jedoch optimierten Profiler der NGen-Images anfordern, nur dann, wenn diese Rückrufe verwendet, eine Funktion, die kompilierten just-in-Time (JIT) werden erzwungen werden soll. Andernfalls sollte der Profiler eine Strategie für die verzögerte verwenden, zum Erfassen von Funktionsinformationen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
