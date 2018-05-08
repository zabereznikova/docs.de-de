---
title: ICorProfilerCallback4::ReJITError-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec6472a33c49d9345793d73ac2f78f8896dc218b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError-Methode
Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler einen Fehler bei der Neukompilierung aufgetreten.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Die `ModuleID` in dem die fehlerhaften Neukompilierung versucht wurde.  
  
 `methodId`  
 [in] Die `MethodDef` der Methode, die auf dem die fehlerhaften Neukompilierung versucht wurde.  
  
 `functionId`  
 [in] Die Funktionsinstanz, die erneut kompilierte oder für das neu kompiliert wird. Dieser Wert möglicherweise `NULL` Wenn regelmäßig jede Methode anstelle einer pro-Instanziierung-Basis (beispielsweise, wenn der Profiler eine ungültige Metadatentoken für die Methode für die erneute Kompilierung angegeben), der der Fehler aufgetreten ist.  
  
 `hrStatus`  
 [in] Ein HRESULT, das die Art des Fehlers angibt. Finden Sie im Abschnitt "Status HRESULTS" eine Liste von Werten aus.  
  
## <a name="return-value"></a>Rückgabewert  
 Rückgabewerte von diesem Rückruf werden ignoriert.  
  
## <a name="status-hresults"></a>Status HRESULTS  
  
|Statusarray HRESULT|Beschreibung|  
|--------------------------|-----------------|  
|E_INVALIDARG|Die `moduleID` oder `methodDef` Token ist `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Das Modul ist noch nicht vollständig geladen, oder es wird gerade entladen.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Das angegebene Modul wurde dynamisch generiert (z. B. durch `Reflection.Emit`), und wird daher von dieser Methode nicht unterstützt.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Die Methode in einer entladbare Assembly instanziiert wird, und kann daher nicht neu kompiliert werden. Beachten Sie, die von Typen und Funktionen, die in einen Reflektionskontext definiert (z. B. `List<MyCollectibleStruct>`) in einer entladbare Assembly instanziiert werden kann.|  
|E_OUTOFMEMORY|Die CLR den Puffertypen nicht genügend Arbeitsspeicher auf die angegebene Methode für die JIT-Neukompilierung zu markieren.|  
|Andere|Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben. Beispielsweise wird ein Systemaufruf zum Ändern des Zugriffsschutz einer Seite des Speichers ein Fehler auftritt, der Betriebssystemfehler angezeigt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
