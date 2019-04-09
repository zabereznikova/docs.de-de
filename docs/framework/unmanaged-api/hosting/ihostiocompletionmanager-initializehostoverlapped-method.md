---
title: IHostIoCompletionManager::InitializeHostOverlapped-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dea19a13cd2c741a24695b293ae1c8621ad5688
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157664"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>IHostIoCompletionManager::InitializeHostOverlapped-Methode
Ermöglicht es dem Host mit der Möglichkeit, benutzerdefinierte Daten zum Anfügen an eine Win32 initialisieren `OVERLAPPED` -Struktur, die für asynchrone e/a-Anforderungen verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pvOverlapped`  
 [in] Ein Zeiger auf die Win32- `OVERLAPPED` Struktur mit der e/a-Anforderung eingeschlossen werden sollen.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuweisen.|  
  
## <a name="remarks"></a>Hinweise  
 Die Windows-Plattform-Funktionen verwenden die `OVERLAPPED` Struktur zum Speichern von Status für asynchrone e/a-Anforderungen. Die CLR ruft die `InitializeHostOverlapped` Methode, um dem Host Geben Sie das Anfügen von benutzerdefinierten Daten zu einem `OVERLAPPED` Instanz.  
  
> [!IMPORTANT]
>  Rufen Sie am Anfang des benutzerdefinierten Datenblocks müssen Hosts den Offset der Größe der Festlegen der `OVERLAPPED` Struktur (`sizeof(OVERLAPPED)`).  
  
 Ein Rückgabewert von E_OUTOFMEMORY gibt an, dass der Host zum Initialisieren der benutzerdefinierten Daten fehlgeschlagen ist. In diesem Fall wird die CLR meldet einen Fehler, und der Aufruf schlägt fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [GetHostOverlappedSize-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [IHostIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
