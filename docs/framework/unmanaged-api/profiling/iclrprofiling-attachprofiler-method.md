---
title: ICLRProfiling::AttachProfiler-Methode
ms.date: 03/30/2017
api_name:
- IClrProfiling.AttachProfiler Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- IClrProfiling::AttachProfiler
helpviewer_keywords:
- AttachProfiler method [.NET Framework profiling]
- IClrProfiling::AttachProfiler method [.NET Framework profiling]
ms.assetid: 535a6839-c443-405b-a6f4-e2af90725d5b
topic_type:
- apiref
ms.openlocfilehash: 25c208c98802be540bde7532c53798e6f7b35446
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445949"
---
# <a name="iclrprofilingattachprofiler-method"></a>ICLRProfiling::AttachProfiler-Methode
Fügt den angegebenen Profiler an den angegebenen Prozess an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AttachProfiler(  
  [in] DWORD dwProfileeProcessID,  
  [in] DWORD dwMillisecondsMax,                     // optional  
  [in] const CLSID * pClsidProfiler,  
  [in] LPCWSTR wszProfilerPath,                     // optional  
  [in] size_is(cbClientData)] void * pvClientData,  // optional  
  [in] UINT cbClientData);                          // optional  
```  
  
## <a name="parameters"></a>Parameter  
 `dwProfileeProcessID`  
 [in] Die Prozess-ID des Prozesses, an den der Profiler angefügt werden soll. Auf einem 64-Bit-Computer muss die Bitanzahl des profilierten Prozesses der Bitanzahl des Triggerprozesses entsprechen, von dem `AttachProfiler` aufgerufen wird. Wenn das Benutzerkonto, unter dem `AttachProfiler` aufgerufen wird, über Administratorrechte verfügt, kann der Zielprozess jeder Prozess im System sein. Andernfalls muss der Zielprozess im Besitz desselben Benutzerkontos sein.  
  
 `dwMillisecondsMax`  
 [in] Die Dauer in Millisekunden, bis `AttachProfiler` abgeschlossen sein soll. Der Triggerprozess sollte ein Timeout übergeben, von dem bekannt ist, dass es für den Abschluss der Initialisierung des betreffenden Profilers ausreicht.  
  
 `pClsidProfiler`  
 [in] Ein Zeiger auf die CLSID des Profilers, der geladen werden soll. Der Triggerprozess kann diesen Arbeitsspeicher wiederverwenden, nachdem `AttachProfiler` beendet wurde.  
  
 `wszProfilerPath`  
 [in] Der vollständige Pfad zur DLL-Datei des Profilers, der geladen werden soll. Diese Zeichenfolge darf, einschließlich des NULL-Abschlusszeichens, nicht mehr als 260 Zeichen enthalten. Wenn `wszProfilerPath` gleich NULL oder eine leere Zeichenfolge ist, versucht die Common Language Runtime (CLR), den Speicherort der DLL-Datei des Profilers zu ermitteln, indem sie in der Registrierung nach der CLSID von diesem `pClsidProfiler` sucht.  
  
 `pvClientData`  
 [in] A pointer to data to be passed to the profiler by the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method. Der Triggerprozess kann diesen Arbeitsspeicher wiederverwenden, nachdem `AttachProfiler` beendet wurde. Wenn `pvClientData` gleich NULL ist, muss `cbClientData` gleich 0 (null) sein.  
  
 `cbClientData`  
 [in] Die Größe der Daten in Bytes, auf die `pvClientData` verweist.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden HRESULTs zurück.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der angegebene Profiler wurde erfolgreich an den Zielprozess angefügt.|  
|CORPROF_E_PROFILER_ALREADY_ACTIVE|Es ist bereits ein Profiler aktiv, oder es wird bereits ein Profiler an den Zielprozess angefügt.|  
|CORPROF_E_PROFILER_NOT_ATTACHABLE|Anfügen wird vom angegebenen Profiler nicht unterstützt. Der Triggerprozess versucht möglicherweise, einen anderen Profiler anzufügen.|  
|CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER|Das Anfügen eines Profilers kann nicht angefordert werden, da die Version des Zielprozesses nicht mit dem aktuellen Prozess kompatibel ist, von dem `AttachProfiler` aufgerufen wird.|  
|HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)|Der Benutzer des Triggerprozesses hat keinen Zugriff auf den Zielprozess.|  
|HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)|Der Benutzer des Triggerprozesses hat nicht die erforderlichen Rechte, um einen Profiler an den angegebenen Zielprozess anzufügen. Das Anwendungsereignisprotokoll enthält möglicherweise weitere Informationen.|  
|CORPROF_E_IPC_FAILED|Fehler bei der Kommunikation mit dem Zielprozess. Dies geschieht häufig, wenn der Zielprozess heruntergefahren wurde.|  
|HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)|Der Zielprozess ist nicht vorhanden oder führt keine CLR aus, die Anfügen unterstützt. Dies kann darauf hinweisen, dass die CLR seit dem Aufruf von der Runtime-Enumerationsmethode entladen wurde.|  
|HRESULT_FROM_WIN32(ERROR_TIMEOUT)|Das Timeout ist abgelaufen, ohne dass mit dem Laden des Profilers begonnen wurde. Sie können den Anfügevorgang wiederholen. Timeouts treten auf, wenn ein Finalizer im Zielprozess für einen längeren Zeitraum als durch den Timeoutwert angegeben ausgeführt wird.|  
|E_INVALIDARG|Mindestens ein Parameter hat ungültige Werte.|  
|E_FAIL|Ein anderer, nicht angegebener Fehler ist aufgetreten.|  
|Sonstige Fehlercodes|If the profiler’s [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method returns an HRESULT that indicates failure, `AttachProfiler` returns that same HRESULT. In diesem Fall wird E_NOTIMPL in CORPROF_E_PROFILER_NOT_ATTACHABLE konvertiert.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="memory-management"></a>Speicherverwaltung  
 Entsprechend den COM-Konventionen ist der Aufrufer von `AttachProfiler` (z. B. der vom Profilerentwickler erstellte Triggercode) für das Zuordnen und Freigeben des Arbeitsspeichers für die Daten zuständig, auf die der `pvClientData`-Parameter verweist. Wenn die CLR den `AttachProfiler`-Aufruf ausführt, erstellt sie eine Kopie des Arbeitsspeichers, auf den `pvClientData` verweist, und sie überträgt die Kopie an den Zielprozess. Wenn die CLR im Zielprozess ihre eigene Kopie des `pvClientData`-Blocks empfängt, übergibt sie den Block über die `InitializeForAttach`-Methode an den Profiler, und dann gibt sie ihre Kopie der `pvClientData`-Blocks aus dem Zielprozess frei.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
