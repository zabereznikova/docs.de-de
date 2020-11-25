---
title: ICorProfilerCallback8::D ynamicmethodjitcompilationstarted-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 46a25fc6e9119481f728275e0569429cc6c46dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725429"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::D ynamicmethodjitcompilationstarted-Methode

[Wird in der .NET Framework 4,7 und höheren Versionen unterstützt]  
  
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
Der Bezeichner der in-Memory-Funktion, für die die JIT-Kompilierung gestartet wird.

[in] `fIsSafeToBlock` 
 `true` , um anzugeben, dass das blockieren möglicherweise dazu führt, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung den Lauf der Laufzeit nicht beeinträchtigt.  

[in] `pILHeader` Ein Zeiger auf das erste Byte des Il-Headers der Methode.

[in] `cbILHeader` Die Anzahl der Bytes im Il-Header.

## <a name="remarks"></a>Hinweise  

Dieser Rückruf wird ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird. Dies schließt verschiedene IL-Stub-und LCG-Methoden ein. Ziel ist es, Profiler-Writern ausreichend Informationen bereitzustellen, um die kompilierte Methode für Benutzer zu identifizieren.

> [!NOTE]
> `functionId` Werte können nicht verwendet werden, um Ihre Metadatentoken aufzulösen, da dynamische Methoden keine Metadaten aufweisen.

Der `pILHeader` Zeiger ist nur während des Rückrufs gültig.

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [DynamicMethodJITCompilationStarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback8-Schnittstelle](icorprofilercallback8-interface.md)
