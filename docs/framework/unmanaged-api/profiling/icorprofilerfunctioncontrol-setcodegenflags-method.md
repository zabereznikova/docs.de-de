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
ms.openlocfilehash: 75414ec3d2b30fe8afc5db1e97c81f34b29a3115
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864673"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags-Methode
Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) -Enumeration fest, um die Codegenerierung für die neu kompilierte Just-in-time (JIT)-Funktion zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>Parameters  
 `flags`  
 in Ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) -Enumeration.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler Ruft eine Instanz dieser Schnittstelle über den [ICorProfilerCallback4:: getrejitparameters](icorprofilercallback4-getrejitparameters-method.md) -Rückruf ab. `SetCodegenFlags` ermöglicht es dem Profiler, die Codegenerierung für die neu kompilierte Funktion zu steuern. Wie bei allen anderen JIT-neukompilierungs Parametern gelten die Code Generierungs Flags für alle Instanzen der Funktion.  
  
 Der JIT-Compiler berücksichtigt diese Kompilierungs Flags zusammen mit anderen Flags, die von anderen Quellen angegeben werden, wenn eine Funktion kompiliert wird.  Die anderen Quellen enthalten den Debugger, globale Flags, die vom Profiler beim Start festgelegt werden, mit der [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode (mit den Werten `COR_PRF_DISABLE_INLINING` und `COR_PRF_DISABLE_OPTIMIZATIONS`) und dem [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) -Rückruf des Profilers.  Der JIT-Compiler hat Vorrang vor einer Quelle, die den geringsten Optimierungs Aufwand anfordert.  Wenn der Profiler z. b. `COR_PRF_DISABLE_INLINING` beim Start angibt, aber keine `COR_PRF_CODEGEN_DISABLE_INLINING` im [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Rückruf angibt, ist Inlining weiterhin deaktiviert.  Wenn der Profiler in `SetCodegenFlags`keine `COR_PRF_CODEGEN_DISABLE_INLINING` angibt, sondern das Inlining mithilfe des [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) -Rückrufs deaktiviert, ist Inlining deaktiviert.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerFunctionControl-Schnittstelle](icorprofilerfunctioncontrol-interface.md)
