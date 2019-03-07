---
title: ICorProfilerCallback::JITCompilationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5556fecb6251a2dd6a131332dbff1b5ca2f5d95
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493335"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>ICorProfilerCallback::JITCompilationFinished-Methode
Benachrichtigt den Profiler, dass der just-in-Time (JIT)-Compiler die Kompilierung einer Funktion abgeschlossen ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die kompiliert wurde.  
  
 `hrStatus`  
 [in] Ein Wert, der angibt, ob die Kompilierung erfolgreich war.  
  
 `fIsSafeToBlock`  
 [in] Ein Wert, der angibt, an den Profiler an, ob blockierende wirkt sich auf den Vorgang der Runtime. Der Wert ist `true` Wenn Blockierungen der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.  
  
 Obwohl ein Wert von `true` wird die Runtime nicht beschädigen, können sie die Ergebnisse der profilerstellung verzerren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
