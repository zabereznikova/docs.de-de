---
title: IHostCrst::SetSpinCount-Methode
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: a8642235cda359b849c49a35ab565397402c37d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130516"
---
# <a name="ihostcrstsetspincount-method"></a>IHostCrst::SetSpinCount-Methode
Legt die drehanzahl für die aktuelle [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) -Instanz fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwSpinCount`  
 in Die neue Spin-Anzahl für die aktuelle `IHostCrst` Instanz.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetSpinCount` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn auf Multiprozessorsystemen der kritische Abschnitt, der durch die aktuelle `IHostCrst` Instanz dargestellt wird, nicht verfügbar ist, wird `dwSpinCount` Zeiten von einem aufrufenden Thread aufgerufen, bevor [IHostSemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) für ein Semaphor aufgerufen wird, das mit dem kritischen Abschnitt verknüpft ist. Wenn der kritische Abschnitt während des drehvorgangs frei wird, vermeidet der aufrufenden Thread den warte Vorgang.  
  
 Die Verwendung von `dwSpinCount` ist mit der Verwendung des-Parameters desselben Namens in der Win32-`InitializeCriticalSectionAndSpinCount` Funktion identisch.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostCrst-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
