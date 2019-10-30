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
ms.openlocfilehash: cd43dce995c2bc9a45a0c8134a91b20cb1dec26e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111432"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>ICLRDebugging::OpenVirtualProcess-Methode
Ruft die ICorDebugProcess-Schnittstelle ab, die einem Common Language Runtime (CLR)-Modul entspricht, das in den Prozess geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Die Basisadresse eines Moduls im Ziel Prozess. COR_E_NOT_CLR wird zurückgegeben, wenn das angegebene Modul kein CLR-Modul ist.  
  
 `pDataTarget`  
 in Eine Daten Ziel Abstraktion, die es dem verwalteten Debugger ermöglicht, den Prozessstatus zu überprüfen. Der Debugger muss die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) -Schnittstelle implementieren. Sie sollten die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) -Schnittstelle implementieren, um Szenarios zu unterstützen, in denen die CLR, die gedebuggt wird, nicht lokal auf dem Computer installiert ist.  
  
 `pLibraryProvider`  
 in Eine Bibliotheks Anbieter-Rückruf Schnittstelle, die es ermöglicht, versionsspezifische Debugbibliotheken nach Bedarf zu finden und zu laden. Dieser Parameter ist nur erforderlich, wenn `ppProcess` oder `pFlags` nicht `null`ist.  
  
 `pMaxDebuggerSupportedVersion`  
 in Die höchste Version der CLR, die von diesem Debugger debuggt werden kann. Geben Sie die Haupt-, neben-und Buildversionen aus der aktuellen CLR-Version an, die dieser Debugger unterstützt, und legen Sie die Revisionsnummer auf 65535 fest, um zukünftige direkte CLR-Wartungs Releases zu ermöglichen.  
  
 `riidProcess`  
 in Die ID der abzurufenden ICorDebugProcess-Schnittstelle. Derzeit sind die einzigen akzeptierten Werte IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 vorgenommen Ein Zeiger auf die COM-Schnittstelle, die durch `riidProcess`identifiziert wird.  
  
 `pVersion`  
 [in, out] Die Version der CLR. Bei der Eingabe kann dieser Wert `null`werden. Sie kann auch auf eine [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) -Struktur verweisen. in diesem Fall muss das `wStructVersion` Feld der Struktur mit 0 (null) initialisiert werden.  
  
 Bei der Ausgabe wird die zurückgegebene `CLR_DEBUGGING_VERSION` Struktur mit den Versionsinformationen für die CLR ausgefüllt.  
  
 `pdwFlags`  
 vorgenommen Informationsflags für die angegebene Laufzeit. Eine Beschreibung der Flags finden Sie im Thema [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) .  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pDataTarget` ist `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Der [iclrbinbugginglibraryprovider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) -Rückruf gibt einen Fehler zurück oder stellt kein gültiges Handle bereit.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` implementiert die erforderlichen Daten Ziel Schnittstellen für diese Version der Laufzeit nicht.|  
|CORDBG_E_NOT_CLR|Das gekennzeichnete Modul ist kein CLR-Modul. Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht erkannt werden kann, weil der Arbeitsspeicher beschädigt ist, das Modul nicht verfügbar ist oder die CLR-Version höher als die Shim-Version ist.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Dieses debugingmodell wird von dieser Laufzeitversion nicht unterstützt. Derzeit wird das debugingmodell von CLR-Versionen vor dem .NET Framework 4 nicht unterstützt. Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Die CLR-Version ist größer als die Version, die dieser Debugger unterstützt. Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.|  
|E_NO_INTERFACE|Die `riidProcess`-Schnittstelle ist nicht verfügbar.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|Die `CLR_DEBUGGING_VERSION` Struktur hat keinen erkannten Wert für `wStructVersion`. Der einzige akzeptierte Wert ist zu diesem Zeitpunkt 0.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
