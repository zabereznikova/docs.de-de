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
ms.openlocfilehash: cda629b7a6560ca5d731cd88cffc2cffd3486d8a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866215"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched-Methode
Benachrichtigt den Profiler, dass eine Funktion, die Just-in-time (JIT)-kompiliert wurde, aus dem Arbeitsspeicher entfernt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 in Die ID der Funktion, die entfernt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die entfernte Funktion aufgerufen wird, empfängt der Profiler neue JIT-Kompilierungs Ereignisse, wenn die Funktion erneut kompiliert wird. Der Common Language Runtime (CLR)-JIT-Compiler entfernt derzeit keine Funktionen aus dem Arbeitsspeicher, weshalb dieser Rückruf derzeit nicht verwendet wird und nicht vom Profiler empfangen wird.  
  
 Der Wert `functionId` ist erst gültig, wenn die Funktion erneut kompiliert wird. Wenn die Funktion erneut kompiliert wird, wird derselbe `functionId` Wert verwendet.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
