---
title: FunctionIDMapper-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionIDMapper
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionIDMapper
helpviewer_keywords: FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 24e48ecb551a5faacc7da94b857b2e260f5aeca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="functionidmapper-function"></a>FunctionIDMapper-Funktion
Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückrufe für diese Funktion. Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.  
  
## <a name="syntax"></a>Syntax  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Der Funktionsbezeichner, der neu zugeordnet werden soll.  
  
 `pbHookFunction`  
 [out] Ein Zeiger auf einen Wert, der Profiler festlegt, `true` , wenn er empfangen will `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe; andernfalls wird dieser Wert auf `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Profiler gibt einen Wert zurück, den das Ausführungsmodul als alternativen Funktionsbezeichner verwendet. Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben. Andernfalls liefert ein Rückgabewert von null zu unvorhersehbaren Ergebnissen, einschließlich des möglichen Anhaltens des Prozesses.  
  
## <a name="remarks"></a>Hinweise  
 Die `FunctionIDMapper` -Funktion ist ein Rückruf. Die Implementierung erfolgt durch den Profiler an eine Partitionsfunktions-ID auf einen anderen Bezeichner neu zuordnen, die besser eignet, um den Profiler. Die `FunctionIDMapper` gibt die alternative-ID für jede gegebene Funktion verwendet werden soll. Das Ausführungsmodul berücksichtigt dann die Anforderung des Profilers übergeben diese alternative ID zusätzlich zu den herkömmlichen Funktions-ID an dem Profiler in den `clientData` Parameter von der `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Hooks, um zu identifizieren die Funktion für die die Hookfunktion aufgerufen wird.  
  
 Können Sie die [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) an die Implementierung der Methode der `FunctionIDMapper` Funktion. Sie erreichen die `ICorProfilerInfo::SetFunctionIDMapper` -Methode nur einmal, und wir empfehlen zudem, dass Sie daher in der [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.  
  
 Standardmäßig wird davon ausgegangen, dass ein Profiler, die das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe festlegt [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), und Hooks über [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), erhalten die `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe für jede Funktion. Allerdings Profiler implementieren können `FunctionIDMapper` , selektiv zu vermeiden, dass diese Rückrufe für bestimmte Funktionen durch Festlegen von `pbHookFunction` auf `false`.  
  
 Profiler sollten fehlertolerante der Fälle werden, in denen mehrere Threads einer Anwendung mit Profil dieselbe Methode/Funktion gleichzeitig aufrufen. In solchen Fällen erhält der Profiler kann mehrere `FunctionIDMapper` Rückrufe für dieselbe `FunctionID`. Der Profiler sollte sichergestellt sein, um die Werte von diesem Rückruf zurückgeben, wenn sie mehrere Male, mit dem gleichen aufgerufen wird `FunctionID`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [SetFunctionIDMapper-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [FunctionIDMapper2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
