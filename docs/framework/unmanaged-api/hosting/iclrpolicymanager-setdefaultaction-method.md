---
title: ICLRPolicyManager::SetDefaultAction-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: 8dc3a3c04a619ace566e173fb8d8945a9d921bce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140767"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>ICLRPolicyManager::SetDefaultAction-Methode
Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Vorgang auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `operation`  
 in Einer der [eclroperations](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) -Werte, der die Aktion angibt, für die das CLR-Verhalten angepasst werden soll.  
  
 `action`  
 in Einer der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die die CLR beim Auftreten `operation` ausführen sollte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|Für den `operation`wurde ein ungültiger `action` angegeben, oder für `operation`wurde ein ungültiger Wert angegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Nicht alle Richtlinien Aktionswerte können als Standardverhalten für CLR-Vorgänge angegeben werden. `SetDefaultAction` können in der Regel nur zum eskalieren des Verhaltens verwendet werden. Beispielsweise kann ein Host angeben, dass Thread Abbrüche in grobe Thread Abbrüche umgewandelt werden, aber nicht das Gegenteil angeben können. In der folgenden Tabelle werden die gültigen `action` Werte für jeden möglichen `operation` Wert beschrieben.  
  
|Wert für `operation`|Gültige Werte für `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|-eabortthread<br />-erudeabortthread<br />-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-erudeabortthread<br />-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_AppDomainRudeUnload|-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_ProcessExit|-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_FinalizerRun|-enoaction<br />-eabortthread<br />-erudeabortthread<br />-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrOperation-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
