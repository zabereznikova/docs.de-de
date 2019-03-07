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
ms.openlocfilehash: 84ba3996d91d0e8a6bbf9cb1071a37909f2ee16d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484913"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition-Methode
Benachrichtigt den Profiler, dass ein Übergang aus verwaltetem Code an nicht verwalteten Code aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die aufgerufen wird.  
  
 `reason`  
 [in] Der Wert der [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) Enumeration, der angibt, ob der Übergang erfolgt ist, aufgrund eines Aufrufs in nicht verwaltetem Code aus verwaltetem Code oder aufgrund einer Rückgabe von einer verwalteten Funktion, die von einer nicht aufgerufen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert des `reason` COR_PRF_TRANSITION_CALL die Funktion, die ID ist, dass der nicht verwaltete Funktion, die nicht kompiliert wurden wird mithilfe des just-in-Time-Compilers. Nicht verwaltete Funktionen sind grundlegende Informationen, die zugeordnet sind, z. B. einen Namen und einige Metadaten. Wenn die nicht verwaltete Funktion aufgerufen wurde, mithilfe des impliziten Plattform Plattformaufruf (PInvoke), die Laufzeit nicht bestimmen, das Ziel des Aufrufs und den Wert der `functionId` NULL. Weitere Informationen zu implizites PInvoke, finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [UnmanagedToManagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
