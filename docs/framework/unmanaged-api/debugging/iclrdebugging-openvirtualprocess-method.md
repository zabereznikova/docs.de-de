---
title: ICLRDebugging::OpenVirtualProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging.OpenVirtualProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a59d676e358b2e06ac04bdf586d8ad416445337
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>ICLRDebugging::OpenVirtualProcess-Methode
Ruft die ICorDebugProcess-Schnittstelle, die eine common Language Runtime (CLR)-Modul im Prozess geladenen entspricht.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `moduleBaseAddress`  
 [in] Die Basisadresse eines Moduls im Zielprozess. COR_E_NOT_CLR wird zurückgegeben, wenn das angegebene Modul kein CLR-Modul ist.  
  
 `pDataTarget`  
 [in] Der Abstraktion eines Daten-Ziel, das den verwalteten Debugger Prozessstatus überprüfen kann. Der Debugger muss implementieren die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle. Implementieren Sie die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) -Schnittstelle zur Unterstützung von Szenarien, in denen die CLR, die gedebuggt wird ist nicht lokal auf dem Computer installiert.  
  
 `pLibraryProvider`  
 [in] Eine Bibliothek Rückrufschnittstelle, die es ermöglicht, versionsspezifische-Debugbibliotheken Nachfrage gefunden und geladen werden. Dieser Parameter ist erforderlich, wenn nur `ppProcess` oder `pFlags` nicht `null`.  
  
 `pMaxDebuggerSupportedVersion`  
 [in] Die höchste Version der CLR, die diesen Debugger Debuggen kann. Sie sollten geben Haupt-oder Nebenversion, und Buildversionen aus der aktuellen CLR-Version, die dieser Debugger unterstützt, und legen die Revisionsnummer auf 65.535 ein, um zukünftige direktes CLR Wartung Versionen aufzunehmen.  
  
 `riidProcess`  
 [in] Die ID der ICorDebugProcess-Schnittstelle zum Abrufen. Aktuell sind die einzigen zulässigen Werte IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS akzeptiert.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die COM-Schnittstelle, die identifizierte `riidProcess`.  
  
 `pVersion`  
 [in, out] Die Version der CLR. Dieser Wert kann bei der Eingabe, sein `null`. Es kann auch zeigen Sie auf eine [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Struktur, in diesem Fall der Struktur `wStructVersion` -Feld auf 0 (null) initialisiert werden muss.  
  
 Bei der Ausgabe der zurückgegebenen `CLR_DEBUGGING_VERSION` Struktur wird mit der die Versionsinformationen für die CLR gefüllt.  
  
 `pdwFlags`  
 [out] Nur zu Informationszwecken Flags zu dem angegebenen Common Language Runtime. Finden Sie unter der [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) Thema eine Beschreibung der Flags.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pDataTarget` ist `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Rückruf einen Fehler zurück, oder ein gültiges Handle werden nicht bereitgestellt.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget`implementiert nicht die erforderlichen Daten Ziel-Schnittstellen für diese Version der Laufzeit.|  
|CORDBG_E_NOT_CLR|Das angegebene Modul ist kein CLR-Modul. Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht ermittelt werden kann, da der Arbeitsspeicher ist beschädigt, das Modul ist nicht verfügbar oder die CLR-Version ist neuer als die Shimversion.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Diese Version der Common Language Runtime unterstützt diese debuggingmodell nicht. Die debuggingmodell wird derzeit nicht unterstützt, von CLR-Versionen vor der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Die `pwszVersion` Output-Parameter nach diesem Fehler noch auf den richtigen Wert festgelegt ist.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Die Version der CLR ist größer als die Version, die dieser Debugger unterstützt. Die `pwszVersion` Output-Parameter nach diesem Fehler noch auf den richtigen Wert festgelegt ist.|  
|E_NO_INTERFACE|Die `riidProcess` Schnittstelle ist nicht verfügbar.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|Die `CLR_DEBUGGING_VERSION` Struktur verfügt nicht über einen gültigen Wert für `wStructVersion`. Der einzige akzeptierte Wert zu diesem Zeitpunkt ist 0.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
