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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0735e4c59ba609ed87d61aca737c4f8a4dab757a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453485"
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
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [UnmanagedToManagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
