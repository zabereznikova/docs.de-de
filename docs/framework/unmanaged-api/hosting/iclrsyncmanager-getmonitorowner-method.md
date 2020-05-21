---
title: ICLRSyncManager::GetMonitorOwner-Methode
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
ms.openlocfilehash: 77debe047f5b379237022f44ef8f9d96718b227d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762499"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>ICLRSyncManager::GetMonitorOwner-Methode
Ruft die [IHostTask](ihosttask-interface.md) -Instanz ab, die den Monitor besitzt, der durch das angegebene Cookie identifiziert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cookie`  
 in Das Cookie, das dem Monitor zugeordnet ist.  
  
 `ppOwnerHostTask`  
 vorgenommen Ein Zeiger auf den, der `IHostTask` derzeit den Monitor besitzt, oder NULL, wenn keine Aufgabe den Besitz besitzt.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ruft in der Regel `GetMonitorOwner` als Teil eines Deadlock-Erkennungsmechanismus auf. Das Cookie ist einem Monitor zugeordnet, wenn er mithilfe eines [IHostSyncManager:: | atemonitorevent](ihostsyncmanager-createmonitorevent-method.md)-Aufrufens erstellt wird.  
  
> [!NOTE]
> Ein aufzurufende Ereignis, das dem Monitor zugrunde liegt, blockiert möglicherweise –, aber keinen Deadlock –, wenn aktuell ein aufrufungs Vorgang für das diesem Monitor zugeordnete Cookie wirksam ist. Andere Tasks können auch blockiert werden, wenn Sie versuchen, diesen Monitor zu erwerben.  
  
 `GetMonitorOwner`gibt immer sofort zurück und kann nach einem Aufruf von jederzeit aufgerufen werden `CreateMonitorEvent` . Der Host muss nicht warten, bis ein Task auf das Ereignis wartet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
