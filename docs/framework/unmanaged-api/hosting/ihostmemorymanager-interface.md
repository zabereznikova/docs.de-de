---
title: IHostMemoryManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b39a43874bc1808928f21e0a35638aae9a99ca8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager-Schnittstelle
Stellt Methoden, mit die die common Language Runtime (CLR) virtueller Arbeitsspeicher Anforderungen über den Host vornehmen können statt der standardmäßigen Win32 virtueller Arbeitsspeicher Funktionen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die common Language Runtime (CLR) auf den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen wurden.|  
|[CreateMAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Ruft einen Schnittstellenzeiger auf eine [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz, die zum Anfordern von speicherbelegungen aus einem Heap erstellt, die vom Host verwendet wird.|  
|[GetMemoryLoad-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Ruft die Größe des physischen Speichers, der gerade verwendet wird, ab, wie durch den Host gemeldet.|  
|[NeedsVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR versucht, den angegebenen Arbeitsspeicher verwendet wird.|  
|[RegisterMemoryNotificationCallback-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registriert einen Zeiger auf eine Rückruffunktion, die der Host wird aufgerufen, um die CLR über der aktuellen Auslastung des Arbeitsspeichers auf dem Computer zu benachrichtigen.|  
|[ReleasedVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR wurde mit den angegebenen Speicher.|  
|[VirtualAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die reserviert oder führt einen Commit für einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses.|  
|[VirtualFree-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die frei, Aufhebung der Zusage, oder freigibt und Aufhebung der Zusage eines von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses.|  
|[VirtualProtect-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die ändert sich der Schutz für einen Bereich der Seiten im virtuellen Adressraum des aufrufenden Prozesses, die ein Commit ausgeführt wurde.|  
|[VirtualQuery-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abruft.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostMemoryManager`Außerdem bietet Methoden für die CLR, um einen Zeiger über den Arbeitsspeicher auf dem Heap anzufordern und die abzurufenden die Ebene der arbeitsspeicherauslastung im Prozess, durch den Host gemeldet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
