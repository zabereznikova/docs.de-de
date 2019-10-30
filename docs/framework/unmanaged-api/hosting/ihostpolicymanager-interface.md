---
title: IHostPolicyManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128602"
---
# <a name="ihostpolicymanager-interface"></a>IHostPolicyManager-Schnittstelle
Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die Common Language Runtime (CLR) im Falle von Abbrüchen, Timeouts oder Fehlern ausführt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[OnDefaultAction-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|Benachrichtigt den Host, dass die CLR die Standardaktion, die durch einen [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) -Befehl angegeben wird, als Reaktion auf einen Thread Abbruch oder <xref:System.AppDomain> entladen übernehmen soll.|  
|[OnFailure-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Server Failure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) -Aufrufe angegebene Aktion in Reaktion auf einen Fehler bei der Ressourcen Zuordnung oder-Wiederherstellung auszuführen.|  
|[OnTimeout-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Abtast Timeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) -Vorgang angegebene Aktion als Antwort auf ein Timeout auszuführen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EClrOperation-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
