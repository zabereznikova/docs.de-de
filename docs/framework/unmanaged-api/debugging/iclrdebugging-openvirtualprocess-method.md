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
ms.openlocfilehash: 2edd7f628e17c8dc6cbcbb577d06269ba8c64cb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723538"
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
 in Eine Daten Ziel Abstraktion, die es dem verwalteten Debugger ermöglicht, den Prozessstatus zu überprüfen. Der Debugger muss die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle implementieren. Sie sollten die [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle implementieren, um Szenarios zu unterstützen, in denen die CLR, die gedebuggt wird, nicht lokal auf dem Computer installiert ist.  
  
 `pLibraryProvider`  
 in Eine Bibliotheks Anbieter-Rückruf Schnittstelle, die es ermöglicht, versionsspezifische Debugbibliotheken nach Bedarf zu finden und zu laden. Dieser Parameter ist nur erforderlich, wenn `ppProcess` oder `pFlags` nicht ist `null` .  
  
 `pMaxDebuggerSupportedVersion`  
 in Die höchste Version der CLR, die von diesem Debugger debuggt werden kann. Geben Sie die Haupt-, neben-und Buildversionen aus der aktuellen CLR-Version an, die dieser Debugger unterstützt, und legen Sie die Revisionsnummer auf 65535 fest, um zukünftige direkte CLR-Wartungs Releases zu ermöglichen.  
  
 `riidProcess`  
 in Die ID der abzurufenden ICorDebugProcess-Schnittstelle. Zurzeit sind die einzigen akzeptierten Werte IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 vorgenommen Ein Zeiger auf die von identifizierte com-Schnittstelle `riidProcess` .  
  
 `pVersion`  
 [in, out] Die Version der CLR. Bei der Eingabe kann dieser Wert lauten `null` . Sie kann auch auf eine [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) Struktur verweisen. in diesem Fall muss das Feld der Struktur `wStructVersion` mit 0 (null) initialisiert werden.  
  
 Bei der Ausgabe wird die zurückgegebene `CLR_DEBUGGING_VERSION` Struktur mit den Versionsinformationen für die CLR ausgefüllt.  
  
 `pdwFlags`  
 vorgenommen Informationsflags für die angegebene Laufzeit. Eine Beschreibung der Flags finden Sie im [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) Thema.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pDataTarget` ist `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Der [iclrbinbugginglibraryprovider](iclrdebugginglibraryprovider-interface.md) -Rückruf gibt einen Fehler zurück oder stellt kein gültiges Handle bereit.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` implementiert nicht die erforderlichen Daten Ziel Schnittstellen für diese Version der Laufzeit.|  
|CORDBG_E_NOT_CLR|Das gekennzeichnete Modul ist kein CLR-Modul. Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht erkannt werden kann, weil der Arbeitsspeicher beschädigt ist, das Modul nicht verfügbar ist oder die CLR-Version höher als die Shim-Version ist.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Dieses debugingmodell wird von dieser Laufzeitversion nicht unterstützt. Derzeit wird das debugingmodell von CLR-Versionen vor dem .NET Framework 4 nicht unterstützt. Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Die CLR-Version ist größer als die Version, die dieser Debugger unterstützt. Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.|  
|E_NO_INTERFACE|Die `riidProcess` Schnittstelle ist nicht verfügbar.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|Die- `CLR_DEBUGGING_VERSION` Struktur hat keinen erkannten Wert für `wStructVersion` . Der einzige akzeptierte Wert ist zu diesem Zeitpunkt 0.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
