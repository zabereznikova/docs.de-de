---
title: ICLRSyncManager::CreateRWLockOwnerIterator-Methode
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3554d351512f48aad65872dd9ae82d084552d518
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600244"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>ICLRSyncManager::CreateRWLockOwnerIterator-Methode
Fordert, dass die common Language Runtime (CLR) erstellt einen Iterator für den Host zu verwenden, um zu bestimmen, den Satz von Aufgaben, die auf eine Reader / Writer-Sperre warten.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cookie`  
 [in] Das Cookie, das die gewünschte Reader / Writer-Sperre zugeordnet.  
  
 `pIterator`  
 [out] Ein Zeiger auf ein Iterator, der übergeben werden kann die [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) und [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) Methoden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator` wurde in einem Thread aufgerufen, die derzeit auf verwalteten Code ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie die Hosts in der Regel die `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, und `GetRWLockOwnerNext` Methoden während der Deadlockerkennung. Der Host ist dafür verantwortlich, sicherzustellen, dass die Reader / Writer-Sperre noch gültig ist, ist, da die CLR versucht nicht, die die Lese-/ Schreibsperre beibehalten wird. Es stehen verschiedene Strategien für den Host aus, um sicherzustellen, dass die Gültigkeit der Sperre zur Verfügung:  
  
-   Der Host kann Freigabeaufrufe für den Lese-/ Schreibsperre (z. B. [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) und gleichzeitig sicherstellen, dass dieser Block keinen Deadlock verursacht.  
  
-   Der Host kann das Warten auf das Ereignisobjekt, das der Reader / Writer-Sperre zugeordneten beenden blockieren und wieder sicherstellen, dass dieser Block keinen Deadlock verursacht.  
  
> [!NOTE]
>  `CreateRWLockOwnerIterator` muss nur auf Threads aufgerufen werden, die derzeit nicht verwalteten Code ausgeführt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
