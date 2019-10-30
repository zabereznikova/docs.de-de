---
title: ICLRPolicyManager::SetActionOnFailure-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: 143052febe136e969987c35bc06f6c3b3356aedf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140780"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>ICLRPolicyManager::SetActionOnFailure-Methode
Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `failure`  
 in Einer der [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) -Werte, der den Typ des Fehlers angibt, für den eine Aktion ausgeführt werden soll.  
  
 `action`  
 in Einer der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die durchgeführt werden soll, wenn ein Fehler auftritt. Eine Liste der unterstützten Werte finden Sie im Abschnitt "Hinweise".  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|Eine Richtlinien Aktion kann für den angegebenen Vorgang nicht festgelegt werden, oder für den Vorgang wurde eine ungültige Richtlinien Aktion angegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig löst die CLR eine Ausnahme aus, wenn Sie eine Ressource, z. b. Arbeitsspeicher, nicht zuordnen kann. `SetActionOnFailure` ermöglicht dem Host, dieses Verhalten durch Angeben der Richtlinien Aktion, die bei einem Fehler ausgeführt werden soll, zu überschreiben. In der folgenden Tabelle werden die Kombinationen der unterstützten [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) -und [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte angezeigt. (Das FAIL_-Präfix wird in [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) -Werten weggelassen.)  
  
||Nicht criticalresource|Criticalresource|Fatalruntime|Waisen-edlock|StackOverflow|Zugriffsverletzung|Code Contract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|w|w||||Nicht zutreffend||  
|ethrowexception|w|w||||Nicht zutreffend||  
|`eAbortThread`|w|w||||Nicht zutreffend|w|  
|`eRudeAbortThread`|w|w||||Nicht zutreffend|w|  
|`eUnloadAppDomain`|w|w||w||Nicht zutreffend|w|  
|`eRudeUnloadAppDomain`|w|w||w|w|Nicht zutreffend|w|  
|`eExitProcess`|w|w||w|w|Nicht zutreffend|w|  
|efastexitprocess|w|w||w|w|Nicht zutreffend||  
|`eRudeExitProcess`|w|w|w|w|w|Nicht zutreffend||  
|`eDisableRuntime`|w|w|w|w|w|Nicht zutreffend||  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
