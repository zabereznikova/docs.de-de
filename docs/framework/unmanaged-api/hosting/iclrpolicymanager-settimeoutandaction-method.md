---
title: ICLRPolicyManager::SetTimeoutAndAction-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: efd30ef04c148d5e098110efcb37e50f143884e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703428"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>ICLRPolicyManager::SetTimeoutAndAction-Methode
Legt einen Timeout Wert für den angegebenen Vorgang fest und gibt die Richtlinien Aktion an, die der Common Language Runtime (CLR) ausführen soll, wenn der Vorgang ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `operation`  
 in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der den Vorgang angibt, für den das Timeout und die Richtlinie festgelegt werden sollen `action` . Die folgenden Werte werden unterstützt:  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 in Der neue Timeout Wert in Millisekunden. Der Wert unendlich bewirkt, dass nie ein Timeout auftritt `operation` .  
  
 `action`  
 in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die die CLR bei Auftreten durchführen soll `operation` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|Für den angegebenen kann kein Timeout festgelegt werden `operation` , oder für wurde ein ungültiger Wert angegeben `action` .|  
  
## <a name="remarks"></a>Hinweise  
 `SetTimeoutAndAction`kapselt die Funktionen der [ICLRPolicyManager:: setTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) -Methode und der [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) -Methode und kann anstelle von sequenziellen Aufrufen dieser beiden Methoden aufgerufen werden.  
  
> [!IMPORTANT]
> Nicht alle Richtlinien Aktionswerte können als Timeout Verhalten für CLR-Vorgänge angegeben werden. Gültige Werte finden Sie in den Abschnitten zu den Themen zu diesen beiden Methoden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrOperation-Enumeration](eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [SetActionOnTimeout-Methode](iclrpolicymanager-setactionontimeout-method.md)
- [ICLRPolicyManager:: SetTimeoutAndAction](iclrpolicymanager-settimeoutandaction-method.md)
