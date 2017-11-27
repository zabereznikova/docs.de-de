---
title: ICLRPolicyManager::SetTimeoutAndAction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetTimeoutAndAction
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a15454e1cea29e3c0025797633f22e9e18554347
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>ICLRPolicyManager::SetTimeoutAndAction-Methode
Legt einen Timeoutwert für den angegebenen Vorgang und gibt an, die Gruppenrichtlinien-Aktion, die die common Language Runtime (CLR) ausgeführt werden soll, wenn der Vorgang auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `operation`  
 [in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der den Vorgang für die das Timeout und eine Richtlinie festgelegt `action`. Die folgenden Werte werden unterstützt:  
  
-   OPR_AppDomainUnload  
  
-   OPR_ProcessExit  
  
-   OPR_ThreadRudeAbortInCriticalRegion  
  
-   OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 [in] Der neue Timeoutwert in Millisekunden. Der Wert INFINITE bewirkt, dass `operation` niemals zu einem Timeout führen.  
  
 `action`  
 [in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der angibt, dass die CLR, wenn ausführen soll die Richtlinienaktion `operation` auftritt.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `action`.|  
  
## <a name="remarks"></a>Hinweise  
 `SetTimeoutAndAction`Kapselt die Funktionen des die [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) und [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) Methoden, und kann anstelle von sequenziellen Aufrufen dieser beiden Methoden aufgerufen werden.  
  
> [!IMPORTANT]
>  Nicht alle Werte für Aktivierungsrichtlinien Aktion können als das Timeoutverhalten für CLR-Vorgänge angegeben werden. Finden Sie im Abschnitt "Hinweise" in den Themen dieser beiden Methoden für gültige Werte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [EClrOperation-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnTimeout-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)  
 [ICLRPolicyManager:: SetTimeoutAndAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
