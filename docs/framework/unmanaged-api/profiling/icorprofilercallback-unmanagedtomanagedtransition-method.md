---
title: ICorProfilerCallback::UnmanagedToManagedTransition-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 312f133c263becfd815f1b4ad48dff4892963aaf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227847"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition-Methode
Benachrichtigt den Profiler, dass ein Übergang von nicht verwaltetem Code an verwalteten Code aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die aufgerufen wird.  
  
 `reason`  
 [in] Der Wert der [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von nicht verwaltetem Code zu verwaltetem Code oder aufgrund einer Rückgabe von einer nicht verwalteten Funktion wird aufgerufen, indem Sie ein verwaltetes Verzeichnis aufgetreten ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert des `reason` COR_PRF_TRANSITION_RETURN und `functionId` nicht null ist, ist die ID ist der nicht verwalteten Funktion und wird nicht kompiliert wurden mithilfe des just-in-Time (JIT)-Compilers-Funktion. Nicht verwalteten Funktionen sind einige grundlegende Informationen zugeordnet sind, z. B. einen Namen und einige Metadaten.  
  
 Wenn der Wert des `reason` COR_PRF_TRANSITION_CALL, ist es eventuell möglich, dass die aufgerufene Funktion (d. h. die verwaltete Funktion) noch nicht JIT-kompiliert wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ManagedToUnmanagedTransition-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)
- [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [Verwenden von C++-Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
