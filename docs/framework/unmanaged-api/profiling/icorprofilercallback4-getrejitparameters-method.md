---
title: ICorProfilerCallback4::GetReJITParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: d81d7275d197de1dfc99b135377459f509c2651f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439437"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>ICorProfilerCallback4::GetReJITParameters-Methode
Ermöglicht dem Codeprofiler das Festlegen von Flags für die Alternative Codegenerierung für einen neuen neu kompilierten Methoden Text.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 in Das Modul, das die Methode enthält, für die die CLR JIT-neukompilierungs Parameter benötigt.  
  
 `methodId`  
 in Der `MethodDef` der Methode, für die die CLR JIT-neukompilierungs Parameter benötigt.  
  
 `pFunctionControl`  
 in Ein Zeiger auf eine [icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) -Schnittstelle, die der Profiler verwenden kann, um JIT-neukompilierungs Informationen für die neu kompilierte Methode bereitzustellen.  
  
## <a name="remarks"></a>Hinweise  
 Die CLR gibt einen `GetReJITParameters` Rückruf aus, sodass der Profiler die Parameter zum erneuten Kompilieren einer bestimmten Methode angeben kann. Der `GetReJITParameters` Rückruf wird nur einmal pro Funktion ausgegeben. die Parameter, die vom Profiler bereitgestellt werden, gelten für alle Instanzen dieser Funktion.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [ReJITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
