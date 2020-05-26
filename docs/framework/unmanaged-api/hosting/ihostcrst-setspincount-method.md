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
ms.openlocfilehash: 2436809f35d5c46416f48987cc92feb51d291a6a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804884"
---
# <a name="ihostcrstsetspincount-method"></a>IHostCrst::SetSpinCount-Methode
Legt die drehanzahl für die aktuelle [IHostCrst](ihostcrst-interface.md) -Instanz fest.  
  
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
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetSpinCount`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn auf Multiprozessorsystemen der kritische, von der aktuellen Instanz dargestellte Abschnitt nicht `IHostCrst` verfügbar ist, wird ein aufrufenden Thread `dwSpinCount` vor dem Aufrufen von [IHostSemaphore:: Wait](ihostsemaphore-wait-method.md) für ein Semaphor, das dem kritischen Abschnitt zugeordnet ist, mehrmals aufgerufen. Wenn der kritische Abschnitt während des drehvorgangs frei wird, vermeidet der aufrufenden Thread den warte Vorgang.  
  
 Die Verwendung von `dwSpinCount` ist mit der Verwendung des-Parameters desselben Namens in der Win32- `InitializeCriticalSectionAndSpinCount` Funktion identisch.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostCrst-Schnittstelle](ihostcrst-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
