---
title: IHostMemoryManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96c2081e5ff5b716c2645fa44a24f12beaa0f8e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585457"
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager-Schnittstelle
Enthält Methoden, mit denen die common Language Runtime (CLR) zum virtuellen Arbeitsspeicher Anforderungen über den Host, anstelle der Win32-Standardfunktionen der virtuellen Speicher an.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Benachrichtigt den Host aus, die common Language Runtime (CLR) auf den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen wurde.|  
|[CreateMAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Ruft einen Schnittstellenzeiger auf ein [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz, die zum Anfordern der speicherbelegung aus einem Heap erstellt, die vom Host verwendet wird.|  
|[GetMemoryLoad-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Ruft die Menge des physischen Speichers, der gerade verwendet wird, ab, wie durch den Host gemeldet.|  
|[NeedsVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR versucht, den angegebenen Speicher zu verwenden ist.|  
|[RegisterMemoryNotificationCallback-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die CLR über die aktuelle Auslastung des Arbeitsspeichers auf dem Computer zu benachrichtigen.|  
|[ReleasedVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR wurde mit den angegebenen Speicher.|  
|[VirtualAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion, die reserviert oder übergibt einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses.|  
|[VirtualFree-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion, die Versionen, bewirkt, oder frei und Aufhebung der Zusage eines der Seiten, die innerhalb des virtuellen Adressraums des aufrufenden Prozesses.|  
|[VirtualProtect-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Dient als ein logischer Wrapper für die entsprechende Win32-Funktion, die den Schutz in einem Bereich von Seiten mit Commit in der virtuelle Adressraum des aufrufenden Prozesses geändert.|  
|[VirtualQuery-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion, die Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abgerufen.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostMemoryManager` Außerdem bietet Methoden für die CLR einen Zeiger über die speicheranforderungen auf dem Heap zu machen, sowie zum Abrufen der Ebene der arbeitsspeicherauslastung im Prozess zu erhalten, wie durch den Host gemeldet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
