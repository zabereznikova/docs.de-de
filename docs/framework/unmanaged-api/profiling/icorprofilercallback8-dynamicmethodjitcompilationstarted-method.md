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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationStarted-Methode
[Wird nur in .NET Framework 4.7 und höheren Versionen unterstützt]  
  
Benachrichtigt den Profiler, wenn JIT-Kompilierung einer dynamischen Methode gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a>Parameter  
[in] `functionId`  
Der Bezeichner der in-Memory-Funktion, die für die JIT-Kompilierung gestartet wird.   

[in] `fIsSafeToBlock`   
`true` um anzugeben, dass blockiert die Common Language Runtime zu warten, bis der aufrufende Thread von diesem Rückruf zurückgegeben bewirken kann. `false` um anzugeben, dass blockiert die Ausführung von der Laufzeit nicht beeinflusst.  

[in] `pILHeader`    
Ein Zeiger auf das erste Byte des IL-Headers für die Methode.   

[in] `cbILHeader`    
Die Anzahl der Bytes im IL-Header. 

## <a name="remarks"></a>Hinweise  

Dieser Rückruf wird ausgelöst, wenn eine dynamische Methode JIT-kompiliert wird. Dies umfasst verschiedene IL-Stubs und LCG-Methoden. Das Ziel besteht Profiler Writer genügend Informationen zum Identifizieren Sie der kompilierten Methode für Benutzer bereitstellen.

> [!NOTE]
> `functionId` Werte können nicht zum Auflösen in ihren Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten aufweisen.

Die `pILHeader` -Zeiger ist nur gültig, während des Rückrufs.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [DynamicMethodJITCompilationFinished-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [ICorProfilerCallback8-Schnittstelle](icorprofilercallback8-interface.md)
