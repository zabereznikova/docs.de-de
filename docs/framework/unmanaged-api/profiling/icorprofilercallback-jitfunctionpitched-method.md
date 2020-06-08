---
title: ICorProfilerCallback::JITFunctionPitched-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 2715a5b6b03a5ad33a6f18fb736fce3911bfbef0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500025"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched-Methode
Benachrichtigt den Profiler, dass eine Funktion, die Just-in-time (JIT)-kompiliert wurde, aus dem Arbeitsspeicher entfernt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 in Die ID der Funktion, die entfernt wurde.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn die entfernte Funktion aufgerufen wird, empfängt der Profiler neue JIT-Kompilierungs Ereignisse, wenn die Funktion erneut kompiliert wird. Der Common Language Runtime (CLR)-JIT-Compiler entfernt derzeit keine Funktionen aus dem Arbeitsspeicher, weshalb dieser Rückruf derzeit nicht verwendet wird und nicht vom Profiler empfangen wird.  
  
 Der Wert von `functionId` ist erst gültig, wenn die Funktion erneut kompiliert wird. Wenn die Funktion erneut kompiliert wird, wird derselbe `functionId` Wert verwendet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
