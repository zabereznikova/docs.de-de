---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177045"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationStarted-Methode
[Unterstützt in .NET Framework 4.7 und neueren Versionen]  
  
Benachrichtigt den Profiler, wenn die JIT-Kompilierung einer dynamischen Methode gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a>Parameter  
[in] `functionId`  
Der Bezeichner der In-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.

[in] `fIsSafeToBlock` , um anzugeben, dass das Blockieren dazu führen kann, dass die Laufzeit darauf wartet, dass der aufrufende Thread von diesem Rückruf 
 `true` zurückkehrt. `false` , um anzugeben, dass die Blockierung den Betrieb der Laufzeit nicht beeinträchtigt.  

[in] `pILHeader` Ein Zeiger auf das erste Byte des IL-Headers der Methode.

[in] `cbILHeader` Die Anzahl der Bytes im IL-Header.

## <a name="remarks"></a>Bemerkungen  

Dieser Rückruf wird ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird. Dazu gehören verschiedene IL-Stubs und LCG-Methoden. Ziel ist es, Profilerautoren genügend Informationen zur Verfügung zu stellen, um die kompilierte Methode für Benutzer zu identifizieren.

> [!NOTE]
> `functionId`Werte können nicht zum Auflösen in ihre Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten haben.

Der `pILHeader` Zeiger ist nur während des Rückrufs gültig.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback8-Schnittstelle](icorprofilercallback8-interface.md)
