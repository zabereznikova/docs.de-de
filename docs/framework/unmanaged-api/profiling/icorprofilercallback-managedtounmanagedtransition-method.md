---
title: ICorProfilerCallback::ManagedToUnmanagedTransition-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: 0750ac66c654285e11dbbb5941f029bf5f900842
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866194"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition-Methode
Benachrichtigt den Profiler, dass ein Übergang von verwaltetem Code zu nicht verwaltetem Code erfolgt ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 in Die ID der Funktion, die aufgerufen wird.  
  
 `reason`  
 in Ein Wert der [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) -Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von nicht verwaltetem Code aus verwaltetem Code aufgetreten ist, oder aufgrund einer Rückgabe von einer verwalteten Funktion, die von einer nicht verwalteten Funktion aufgerufen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert von `reason` COR_PRF_TRANSITION_CALL ist, entspricht die Funktions-ID der der nicht verwalteten Funktion, die nie mit dem Just-in-Time-Compiler kompiliert wurde. Nicht verwalteten Funktionen sind grundlegende Informationen zugeordnet, z. b. ein Name und einige Metadaten. Wenn die nicht verwaltete Funktion mit dem impliziten Platt Form Aufruf (PInvoke) aufgerufen wurde, kann die Laufzeit das Ziel des Aufrufs nicht bestimmen, und der Wert `functionId` ist NULL. Weitere Informationen zu implizitem PInvoke finden [Sie C++ unter Using Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [UnmanagedToManagedTransition-Methode](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
