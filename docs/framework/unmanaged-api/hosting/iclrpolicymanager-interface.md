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
ms.openlocfilehash: 631301a10aee96bb00aeda6b0b8695f0aea186a8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703477"
---
# <a name="iclrpolicymanager-interface"></a>ICLRPolicyManager-Schnittstelle
Stellt Methoden bereit, die es dem Host ermöglichen, Richtlinien Aktionen anzugeben, die im Fall von Fehlern und Timeouts durchgeführt werden sollen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetActionOnFailure-Methode](iclrpolicymanager-setactiononfailure-method.md)|Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.|  
|[SetActionOnTimeout-Methode](iclrpolicymanager-setactionontimeout-method.md)|Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn für den angegebenen Vorgang ein Timeout auftritt.|  
|[SetDefaultAction-Methode](iclrpolicymanager-setdefaultaction-method.md)|Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn der angegebene Vorgang auftritt.|  
|[SetTimeout-Methode](iclrpolicymanager-settimeout-method.md)|Legt einen Timeout Wert für den angegebenen Vorgang fest.|  
|[SetTimeoutAndAction-Methode](iclrpolicymanager-settimeoutandaction-method.md)|Legt einen Timeout Wert für den angegebenen Vorgang fest und gibt die Richtlinien Aktion an, die von der CLR bei Auftreten des Vorgangs ausgeführt werden soll.|  
|[SetUnhandledExceptionPolicy-Methode](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Gibt das Verhalten der CLR an, wenn eine nicht behandelte Ausnahme auftritt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](eclrfailure-enumeration.md)
- [EClrOperation-Enumeration](eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](epolicyaction-enumeration.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
