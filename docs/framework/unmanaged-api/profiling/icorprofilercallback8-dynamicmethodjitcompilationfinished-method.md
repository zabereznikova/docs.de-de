---
title: ICorProfilerCallback8::D ynamicmethodjitcompilationbeendete-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 554cc93de934061e87322c7557e05545e5e7bc62
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499076"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::D ynamicmethodjitcompilationbeendete-Methode
[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]  
  
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
Der Bezeichner der in-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.

[in] `hrStatus` Ein Wert, der angibt, ob die JIT-Kompilierung erfolgreich war.

[in] `fIsSafeToBlock` 
 `true` , um anzugeben, dass das blockieren möglicherweise dazu führt, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung den Lauf der Laufzeit nicht beeinträchtigt.  

## <a name="remarks"></a>Bemerkungen  

Dieser Rückruf wird ausgelöst, wenn die JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde. Dies schließt verschiedene IL-Stub-und LCG-Methoden ein. Ziel ist es, Profiler-Writern ausreichend Informationen bereitzustellen, um die kompilierte Methode für Benutzer zu identifizieren.

> [!NOTE]
> `functionId`Werte können nicht verwendet werden, um Ihre Metadatentoken aufzulösen, da dynamische Methoden keine Metadaten aufweisen.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8-Schnittstelle](icorprofilercallback8-interface.md)
