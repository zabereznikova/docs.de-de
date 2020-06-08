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
ms.openlocfilehash: 0da67f0d4be779cc21481d03a21209620289888e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500058"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>ICorProfilerCallback::JITCompilationFinished-Methode
Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion abgeschlossen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameter

- `functionId`

  \[in] die ID der Funktion, die kompiliert wurde.

- `hrStatus`

  \[in] ein Wert, der angibt, ob die Kompilierung erfolgreich war.

- `fIsSafeToBlock`

  \[in] ein Wert, der angibt, ob die Blockierung den Lauf Zeitvorgang beeinträchtigt. Der Wert ist `true` , wenn die-Sperre bewirken kann, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet, andernfalls `false` .

  Obwohl der Wert für `true` die Laufzeit nicht beeinträchtigt wird, kann er die Profil Erstellungs Ergebnisse verzerren.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [JITCompilationStarted-Methode](icorprofilercallback-jitcompilationstarted-method.md)
