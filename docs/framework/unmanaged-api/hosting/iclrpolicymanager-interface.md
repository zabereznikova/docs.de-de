---
title: ICLRPolicyManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140803"
---
# <a name="iclrpolicymanager-interface"></a>ICLRPolicyManager-Schnittstelle
Stellt Methoden bereit, die es dem Host ermöglichen, Richtlinien Aktionen anzugeben, die im Fall von Fehlern und Timeouts durchgeführt werden sollen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetActionOnFailure-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.|  
|[SetActionOnTimeout-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn für den angegebenen Vorgang ein Timeout auftritt.|  
|[SetDefaultAction-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn der angegebene Vorgang auftritt.|  
|[SetTimeout-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|Legt einen Timeout Wert für den angegebenen Vorgang fest.|  
|[SetTimeoutAndAction-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|Legt einen Timeout Wert für den angegebenen Vorgang fest und gibt die Richtlinien Aktion an, die von der CLR bei Auftreten des Vorgangs ausgeführt werden soll.|  
|[SetUnhandledExceptionPolicy-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Gibt das Verhalten der CLR an, wenn eine nicht behandelte Ausnahme auftritt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EClrOperation-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
