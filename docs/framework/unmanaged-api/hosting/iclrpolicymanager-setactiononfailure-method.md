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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34d9e1a3747ecf3dffc925d7883599b773dd51f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638969"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>ICLRPolicyManager::SetActionOnFailure-Methode
Gibt die Richtlinienaktion, die die common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `failure`  
 [in] Eines der [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) Werte, der Art des Fehlers für die auszuführende Aktion angibt.  
  
 `action`  
 [in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der angibt, der Aktion, die ausgeführt wird, wenn ein Fehler auftritt. Eine Liste der unterstützten Werte finden Sie im Abschnitt "Hinweise".  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|Eine Richtlinienaktion kann nicht festgelegt werden, für den angegebenen Vorgang, oder eine ungültige Richtlinie-Aktion wurde für den Vorgang angegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig löst die CLR eine Ausnahme aus, wenn ein Fehler auftritt, eine Ressource, z. B. Arbeitsspeicher reservieren. `SetActionOnFailure` ermöglicht dem Host, um dieses Verhalten zu überschreiben, indem Sie die Richtlinie für Aktionen, bei einem Fehler angeben. In der folgende Tabelle werden die Kombinationen von [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) und [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die unterstützt werden. (Das Präfix FAIL_ aus weggelassen [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) Werte.)  
  
||NonCriticalResource|CriticalResource|FatalRuntime|OrphanedLock|StackOverflow|AccessViolation|CodeContract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||Nicht zutreffend||  
|eThrowException|X|X||||Nicht zutreffend||  
|`eAbortThread`|X|X||||Nicht zutreffend|X|  
|`eRudeAbortThread`|X|X||||Nicht zutreffend|X|  
|`eUnloadAppDomain`|X|X||X||Nicht zutreffend|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|Nicht zutreffend|X|  
|`eExitProcess`|X|X||X|X|Nicht zutreffend|X|  
|eFastExitProcess|X|X||X|X|Nicht zutreffend||  
|`eRudeExitProcess`|X|X|X|X|X|Nicht zutreffend||  
|`eDisableRuntime`|X|X|X|X|X|Nicht zutreffend||  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
