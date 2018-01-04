---
title: ICorProfilerCallback::JITCompilationFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9bd1a163fa5e941c68c5dd8d7d3221e8a5aa3df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>ICorProfilerCallback::JITCompilationFinished-Methode
Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler Kompilieren eine Funktion abgeschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die kompiliert wurde.  
  
 `hrStatus`  
 [in] Ein Wert, der angibt, ob die Kompilierung erfolgreich war.  
  
 `fIsSafeToBlock`  
 [in] Ein Wert, der angibt, an den Profiler an, ob blockierende wird die Funktion der Laufzeit beeinflussen. Der Wert ist `true` Wenn blockiert die Common Language Runtime von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.  
  
 Obwohl ein Wert von `true` wird nicht auf die Common Language Runtime Schaden anrichten, sie können die Profilerstellungsergebnisse verzerren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
