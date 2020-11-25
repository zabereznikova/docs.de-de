---
title: IHostPolicyManager::OnFailure-Methode
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
ms.openlocfilehash: efa7b9d49ea9807af2164bb6ee54422dd72b14e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730421"
---
# <a name="ihostpolicymanageronfailure-method"></a>IHostPolicyManager::OnFailure-Methode

Benachrichtigt den Host, dass die Common Language Runtime (CLR) die Aktion durchführen soll, die durch einen Aufrufe der [ICLRPolicyManager:: abtationonfailure](iclrpolicymanager-setactiononfailure-method.md) -Methode als Reaktion auf einen Ressourcen Zuordnungs-oder-Fehler bei der Wiederherstellung angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `failure`  
 in Einer der [EClrFailure](eclrfailure-enumeration.md) -Werte, der die Art des Fehlers angibt, auf den die CLR antwortet.  
  
 `action`  
 in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die von der CLR als Reaktion auf ausgeführt wird `failure` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`OnFailure` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EClrFailure-Enumeration](eclrfailure-enumeration.md)
- [EPolicyAction-Enumeration](epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](ihostpolicymanager-interface.md)
