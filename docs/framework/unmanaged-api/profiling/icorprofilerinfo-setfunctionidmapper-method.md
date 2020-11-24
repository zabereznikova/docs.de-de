---
title: ICorProfilerInfo::SetFunctionIDMapper-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 3a9ab64730feaa372f9b5d9ad7cefcb86580ca5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671173"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a>ICorProfilerInfo::SetFunctionIDMapper-Methode

Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a>Parameter  

 `pFunc`  
 in Ein Zeiger auf die [FunctionIDMapper](functionidmapper-function.md) -Implementierung, die aufgerufen wird, um die `FunctionID` Werte ihren alternativen Werten zuzuordnen.  
  
## <a name="remarks"></a>Hinweise  

 Die Alternativen für die `FunctionID` Werte werden an die Funktions Einstiegs-/Beendigungs Hooks des Profilers ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)und [FunctionTailcall2](functiontailcall2-function.md)) übermittelt, die von der [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) -Methode angegeben werden.  
  
 Der `FunctionIDMapper` kann nur ein Mal festgelegt werden, und es wird empfohlen, ihn im [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf festzulegen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
