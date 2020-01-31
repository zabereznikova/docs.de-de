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
ms.openlocfilehash: 66195ea9df4c8e9ce847b38f7d020a3bebffcd37
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865180"
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError-Methode
Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) einen Fehler im neukompilierungs Prozess festgestellt hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parameters  
 `moduleID`  
 in Die `ModuleID`, in der der fehlgeschlagene neukompilierungs Versuch erfolgte.  
  
 `methodId`  
 in Der `MethodDef` der Methode, für die der fehlgeschlagene neukompilierungs Versuch durchgeführt wurde.  
  
 `functionId`  
 in Die Funktions Instanz, die erneut kompiliert oder für die Neukompilierung markiert wird. Dieser Wert kann `NULL` sein, wenn der Fehler nicht pro Instanziierung, sondern pro Methode aufgetreten ist (z. b. wenn der Profiler ein ungültiges Metadatentoken für die neu zu kompilierende Methode angegeben hat).  
  
 `hrStatus`  
 in Ein HRESULT, das die Art des Fehlers angibt. Eine Liste der Werte finden Sie im Abschnitt "Status-HRESULTs".  
  
## <a name="return-value"></a>Rückgabewert  
 Rückgabewerte von diesem Rückruf werden ignoriert.  
  
## <a name="status-hresults"></a>Status HRESULTS  
  
|Statusarray HRESULT|Beschreibung|  
|--------------------------|-----------------|  
|E_INVALIDARG|Die `moduleID` oder `methodDef` Token ist `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Das Modul ist noch nicht vollständig geladen, oder es wird gerade entladen.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Das angegebene Modul wurde dynamisch generiert (z. b. durch `Reflection.Emit`) und wird daher von dieser Methode nicht unterstützt.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Die-Methode wird in einer entladbaren Assembly instanziiert und kann daher nicht erneut kompiliert werden. Beachten Sie, dass Typen und Funktionen, die in einem nicht Reflektionskontext (z. b. `List<MyCollectibleStruct>`) definiert sind, in einer entladbaren Assembly instanziiert werden können.|  
|E_OUTOFMEMORY|Die CLR hatte beim Versuch, die angegebene Methode für die JIT-Neukompilierung zu markieren, nicht genügend Arbeitsspeicher.|  
|Sonstige|Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben. Wenn beispielsweise ein Systemaufrufe zum Ändern des Zugriffs Schutzes einer Arbeitsspeicher Seite fehlschlägt, wird der Fehler des Betriebssystems angezeigt.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](icorprofilercallback4-interface.md)
