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
ms.openlocfilehash: 527e48d02d5267d6ae41214686c2e8c997d85dca
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499544"
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
 in Ein Zeiger auf eine [icorprofilerfunctioncontrol](icorprofilerfunctioncontrol-interface.md) -Schnittstelle, die der Profiler verwenden kann, um JIT-neukompilierungs Informationen für die neu kompilierte Methode bereitzustellen.  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR gibt einen `GetReJITParameters` Rückruf aus, sodass der Profiler die Parameter zum erneuten Kompilieren einer bestimmten Methode angeben kann. Der `GetReJITParameters` Rückruf wird nur einmal pro Funktion ausgegeben. die Parameter, die vom Profiler bereitgestellt werden, gelten für alle Instanzen dieser Funktion.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](icorprofilercallback4-interface.md)
- [JITCompilationStarted-Methode](icorprofilercallback-jitcompilationstarted-method.md)
- [ReJITCompilationStarted-Methode](icorprofilercallback4-rejitcompilationstarted-method.md)
