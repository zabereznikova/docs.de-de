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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175173"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper-Funktion
Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den Callbacks [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)und [FunctionTailcall2](functiontailcall2-function.md) für diese Funktion verwendet werden soll. Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parameter

- `funcId`

  \[in] Der Funktionsbezeichner, der neu zugeordnet werden soll.

- `pbHookFunction`

  \[out] Ein Zeiger auf einen Wert, `true` auf den der `FunctionEnter2` `FunctionLeave2`Profiler `FunctionTailcall2` setzt, wenn er , und Rückrufe empfangen möchte; Andernfalls wird dieser Wert `false`auf festgelegt.

## <a name="return-value"></a>Rückgabewert  
 Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet. Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben. Andernfalls führt ein NULL-Rückgabewert zu unvorhersehbaren Ergebnissen, einschließlich des möglicherweise anhaltenden Prozesses.  
  
## <a name="remarks"></a>Bemerkungen  
 Die `FunctionIDMapper` Funktion ist ein Rückruf. Sie wird vom Profiler implementiert, um eine Funktions-ID einem anderen Bezeichner neu zuzuordnen, der für den Profiler nützlicher ist. Der `FunctionIDMapper` gibt die alternative ID zurück, die für eine bestimmte Funktion verwendet werden soll. Das Ausführungsmodul berücksichtigt dann die Anforderung des Profilers, indem es diese alternative ID zusätzlich `clientData` zur traditionellen `FunctionEnter2` `FunctionLeave2`Funktions-ID an den Profiler im Parameter von , und `FunctionTailcall2` Hooks zurückgibt, um die Funktion zu identifizieren, für die der Hook aufgerufen wird.  
  
 Sie können die [ICorProfilerInfo::SetFunctionIDMapper-Methode](icorprofilerinfo-setfunctionidmapper-method.md) verwenden, `FunctionIDMapper` um die Implementierung der Funktion anzugeben. Sie können `ICorProfilerInfo::SetFunctionIDMapper` die Methode nur einmal aufrufen, und wir empfehlen, dies im [ICorProfilerCallback::Initialize-Rückruf](icorprofilercallback-initialize-method.md) zu tun.  
  
 Standardmäßig wird davon ausgegangen, dass ein Profiler, der das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe von [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md)festlegt und Hooks über [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), für jede Funktion empfängt. `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` Profiler können jedoch `FunctionIDMapper` implementieren, um selektiv den Empfang dieser `pbHookFunction` Rückrufe für bestimmte Funktionen zu vermeiden, indem sie auf `false`festlegen.  
  
 Profiler sollten tolerant gegenüber Fällen sein, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode/Funktion gleichzeitig aufrufen. In solchen Fällen kann der `FunctionIDMapper` Profiler mehrere Rückrufe für dieselbe `FunctionID`erhalten. Der Profiler sollte sicher sein, dass er dieselben Werte aus diesem `FunctionID`Rückruf zurückgibt, wenn er mehrmals mit derselben aufgerufen wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [SetFunctionIDMapper-Methode](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2-Funktion](functionidmapper2-function.md)
- [FunctionEnter2-Funktion](functionenter2-function.md)
- [FunctionLeave2-Funktion](functionleave2-function.md)
- [FunctionTailcall2-Funktion](functiontailcall2-function.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
