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
ms.openlocfilehash: 585b3d605d0df9169c12ca10198846ec0a7fe6d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793611"
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
  
## <a name="parameters"></a>Parameters  
 `moduleBaseAddress`  
 in Die Basisadresse eines Moduls im Ziel Prozess. COR_E_NOT_CLR wird zurückgegeben, wenn das angegebene Modul kein CLR-Modul ist.  
  
 `pDataTarget`  
 in Eine Daten Ziel Abstraktion, die es dem verwalteten Debugger ermöglicht, den Prozessstatus zu überprüfen. Der Debugger muss die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle implementieren. Sie sollten die [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle implementieren, um Szenarios zu unterstützen, in denen die CLR, die gedebuggt wird, nicht lokal auf dem Computer installiert ist.  
  
 `pLibraryProvider`  
 in Eine Bibliotheks Anbieter-Rückruf Schnittstelle, die es ermöglicht, versionsspezifische Debugbibliotheken nach Bedarf zu finden und zu laden. Dieser Parameter ist nur erforderlich, wenn `ppProcess` oder `pFlags` nicht `null`ist.  
  
 `pMaxDebuggerSupportedVersion`  
 in Die höchste Version der CLR, die von diesem Debugger debuggt werden kann. Geben Sie die Haupt-, neben-und Buildversionen aus der aktuellen CLR-Version an, die dieser Debugger unterstützt, und legen Sie die Revisionsnummer auf 65535 fest, um zukünftige direkte CLR-Wartungs Releases zu ermöglichen.  
  
 `riidProcess`  
 in Die ID der abzurufenden ICorDebugProcess-Schnittstelle. Zurzeit sind die einzigen akzeptierten Werte IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 vorgenommen Ein Zeiger auf die COM-Schnittstelle, die durch `riidProcess`identifiziert wird.  
  
 `pVersion`  
 [in, out] Die Version der CLR. Bei der Eingabe kann dieser Wert `null`werden. Sie kann auch auf eine [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) Struktur verweisen. in diesem Fall muss das `wStructVersion` Feld der Struktur mit 0 (null) initialisiert werden.  
  
 Bei der Ausgabe wird die zurückgegebene `CLR_DEBUGGING_VERSION` Struktur mit den Versionsinformationen für die CLR ausgefüllt.  
  
 `pdwFlags`  
 vorgenommen Informationsflags für die angegebene Laufzeit. Eine Beschreibung der Flags finden Sie im [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) Thema.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde abgeschlossen.|  
|E_POINTER|`pDataTarget` ist `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Der [iclrbinbugginglibraryprovider](iclrdebugginglibraryprovider-interface.md) -Rückruf gibt einen Fehler zurück oder stellt kein gültiges Handle bereit.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` implementiert die erforderlichen Daten Ziel Schnittstellen für diese Version der Laufzeit nicht.|  
|CORDBG_E_NOT_CLR|Das gekennzeichnete Modul ist kein CLR-Modul. Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht erkannt werden kann, weil der Arbeitsspeicher beschädigt ist, das Modul nicht verfügbar ist oder die CLR-Version höher als die Shim-Version ist.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Dieses debugingmodell wird von dieser Laufzeitversion nicht unterstützt. Derzeit wird das debugingmodell von CLR-Versionen vor dem .NET Framework 4 nicht unterstützt. Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Die CLR-Version ist größer als die Version, die dieser Debugger unterstützt. Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.|  
|E_NO_INTERFACE|Die `riidProcess`-Schnittstelle ist nicht verfügbar.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|Die `CLR_DEBUGGING_VERSION` Struktur hat keinen erkannten Wert für `wStructVersion`. Der einzige akzeptierte Wert ist zu diesem Zeitpunkt 0.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
