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
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503938"
---
# <a name="ihostpolicymanager-interface"></a>IHostPolicyManager-Schnittstelle
Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die Common Language Runtime (CLR) im Falle von Abbrüchen, Timeouts oder Fehlern ausführt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[OnDefaultAction-Methode](ihostpolicymanager-ondefaultaction-method.md)|Benachrichtigt den Host, dass die CLR im Begriff ist, die Standardaktion zu übernehmen, die durch einen [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) -Vorgang als Reaktion auf einen Thread Abbruch oder entladen angegeben wird <xref:System.AppDomain> .|  
|[OnFailure-Methode](ihostpolicymanager-onfailure-method.md)|Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Server Failure](iclrpolicymanager-setactiononfailure-method.md) -Aufrufe angegebene Aktion in Reaktion auf einen Fehler bei der Ressourcen Zuordnung oder-Wiederherstellung auszuführen.|  
|[OnTimeout-Methode](ihostpolicymanager-ontimeout-method.md)|Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Abtast Timeout](iclrpolicymanager-setactionontimeout-method.md) -Vorgang angegebene Aktion als Antwort auf ein Timeout auszuführen.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [EClrFailure-Enumeration](eclrfailure-enumeration.md)
- [EClrOperation-Enumeration](eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
