---
title: IHostSyncManager::SetCLRSyncManager-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
ms.openlocfilehash: 79a41b6705b41414f0926c2ed819e437ecfb51d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714834"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a>IHostSyncManager::SetCLRSyncManager-Methode

Legt die [ICLRSyncManager](iclrsyncmanager-interface.md) -Instanz fest, die der aktuellen [IHostSyncManager](ihostsyncmanager-interface.md) -Instanz zugeordnet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pManager`  
 in Ein Zeiger auf eine- `ICLRSyncManager` Instanz, die vom Common Language Runtime (CLR) bereitgestellt wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetCLRSyncManager` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Um die Kommunikation zwischen dem Host und der CLR zu vereinfachen, sind Hostingschnittstellen in der Regel paarweise. Ein Member des Paars wird vom Host implementiert, und der andere Member wird von der CLR implementiert. Als Host seitige Implementierung entspricht die- `IHostSyncManager` Schnittstelle der `ICLRSyncManager` von der CLR implementierten-Schnittstelle. Die CLR ruft `SetCLRSyncManager` auf, um eine- `ICLRSyncManager` Instanz bereitzustellen, die der Host der aktuellen Instanz zuordnen soll `IHostSyncManager` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
