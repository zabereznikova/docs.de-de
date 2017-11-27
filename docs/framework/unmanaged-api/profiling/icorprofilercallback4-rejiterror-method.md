---
title: ICorProfilerCallback4::ReJITError-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITError
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8b1f3c5b206b2e6a108e784a206d597b69fd662
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|Sonstige|Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben. Beispielsweise wird ein Systemaufruf zum Ändern des Zugriffsschutz einer Seite des Speichers ein Fehler auftritt, der Betriebssystemfehler angezeigt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
