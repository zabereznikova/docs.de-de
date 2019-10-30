---
title: ICLRPolicyManager::SetActionOnTimeout-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 9ef906ed5e8a6985c084741bf06b683da79c546e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140790"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a>ICLRPolicyManager::SetActionOnTimeout-Methode
Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn für den angegebenen Vorgang ein Timeout auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `operation`  
 in Einer der [eclroperations](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) -Werte, der den Vorgang angibt, für den die Timeout Aktion angegeben werden soll. Die folgenden Werte werden unterstützt:  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `action`  
 in Einer der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die bei einem Timeout des Vorgangs ausgeführt werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetActionOnTimeout` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|Für den angegebenen `operation`kann kein Timeout festgelegt werden, oder für `operation`wurde ein ungültiger Wert angegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Der Timeout Wert kann entweder das von der CLR festgelegte Standard Timeout oder ein Wert sein, der vom Host in einem Aufrufen der [ICLRPolicyManager:: setTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) -Methode angegeben wird.  
  
 Nicht alle Richtlinien Aktionswerte können als Timeout Verhalten für CLR-Vorgänge angegeben werden. `SetActionOnTimeout` wird in der Regel nur zum eskalieren des Verhaltens verwendet. Beispielsweise kann ein Host angeben, dass Thread Abbrüche in grobe Thread Abbrüche umgewandelt werden, aber nicht das Gegenteil angeben können. In der folgenden Tabelle werden die gültigen `action` Werte für gültige `operation` Werte beschrieben.  
  
|Wert für `operation`|Gültige Werte für `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-erudeabortthread<br />-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_ProcessExit|-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrOperation-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
