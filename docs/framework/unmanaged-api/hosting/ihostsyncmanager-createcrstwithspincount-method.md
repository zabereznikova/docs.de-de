---
title: IHostSyncManager::CreateCrstWithSpinCount-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
ms.openlocfilehash: 6b2f57c7147cc8ff2abff848bd1e4661c2f5e728
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682880"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a>IHostSyncManager::CreateCrstWithSpinCount-Methode

Erstellt ein kritisches Abschnitts Objekt mit der Drehzahl für die Synchronisierung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwSpinCount`  
 in Gibt die drehanzahl für das kritische Abschnitts Objekt an.  
  
 `ppCrst`  
 vorgenommen Ein Zeiger auf die Adresse einer [IHostCrst](ihostcrst-interface.md) -Instanz oder NULL, wenn der kritische Abschnitt nicht erstellt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`CreateCrstWithSpinCount` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um den angeforderten kritischen Abschnitt zu erstellen.|  
  
## <a name="remarks"></a>Hinweise  

 Eine drehanzahl wird nur auf einem System mit mehreren Prozessoren verwendet. Der drehwert gibt an, wie oft ein aufrufende Thread gedreht werden muss, bevor er einen Warte Vorgang für ein Semaphor ausführt, das einem nicht verfügbaren kritischen Abschnitt zugeordnet ist. Wenn der kritische Abschnitt während des drehvorgangs frei wird, vermeidet der aufrufenden Thread den warte Vorgang. `CreateCrstWithSpinCount` spiegelt die Win32- `InitializeCriticalSectionAndSpinCount` Funktion wider.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostSemaphore-Schnittstelle](ihostsemaphore-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
