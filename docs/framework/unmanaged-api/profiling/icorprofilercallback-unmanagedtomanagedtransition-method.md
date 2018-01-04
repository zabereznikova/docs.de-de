---
title: ICorProfilerCallback::UnmanagedToManagedTransition-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.UnmanagedToManagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1653a92563f0031fcb4c215dd58e4e1ac73030d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition-Methode
Benachrichtigt den Profiler, dass ein Übergang zwischen nicht verwaltetem Code zu verwaltetem Code aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die aufgerufen wird.  
  
 `reason`  
 [in] Der Wert der [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von nicht verwaltetem Code zu verwaltetem Code oder aufgrund einer Rückgabe von einer verwalteten Funktion aufgerufen wird, indem Sie eine verwaltete aufgetreten ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert der `reason` COR_PRF_TRANSITION_RETURN und `functionId` nicht null ist, ist die Funktion-ID ist, die nicht verwaltete Funktion und wird nie wurden kompiliert den Just-in-Time (JIT)-Compiler verwenden. Nicht verwaltete Funktionen haben einige grundlegende Informationen zugeordnet werden, z. B. einen Namen und einige Metadaten.  
  
 Wenn der Wert des `reason` COR_PRF_TRANSITION_CALL, ist es eventuell möglich, dass die aufgerufene Funktion (d. h. die verwaltete Funktion) noch kein JIT-kompiliert wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ManagedToUnmanagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [Verwenden von C++-Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
