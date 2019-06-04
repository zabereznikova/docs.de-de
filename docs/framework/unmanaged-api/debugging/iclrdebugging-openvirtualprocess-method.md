---
title: ICLRDebugging::OpenVirtualProcess-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d530f37c979a1ecddf2cb3895234aab2f7556b88
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489630"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>ICLRDebugging::OpenVirtualProcess-Methode
Ruft ab, der ICorDebugProcess-Schnittstelle, die eine common Language Runtime (CLR)-Modul in den Prozess geladenen entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleBaseAddress`  
 [in] Die Basisadresse eines Moduls in den Zielprozess. COR_E_NOT_CLR wird zurückgegeben, wenn das angegebene Modul kein CLR-Modul ist.  
  
 `pDataTarget`  
 [in] Eine Abstraktion der Daten-Ziel, die mit dem verwalteten Debugger Prozessstatus überprüfen kann. Der Debugger muss implementieren die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle. Implementieren Sie die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Schnittstelle zur Unterstützung von Szenarien, in denen die CLR, die gedebuggt wird nicht lokal auf dem Computer installiert ist.  
  
 `pLibraryProvider`  
 [in] Eine Bibliothek Rückrufschnittstelle, die es, versionsspezifische-Debugbibliotheken ermöglicht auf Nachfrage gefunden und geladen werden. Dieser Parameter ist erforderlich, wenn `ppProcess` oder `pFlags` nicht `null`.  
  
 `pMaxDebuggerSupportedVersion`  
 [in] Die höchste Version der CLR, die von diesem Debugger Debuggen kann. Sie sollten Geben Sie die Hauptversion, Nebenversion, build-Versionen aus der aktuellen CLR-Version, die dieser Debugger unterstützt und legen Sie die Revisionsnummer und 65535 liegen, um zukünftige direktes CLR Wartungsversionen zu berücksichtigen.  
  
 `riidProcess`  
 [in] Die ID der ICorDebugProcess-Schnittstelle, abgerufen werden soll. Derzeit werden nur die Werte, IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS akzeptiert.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die COM-Schnittstelle, die identifizierte `riidProcess`.  
  
 `pVersion`  
 [in, out] Die Version der CLR. Dieser Wert kann bei der Eingabe, sein `null`. Sie können auch zeigen Sie auf eine [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Struktur, in diesem Fall der Struktur `wStructVersion` Feld muss mit 0 (null) initialisiert werden.  
  
 Bei Ausgabe ist das zurückgegebene `CLR_DEBUGGING_VERSION` Struktur wird mit der die Versionsinformationen für die CLR gefüllt.  
  
 `pdwFlags`  
 [out] Nur zu Informationszwecken Flags über die angegebene Laufzeit. Finden Sie unter den [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) Thema eine Beschreibung der Flags.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pDataTarget` ist `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Rückruf einen Fehler zurück oder stellt kein gültiges Handle.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` implementiert die Schnittstellen für erforderliche Ziel für diese Version der Laufzeit nicht.|  
|CORDBG_E_NOT_CLR|Das angegebene Modul ist es sich nicht um ein CLR-Modul. Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht ermittelt werden kann, da der Arbeitsspeicher ist beschädigt, das Modul ist nicht verfügbar oder die CLR-Version ist neuer als die Shimversion.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Diese Runtime-Version wird dieses Modell Debuggen nicht unterstützt. Das Debuggen Modell wird derzeit nicht von CLR-Versionen vor .NET Framework 4 unterstützt. Die `pwszVersion` Output-Parameter wird nach dem dieser Fehler weiterhin auf den richtigen Wert festgelegt.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Die Version der CLR ist größer als die Version, die dieser Debugger unterstützt. Die `pwszVersion` Output-Parameter wird nach dem dieser Fehler weiterhin auf den richtigen Wert festgelegt.|  
|E_NO_INTERFACE|Die `riidProcess` Schnittstelle ist nicht verfügbar.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|Die `CLR_DEBUGGING_VERSION` Struktur verfügt nicht über keinen gültigen Wert für `wStructVersion`. Der einzige akzeptierte Wert zu diesem Zeitpunkt ist 0.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
