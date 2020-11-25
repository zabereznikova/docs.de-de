---
title: ICorProfilerCallback4::ReJITCompilationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: a6c2209433a652523fd8e3a7cc2db1272600e1bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730265"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a>ICorProfilerCallback4::ReJITCompilationFinished-Methode

Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion abgeschlossen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter  

 `functionId`  
 in Die ID der Funktion, die neu kompiliert wurde.  
  
 `rejitId`  
 [in] Die Identität der erneut JIT-kompilierten Funktion.  
  
 `hrStatus`  
 in Ein Wert, der angibt, ob die JIT-Neukompilierung erfolgreich war.  
  
 `fIsSafeToBlock`  
 [in] `true` , um anzugeben, dass das blockieren möglicherweise dazu führt, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false` , um anzugeben, dass die Blockierung den Lauf der Laufzeit nicht beeinträchtigt.  
  
 Der Wert von `true` führt nicht zu einer Beeinträchtigung der Laufzeit, kann jedoch die Profil Erstellungs Ergebnisse beeinflussen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](icorprofilercallback4-interface.md)
- [JITCompilationStarted-Methode](icorprofilercallback-jitcompilationstarted-method.md)
- [ReJITCompilationStarted-Methode](icorprofilercallback4-rejitcompilationstarted-method.md)
