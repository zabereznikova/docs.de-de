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
ms.openlocfilehash: 12f91bdd264135eb0ff3a48e15611cf5a0e3c064
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992081"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags-Methode
Legt eine oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) Enumeration Steuerelement-codegenerierung für eine just-in-Time (JIT) kompiliert Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>Parameter  
 `flags`  
 [in] Ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) Enumeration.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler Ruft eine Instanz dieser Schnittstelle durch die [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) Rückruf. `SetCodegenFlags` ermöglicht es dem Profiler zum Steuern der codegenerierung für die neu kompilierte Funktion aus. Wenden die codeerstellungskennzeichen auf alle Instanzen der Funktion, wie bei allen anderen JIT-Neukompilierung Parametern gibt.  
  
 Der JIT-Compiler berücksichtigt diese Kompilierung Flags, die zusammen mit anderen Flags, die von anderen Quellen angegeben wird, wenn eine Funktion zu kompilieren.  Die anderen Quellen umfassen den Debugger, die globale Kennzeichen festgelegt, durch den Profiler beim Start von mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode (mit den Werten `COR_PRF_DISABLE_INLINING` und `COR_PRF_DISABLE_OPTIMIZATIONS`), und des Profilers [ ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) Rückruf.  Der JIT-Compiler bietet Vorrang vor mit einer Datenquelle, die die geringste Menge an optimieren anfordert.  Wenn der Profiler gibt an, z. B. `COR_PRF_DISABLE_INLINING` auf Start, aber nicht angegeben ist `COR_PRF_CODEGEN_DISABLE_INLINING` in der [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) Rückruf, inlining ist immer noch deaktiviert.  Auf ähnliche Weise, wenn der Profiler keine angibt `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, aber dann deaktiviert inlineersetzung mithilfe der [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) Rückruf, inlining ist deaktiviert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerFunctionControl-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
