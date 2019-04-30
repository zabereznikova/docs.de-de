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
ms.openlocfilehash: c8aa46e869d50fc7aa65c1d4244ad4ff71657bad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042028"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched-Methode
Benachrichtigt den Profiler, die eine Funktion, die just-in-Time (JIT)-kompiliert wurde aus dem Arbeitsspeicher entfernt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die entfernt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die entfernte-Funktion aufgerufen wird, erhält der Profiler den neuen JIT-Kompilierung Ereignisse aus, wenn die Funktion neu kompiliert wird. Derzeit werden JIT-Compiler der common Language Runtime (CLR) nicht entfernt Funktionen aus dem Arbeitsspeicher, damit dieser Rückruf derzeit nicht verwendet wird und wird nicht vom Profiler empfangen.  
  
 Der Wert des `functionId` ist nicht gültig, bis die Funktion neu kompiliert wird. Wenn die Funktion neu kompiliert wird, gleich `functionId` Wert verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
