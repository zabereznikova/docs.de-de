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
ms.openlocfilehash: e0cd68f5a15bbd8942f0dc889ecb74b7fde00d30
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502320"
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError-Methode
Benachrichtigt den Profiler an, der just-in-Time-Compiler (JIT) ein Fehler im Prozess eine Neukompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Die `ModuleID` in dem der Fehler Neukompilierung versucht wurde.  
  
 `methodId`  
 [in] Die `MethodDef` der Methode auf dem die fehlgeschlagenen Neukompilierung versucht wurde.  
  
 `functionId`  
 [in] Die Funktionsinstanz, die erneut kompilierte oder für eine Neukompilierung. Dieser Wert möglicherweise `NULL` wenn pro pro-Methode anstelle einer pro Instanziierung (z. B., wenn der Profiler ein ungültiges Metadatentoken für die Methode neu kompiliert werden angegeben), der der Fehler aufgetreten ist.  
  
 `hrStatus`  
 [in] Ein HRESULT, der die Art des Fehlers angibt. Finden Sie im Abschnitt "Status HRESULTS" eine Liste von Werten aus.  
  
## <a name="return-value"></a>Rückgabewert  
 Rückgabewerte von diesem Rückruf werden ignoriert.  
  
## <a name="status-hresults"></a>Status HRESULTS  
  
|Statusarray HRESULT|Beschreibung|  
|--------------------------|-----------------|  
|E_INVALIDARG|Die `moduleID` oder `methodDef` Token `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Das Modul ist noch nicht vollständig geladen, oder es wird gerade entladen.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Das angegebene Modul wurde dynamisch generiert (z. B. durch `Reflection.Emit`), und wird daher von dieser Methode nicht unterstützt.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Die Methode in einer entladbaren Assembly instanziiert wird, und kann daher nicht neu kompiliert werden. Beachten Sie, die von Typen und Funktionen, die in einem nicht-Reflection-Kontext definiert (z. B. `List<MyCollectibleStruct>`) in einer entladbaren Assembly instanziiert werden kann.|  
|E_OUTOFMEMORY|Die CLR war nicht genügend Arbeitsspeicher beim Versuch, die die angegebene Methode für die JIT-Neukompilierung zu markieren.|  
|Andere|Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben. Wenn ein Systemaufruf zum Ändern des Zugriffsschutz einer Seite des Speichers ein Fehler auftritt, wird z. B. Fehlerprotokoll des Betriebssystems angezeigt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
