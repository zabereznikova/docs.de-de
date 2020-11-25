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
ms.openlocfilehash: 17396d3038578c16b74c3717174dc0fa4dc17631
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722842"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper-Funktion

Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter2](functionenter2-function.md)-, [FunctionLeave2](functionleave2-function.md)-und [FunctionTailcall2](functiontailcall2-function.md) -Rückrufe für diese Funktion verwendet werden soll. Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parameter

- `funcId`

  \[in] der Funktions Bezeichner, der neu zugeordnet werden soll.

- `pbHookFunction`

  \[out] ein Zeiger auf einen Wert, den der Profiler auf festlegt `true` , wenn er `FunctionEnter2` -,-und-Rückrufe empfangen möchte `FunctionLeave2` `FunctionTailcall2` ; andernfalls wird dieser Wert auf festgelegt `false` .

## <a name="return-value"></a>Rückgabewert  

 Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet. Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben. Andernfalls führt ein NULL-Rückgabewert zu unvorhersehbaren Ergebnissen, einschließlich der möglichen Beendigung des Prozesses.  
  
## <a name="remarks"></a>Hinweise  

 Die `FunctionIDMapper` Funktion ist ein Rückruf. Sie wird vom Profiler implementiert, um eine Funktions-ID einem anderen Bezeichner zuzuordnen, der für den Profiler nützlicher ist. Der `FunctionIDMapper` gibt die Alternative ID zurück, die für eine bestimmte Funktion verwendet werden soll. Die Ausführungs-Engine berücksichtigt dann die Anforderung des Profilers, indem diese Alternative ID zusätzlich zur herkömmlichen Funktions-ID an den Profiler im `clientData` -Parameter der `FunctionEnter2` Hooks, und zurückgegeben wird `FunctionLeave2` `FunctionTailcall2` , um die Funktion zu identifizieren, für die der Hook aufgerufen wird.  
  
 Sie können die [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) -Methode verwenden, um die Implementierung der `FunctionIDMapper` Funktion anzugeben. Die `ICorProfilerInfo::SetFunctionIDMapper` Methode kann nur einmal aufgerufen werden, und es wird empfohlen, dass Sie dies im [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf durchführen.  
  
 Standardmäßig wird davon ausgegangen, dass ein Profiler, der das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe von [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)festlegt und die Hooks über [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)festlegt, die Rückrufe `FunctionEnter2` , `FunctionLeave2` und `FunctionTailcall2` für jede Funktion empfangen soll. Allerdings können Profiler implementieren, `FunctionIDMapper` um den Empfang dieser Rückrufe für bestimmte Funktionen selektiv zu vermeiden, indem auf festgelegt wird `pbHookFunction` `false` .  
  
 Profiler sollten für Fälle tolerant sein, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode bzw. Funktion gleichzeitig aufrufen. In solchen Fällen kann der Profiler mehrere `FunctionIDMapper` Rückrufe für denselben erhalten `FunctionID` . Der Profiler sollte sicher sein, dass die gleichen Werte von diesem Rückruf zurückgegeben werden, wenn er mehrmals mit demselben aufgerufen wird `FunctionID` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [SetFunctionIDMapper-Methode](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2-Funktion](functionidmapper2-function.md)
- [FunctionEnter2-Funktion](functionenter2-function.md)
- [FunctionLeave2-Funktion](functionleave2-function.md)
- [FunctionTailcall2-Funktion](functiontailcall2-function.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
