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
ms.openlocfilehash: a3d5527fc34ad7292974c005179e9d9cad210c94
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503119"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags-Methode
Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) -Enumeration fest, um die Codegenerierung für die neu kompilierte Just-in-time (JIT)-Funktion zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>Parameter  
 `flags`  
 in Ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) -Enumeration.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Profiler Ruft eine Instanz dieser Schnittstelle über den [ICorProfilerCallback4:: getrejitparameters](icorprofilercallback4-getrejitparameters-method.md) -Rückruf ab. `SetCodegenFlags`ermöglicht es dem Profiler, die Codegenerierung für die neu kompilierte Funktion zu steuern. Wie bei allen anderen JIT-neukompilierungs Parametern gelten die Code Generierungs Flags für alle Instanzen der Funktion.  
  
 Der JIT-Compiler berücksichtigt diese Kompilierungs Flags zusammen mit anderen Flags, die von anderen Quellen angegeben werden, wenn eine Funktion kompiliert wird.  Die anderen Quellen enthalten den Debugger, globale Flags, die vom Profiler beim Start festgelegt werden, mit der [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode (mit den Werten `COR_PRF_DISABLE_INLINING` und `COR_PRF_DISABLE_OPTIMIZATIONS` ) und dem [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) -Rückruf des Profilers.  Der JIT-Compiler hat Vorrang vor einer Quelle, die den geringsten Optimierungs Aufwand anfordert.  Wenn der Profiler beispielsweise `COR_PRF_DISABLE_INLINING` beim Start angibt, aber nicht `COR_PRF_CODEGEN_DISABLE_INLINING` im [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Rückruf angibt, ist Inlining weiterhin deaktiviert.  Wenn der Profiler nicht `COR_PRF_CODEGEN_DISABLE_INLINING` in angibt `SetCodegenFlags` , sondern Inlining mithilfe des [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) -Rückrufs deaktiviert, ist Inlining deaktiviert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerFunctionControl-Schnittstelle](icorprofilerfunctioncontrol-interface.md)
