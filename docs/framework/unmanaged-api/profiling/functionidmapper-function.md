---
title: FunctionIDMapper-Funktion
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: 23c6f0a29160b6e1dc194cf360c07374c565522b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440705"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper-Funktion
Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)-, [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)-und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) -Rückrufe für diese Funktion verwendet werden soll. `FunctionIDMapper` ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Der Funktionsbezeichner, der neu zugeordnet werden soll.  
  
 `pbHookFunction`  
 vorgenommen Ein Zeiger auf einen Wert, den der Profiler auf `true` festlegt, wenn er `FunctionEnter2`, `FunctionLeave2`und `FunctionTailcall2` Rückrufe empfangen möchte. Andernfalls wird dieser Wert auf `false`festgelegt.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet. Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben. Andernfalls führt ein NULL-Rückgabewert zu unvorhersehbaren Ergebnissen, einschließlich der möglichen Beendigung des Prozesses.  
  
## <a name="remarks"></a>Hinweise  
 Die `FunctionIDMapper`-Funktion ist ein Rückruf. Sie wird vom Profiler implementiert, um eine Funktions-ID einem anderen Bezeichner zuzuordnen, der für den Profiler nützlicher ist. Der `FunctionIDMapper` gibt die Alternative ID zurück, die für eine bestimmte Funktion verwendet werden soll. Die Ausführungs-Engine berücksichtigt dann die Anforderung des Profilers durch Übergeben dieser alternativen ID zusätzlich zur herkömmlichen Funktions-ID an den Profiler im `clientData`-Parameter der `FunctionEnter2`, `FunctionLeave2`und `FunctionTailcall2` Hooks, um die Funktion zu identifizieren, für die der Hook aufgerufen wird.  
  
 Sie können die [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) -Methode verwenden, um die Implementierung der `FunctionIDMapper`-Funktion anzugeben. Die `ICorProfilerInfo::SetFunctionIDMapper`-Methode kann nur einmal aufgerufen werden, und es wird empfohlen, dass Sie dies im [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) -Rückruf durchführen.  
  
 Standardmäßig wird davon ausgegangen, dass ein Profiler, der das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe von [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)festlegt und Hooks über [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)festlegt, die `FunctionEnter2`-, `FunctionLeave2`-und `FunctionTailcall2` Rückrufe für jede Funktion empfangen soll. Allerdings können Profiler `FunctionIDMapper` implementieren, um den Empfang dieser Rückrufe für bestimmte Funktionen selektiv zu vermeiden, indem Sie `pbHookFunction` auf `false`festlegen.  
  
 Profiler sollten für Fälle tolerant sein, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode bzw. Funktion gleichzeitig aufrufen. In solchen Fällen empfängt der Profiler möglicherweise mehrere `FunctionIDMapper` Rückrufe für denselben `FunctionID`. Der Profiler sollte sicher sein, dass er dieselben Werte von diesem Rückruf zurückgibt, wenn er mehrmals mit demselben `FunctionID`aufgerufen wird.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [SetFunctionIDMapper-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
