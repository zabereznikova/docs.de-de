---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175108"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationFinished-Methode
[Unterstützt in .NET Framework 4.7 und neueren Versionen]  
  
Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a>Parameter  
[in] `functionId`  
Der Bezeichner der In-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.

[in] `hrStatus` Ein Wert, der angibt, ob die JIT-Kompilierung erfolgreich war.

[in] `fIsSafeToBlock` , um anzugeben, dass das Blockieren dazu führen kann, dass die Laufzeit darauf wartet, dass der aufrufende Thread von diesem Rückruf 
 `true` zurückkehrt. `false` , um anzugeben, dass die Blockierung den Betrieb der Laufzeit nicht beeinträchtigt.  

## <a name="remarks"></a>Bemerkungen  

Dieser Rückruf wird ausgelöst, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen ist. Dazu gehören verschiedene IL-Stubs und LCG-Methoden. Ziel ist es, Profilerautoren genügend Informationen zur Verfügung zu stellen, um die kompilierte Methode für Benutzer zu identifizieren.

> [!NOTE]
> `functionId`Werte können nicht zum Auflösen in ihre Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten haben.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8-Schnittstelle](icorprofilercallback8-interface.md)
