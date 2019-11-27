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
ms.openlocfilehash: 88c9f552b73af69ea4e1f64b75ed74ea762dcdfb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429942"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags-Methode
Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) -Enumeration fest, um die Codegenerierung für die neu kompilierte Just-in-time (JIT)-Funktion zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>Parameter  
 `flags`  
 in Ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) -Enumeration.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler Ruft eine Instanz dieser Schnittstelle über den [ICorProfilerCallback4:: getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) -Rückruf ab. `SetCodegenFlags` ermöglicht es dem Profiler, die Codegenerierung für die neu kompilierte Funktion zu steuern. Wie bei allen anderen JIT-neukompilierungs Parametern gelten die Code Generierungs Flags für alle Instanzen der Funktion.  
  
 Der JIT-Compiler berücksichtigt diese Kompilierungs Flags zusammen mit anderen Flags, die von anderen Quellen angegeben werden, wenn eine Funktion kompiliert wird.  Die anderen Quellen enthalten den Debugger, globale Flags, die vom Profiler beim Start festgelegt werden, mit der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) -Methode (mit den Werten `COR_PRF_DISABLE_INLINING` und `COR_PRF_DISABLE_OPTIMIZATIONS`) und dem [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) -Rückruf des Profilers.  Der JIT-Compiler hat Vorrang vor einer Quelle, die den geringsten Optimierungs Aufwand anfordert.  Wenn der Profiler z. b. `COR_PRF_DISABLE_INLINING` beim Start angibt, aber keine `COR_PRF_CODEGEN_DISABLE_INLINING` im [icorprofilerfunctioncontrol:: setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) -Rückruf angibt, ist Inlining weiterhin deaktiviert.  Wenn der Profiler in `SetCodegenFlags`keine `COR_PRF_CODEGEN_DISABLE_INLINING` angibt, sondern das Inlining mithilfe des [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) -Rückrufs deaktiviert, ist Inlining deaktiviert.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerFunctionControl-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
