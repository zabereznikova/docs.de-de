---
title: ICorProfilerCallback::ManagedToUnmanagedTransition-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ManagedToUnmanagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9da8dd44d5b87cd1c65b8b8837c9dd378039d332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition-Methode
Benachrichtigt den Profiler, dass Übergang von verwaltetem Code in nicht verwaltetem Code aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die aufgerufen wird.  
  
 `reason`  
 [in] Der Wert der [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs an nicht verwalteten Code aus verwaltetem Code oder aufgrund einer Rückgabe von einer verwalteten Funktion aufgerufen, die von einer nicht verwalteten aufgetreten ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert des `reason` COR_PRF_TRANSITION_CALL Funktion ID ist, dass der nicht verwaltete Funktion, die nie kompiliert wurden wird mithilfe des Just-in-Time-Compilers. Nicht verwaltete Funktionen sind grundlegende Informationen, die zugeordnet werden, z. B. einen Namen und einige Metadaten. Wenn die nicht verwaltete Funktion aufgerufen wurde, mithilfe der impliziten Plattform (PInvoke) aufrufen, die Common Language Runtime kann nicht bestimmt werden, das Ziel des Aufrufs und den Wert des `functionId` wird null sein. Weitere Informationen zu implizites PInvoke, finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [UnmanagedToManagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
