---
title: ICLRDebuggingLibraryProvider::ProvideLibrary-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9cac9e00c8cb6a13e2acc62b5f314b7bc0cf9e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629119"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary-Methode
Ruft eine Bibliotheksanbieter-Rückrufschnittstelle, die es common Language Runtime (CLR) hängt von der Version Debugbibliotheken ermöglicht zu suchen und zu laden, auf Anforderung ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwszFilename`  
 [in] Der Name des Moduls, das angefordert wird.  
  
 `dwTimestamp`  
 [in] Die Datums-/ Zeitstempel im COFF-Dateiheader der PE-Dateien gespeichert.  
  
 `pLibraryProvider`  
 [in] Die `SizeOfImage` Feld in der optionalen COFF-Dateiheader der PE-Dateien gespeichert.  
  
 `hModule`  
 [out] Das Handle für das angeforderte Modul.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 `ProvideLibrary` ermöglicht dem Debugger, Module bereitzustellen, die für das Debuggen von bestimmten CLR-Dateien wie z. B. "mscordbi.dll" und mscordacwks.dll erforderlich sind. Die Modul-Handles zu haben, gültig bleiben, bis ein Aufruf der [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) -Methode gibt an, dass sie freigegeben werden können, die an diesem Punkt wird es der Verantwortung des Aufrufers, die Handles freizugeben.  
  
 Der Debugger können Sie alle verfügbaren Verfahren suchen oder die debugging-Modul bereitzustellen.  
  
> [!IMPORTANT]
>  Dieses Feature ermöglicht den API-Aufrufer, Module bereitzustellen, die ausführbare Datei, und möglicherweise böswilligen Code enthalten. Als Sicherheitsmaßnahme, der Aufrufer nicht verwenden sollten `ProvideLibrary` keinen Code zu verteilen, dass es nicht selbst ausführen.  
>   
>  Wenn ein ernsthaftes Sicherheitsproblem an einem bereits freigegebenen Bibliothek, z. B. mscordbi.dll oder mscordacwks.dll, erkannt wird, kann das Shim gepatcht werden, so, dass um die fehlerhaften Versionen der Dateien zu erkennen. Das Shim kann Anforderungen für die gepatchten Versionen der Dateien ausgegeben und die ungültigen Versionen ablehnen, wenn sie als Antwort auf jede Anforderung bereitgestellt werden. Dies kann auftreten, nur dann, wenn der Benutzer auf eine neue Version des Shims gepatcht wurde. Nicht gepatchte Versionen bleiben ein Sicherheitsrisiko.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
