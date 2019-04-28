---
title: IHostPolicyManager::OnDefaultAction-Methode
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45167a2b358b9a7a39390c07f552aa3f3dabce4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760141"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a>IHostPolicyManager::OnDefaultAction-Methode
Benachrichtigt den Host, der die common Language Runtime (CLR) die Standardaktion, die durch einen Aufruf festgelegt wurde die [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) -Methode in der Antwort auf den Abbruch eines Threads oder <xref:System.AppDomain> nicht entladen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `operation`  
 [in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der die Art des Ereignisses, der die CLR reagiert.  
  
 `action`  
 [in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der die Aktion, die die CLR in Reaktion auf das Ereignis ausgeführt wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OnDefaultAction` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf zu verarbeiten. erfolgreich|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrOperation-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
