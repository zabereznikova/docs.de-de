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
ms.openlocfilehash: fe07270989df897c3dbf689305784f9f0af65742
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684043"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode

Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen wurde, die zuvor mit dem Native Image Generator (NGen.exe) kompiliert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a>Parameter

- `functionId`

  \[in] die ID der Funktion, für die die Suche durchgeführt wurde.

- `result`

  \[in] ein Wert der [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) -Enumeration, die das Ergebnis der Suche angibt.

## <a name="remarks"></a>Hinweise  

 In der .NET Framework Version 2,0 werden die [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) -und `JITCachedFunctionSearchFinished` Rückrufe nicht für alle Funktionen in regulären NGen-Images erstellt. Nur NGen-Images, die für einen Profiler optimiert sind, generieren Rückrufe für alle Funktionen im Image. Aufgrund des zusätzlichen Aufwands sollte ein Profiler jedoch nur Profiler-optimierte NGen-Images anfordern, wenn er diese Rückrufe verwenden soll, um zu erzwingen, dass eine Funktion Just-in-time (JIT) kompiliert wird. Andernfalls sollte der Profiler eine verzögerte Strategie zum Sammeln von Funktions Informationen verwenden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
