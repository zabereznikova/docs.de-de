---
title: ICorProfilerFunctionControl::SetCodegenFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43c32d1ce4f804da8980dc0c566a77e5b076661b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459612"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags-Methode
Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) Steuerelement codegenerierung für eine just-in-Time (JIT)-Enumeration kompiliert Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a>Parameter  
 `flags`  
 [in] Ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) Enumeration.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler Ruft eine Instanz dieser Schnittstelle durch den [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) Rückruf. `SetCodegenFlags` ermöglicht es dem Profiler zum Steuern der codegenerierung für die neu kompilierten Funktion. Wie bei allen anderen JIT-Neukompilierung Parametern, wenden die codeerstellungskennzeichen auf alle Instanzen der Funktion ein.  
  
 Der JIT-Compiler berücksichtigt diese Flags Kompilierung zusammen mit anderen Flags, die mit anderen Datenquellen angegeben werden, wenn eine Funktion zu kompilieren.  Die anderen Quellen umfassen den Debugger, globale Kennzeichen festgelegt, indem der Profiler beim Start von mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode (mit den Werten `COR_PRF_DISABLE_INLINING` und `COR_PRF_DISABLE_OPTIMIZATIONS`), und des Profilers [ ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) Rückruf.  Der JIT-Compiler gibt Vorrang einer Quelle, die am wenigsten optimieren anfordert.  Z. B., wenn der Profiler gibt `COR_PRF_DISABLE_INLINING` auf Start, aber nicht an `COR_PRF_CODEGEN_DISABLE_INLINING` in der [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) Rückruf inlining ist immer noch deaktiviert.  Auf ähnliche Weise, wenn der Profiler keine `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, aber anschließend deaktiviert inlining mithilfe der [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) Rückruf inlining ist deaktiviert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerFunctionControl-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
