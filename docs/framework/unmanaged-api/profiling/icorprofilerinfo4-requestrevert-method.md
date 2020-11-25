---
title: ICorProfilerInfo4::RequestRevert-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestRevert
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestRevert
helpviewer_keywords:
- RequestRevert method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestRevert method [.NET Framework profiling]
ms.assetid: 70261da5-5933-4e25-9de0-ddf51cba56cc
topic_type:
- apiref
ms.openlocfilehash: b80de5e0e03f6b3a424ac59a099e361dd6c50c86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733814"
---
# <a name="icorprofilerinfo4requestrevert-method"></a>ICorProfilerInfo4::RequestRevert-Methode

Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RequestRevert (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[],  
   [out, size_is(cFunctions)]  HRESULT status[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `cFunctions`  
 [in] Die Anzahl der zurückzusetzenden Funktionen.  
  
 `moduleIds`  
 [in] Gibt den `moduleId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die zurückzusetzenden Funktionen identifiziert werden.  
  
 `methodIds`  
 [in] Gibt den `methodId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die zurückzusetzenden Funktionen identifiziert werden.  
  
 `status`  
 [out] Ein Array von HRESULTs, das im Abschnitt "Status HRESULTs" weiter unten in diesem Thema aufgeführt ist. Jedes HRESULT gibt das erfolgreiche oder fehlgeschlagene Zurücksetzen der einzelnen Funktionen an, die in den parallelen Arrays `moduleIds` und `methodIds` angegeben sind.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Es wurde versucht, alle Anforderungen zurückzusetzen. Das zurückgegebene Statusarray muss jedoch überprüft werden, um zu bestimmen, welche Funktionen erfolgreich zurücksetzt wurden.|  
|CORPROF_E_CALLBACK4_REQUIRED|Der Profiler muss die [ICorProfilerCallback4](icorprofilercallback4-interface.md) -Schnittstelle implementieren, damit dieser-Befehl unterstützt wird.|  
|CORPROF_E_REJIT_NOT_ENABLED|Die JIT-Neukompilierung wurde nicht aktiviert. Sie müssen die JIT-Neukompilierung während der Initialisierung aktivieren, indem Sie die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um das-Flag festzulegen `COR_PRF_ENABLE_REJIT` .|  
|E_INVALIDARG|`cFunctions` ist 0, oder `moduleIds` oder `methodIds` ist `NULL`.|  
|E_OUTOFMEMORY|Die CLR konnte die Anforderung nicht abschließen, da nicht genügend Arbeitsspeicher vorhanden war.|  
  
## <a name="status-hresults"></a>Status HRESULTS  
  
|Statusarray HRESULT|BESCHREIBUNG|  
|--------------------------|-----------------|  
|S_OK|Die entsprechende Funktion wurde erfolgreich zurückgesetzt.|  
|E_INVALIDARG|Der `moduleID`-Parameter oder der `methodDef`-Parameter ist `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Das Modul ist noch nicht vollständig geladen, oder es wird gerade entladen.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Das angegebene Modul wurde dynamisch generiert (z. B. durch `Reflection.Emit`). Daher wird es von dieser Methode nicht unterstützt.|  
|CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND|Die angegebene Funktion konnte von der CLR nicht zurückgesetzt werden, da keine entsprechende aktive Neukompilierungsanforderung gefunden wurde. Entweder wurde die Neukompilierung nie angefordert, oder die Funktion wurde bereits zurückgesetzt.|  
|Sonstiges|Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben. Wenn beispielsweise ein Systemaufruf zum Ändern des Zugriffsschutz einer Speicherseite fehlschlägt, wird der Betriebssystemfehler angezeigt.|  
  
## <a name="remarks"></a>Hinweise  

 Beim nächsten Aufruf einer der zurückgesetzten Funktionsinstanzen werden die ursprünglichen Versionen der Funktionen ausgeführt. Wenn eine Funktion bereits ausgeführt wird, wird die Ausführung der aktiven Version abgeschlossen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
