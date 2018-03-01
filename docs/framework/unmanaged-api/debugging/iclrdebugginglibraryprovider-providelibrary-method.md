---
title: ICLRDebuggingLibraryProvider::ProvideLibrary-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cf6860a616312504e3d23177734cb532405bd714
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary-Methode
Ruft eine Bibliotheksanbieter-Rückrufschnittstelle, die common Language Runtime (CLR) versionsspezifische befindet, und Laden bei Bedarf es ermöglicht.  
  
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
 [in] Der Datums-/ Zeitstempel im COFF-Dateiheader der PE-Dateien gespeichert.  
  
 `pLibraryProvider`  
 [in] Die `SizeOfImage` Feld im optionalen COFF-Dateiheader der PE-Dateien gespeichert.  
  
 `hModule`  
 [out] Das Handle für das angeforderte Modul.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 `ProvideLibrary`ermöglicht es dem Debugger, Module bereitzustellen, die für das Debuggen von bestimmter CLR-Dateien, z. B. "mscordbi.dll" und mscordacwks.dll erforderlich sind. Das Modul verarbeitet haben, gültig bleiben, bis ein Aufruf der [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) Methode gibt an, dass sie freigegeben werden können, an diesem Punkt wird der Verantwortung des Aufrufers, die Handles freizugeben.  
  
 Der Debugger kann alle verfügbaren Verfahren verwenden, suchen und beschaffen das debugging-Modul.  
  
> [!IMPORTANT]
>  Diese Funktion ermöglicht die API-Aufrufer, Module bereitzustellen, die ausführbare Datei, und möglicherweise schädlichen Code enthalten. Als Sicherheitsmaßnahme, der Aufrufer nicht die zu verwendende `ProvideLibrary` keinen Code verteilen, dass es nicht selbst ausführen.  
>   
>  Ein schwerwiegendes Sicherheitsproblem erkannt wird, in einem bereits freigegebenen Bibliothek, z. B. "mscordbi.dll" oder mscordacwks.dll, kann das Shim gepatcht werden, so, dass die fehlerhaften Versionen der Dateien erkannt. Der Shim kann dann ausgeben von Anforderungen für die gepatchten Versionen der Dateien und die ungültigen Versionen ablehnen, wenn sie als Antwort auf eine beliebige Anforderung bereitgestellt werden. Dies kann auftreten, nur, wenn der Benutzer auf eine neue Version des Shims gepatcht wurde. Gepatchte Versionen bleiben anfällig.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
