---
title: ICorProfilerInfo3::SetFunctionIDMapper2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 26c26cf204f1a2743f46cfcfdfadbf2c3e3df38e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721568"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a>ICorProfilerInfo3::SetFunctionIDMapper2-Methode

Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden. Diese Methode erweitert die [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) -Methode mit einem zusätzlichen Daten Parameter, den Profiler verwenden können, um die Unterschiede Zwischenlauf Zeiten zu unterscheiden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a>Parameter  

 `pFunc`  
 in Ein Zeiger auf eine [FunctionIDMapper2](functionidmapper2-function.md) -Implementierung, die aufgerufen wird, um die `FunctionID` Werte ihren alternativen Werten zuzuordnen.  
  
 `clientData`  
 in Ein Zeiger, der an jeden von der aktuellen Laufzeit an jeden [FunctionIDMapper2](functionidmapper2-function.md) -Funktions aufrufenen aufgerufen wird. Der Profiler kann diese Informationen verwenden, um die Unterschiede Zwischenlauf Zeiten zu unterscheiden.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="remarks"></a>Hinweise  

 Die Alternativen für die FunctionID-Werte werden an die Funktions-und Beendigungs Hooks des Profiler ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)und [FunctionTailcall3](functiontailcall3-function.md); oder [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)), die durch die [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) -Methode oder die [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) -Methode angegeben werden, übermittelt.  
  
 Die- `FunctionIDMapper2` Methode kann nur einmal festgelegt werden. es wird empfohlen, Sie im [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf festzulegen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
