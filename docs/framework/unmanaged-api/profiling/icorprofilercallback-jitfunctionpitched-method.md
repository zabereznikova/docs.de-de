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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf51d2a0e7381cd495da8f3846302ec806c34774
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451411"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched-Methode
Benachrichtigt den Profiler, die eine Funktion, die in-Time (JIT)-Kompilierung wurde aus dem Arbeitsspeicher entfernt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die entfernt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die entfernte Funktion aufgerufen wird, erhält der Profiler neue JIT-Kompilierung Ereignisse aus, wenn die Funktion neu kompiliert wird. JIT-Compiler der common Language Runtime (CLR) entfernen derzeit nicht Funktionen aus dem Arbeitsspeicher, damit dieser Rückruf zurzeit nicht verwendet wird und nicht vom Profiler empfangen.  
  
 Der Wert des `functionId` ist nicht gültig, bis die Funktion neu kompiliert wird. Wenn die Funktion neu kompiliert wird, die gleiche `functionId` Wert verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
