---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58e7b3e76d90e9e43f3f5259c52b52cd9f8e1f6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455074"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode
Gibt Profiler implementierten Funktionen an, die für "eingeben", "Übernehmen" und "Tailcall" Hooks von verwalteten Funktionen aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pFuncEnter`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) Rückruf.  
  
 `pFuncLeave`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) Rückruf.  
  
 `pFuncTailcall`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) Rückruf.  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 1.0 kann jeder Funktionszeiger So deaktivieren Sie die entsprechenden Rückruffunktion null sein.  
  
 Nur ein Satz von Rückrufen kann zu einem Zeitpunkt aktiv sein. Daher, wenn ein Profiler beide ruft `SetEnterLeaveFunctionHooks` und [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), klicken Sie dann `SetEnterLeaveFunctionHooks2` hat Vorrang vor.  
  
 Die `SetEnterLeaveFunctionHooks` Methode kann aufgerufen werden, nur von des Profilers [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
