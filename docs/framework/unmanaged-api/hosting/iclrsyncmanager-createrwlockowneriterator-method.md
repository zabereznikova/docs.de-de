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
ms.openlocfilehash: 9eace3e7330d3f8c0c9762e0b1b456ad1bf8a3ac
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763188"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>ICLRSyncManager::CreateRWLockOwnerIterator-Methode
Fordert an, dass die Common Language Runtime (CLR) einen Iterator erstellt, mit dem der Host den Satz von Tasks bestimmt, die auf eine Lese-/Schreibsperre warten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cookie`  
 in Das Cookie, das der gewünschten Lese-/Schreibsperre zugeordnet ist.  
  
 `pIterator`  
 vorgenommen Ein Zeiger auf einen Iterator, der an die Methoden [getrwlockbesitznext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) und [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) weitergeleitet werden kann.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator`wurde in einem Thread aufgerufen, der derzeit verwalteten Code ausgeführt hat.|  
  
## <a name="remarks"></a>Hinweise  
 Hosts ruft in der Regel die `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` Methoden, und während der `GetRWLockOwnerNext` Deadlockerkennung auf. Der Host ist dafür verantwortlich, sicherzustellen, dass die Lese-/Schreibsperre weiterhin gültig ist, da die CLR keinen Versuch macht, die Lese-/Schreibsperre aufrechtzuerhalten. Es stehen mehrere Strategien für den Host zur Verfügung, um die Gültigkeit der Sperre sicherzustellen:  
  
- Der Host kann Freigabe Aufrufe für die Reader-Writer-Sperre blockieren (z. b. [IHostSemaphore:: ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)) und gleichzeitig sicherstellen, dass dieser Block keinen Deadlock verursacht.  
  
- Der Host kann das warten auf das Ereignis Objekt, das der Lese-/Schreibsperre zugeordnet ist, blockieren und sicherstellen, dass dieser Block keinen Deadlock verursacht.  
  
> [!NOTE]
> `CreateRWLockOwnerIterator`muss nur für Threads aufgerufen werden, die derzeit nicht verwalteten Code ausführen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
