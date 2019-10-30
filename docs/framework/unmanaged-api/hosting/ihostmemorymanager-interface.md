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
ms.openlocfilehash: bc05d76795f20d28d6d2899d61dc4674ebfdca8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128647"
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager-Schnittstelle
Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, virtuelle Speicheranforderungen über den Host zu erstellen, statt die standardmäßigen Win32-Funktionen für den virtuellen Arbeitsspeicher zu verwenden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die Common Language Runtime (CLR) den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen hat.|  
|[CreateMAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz ab, die verwendet wird, um Speicher Belegungen von einem Heap anzufordern, der vom Host erstellt wurde.|  
|[GetMemoryLoad-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Ruft die Menge an physischem Arbeitsspeicher ab, die derzeit verwendet wird, wie vom Host gemeldet.|  
|[NeedsVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR versucht, den angegebenen Arbeitsspeicher zu verwenden.|  
|[RegisterMemoryNotificationCallback-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die CLR über die aktuelle Arbeitsspeicher Auslastung auf dem Computer zu benachrichtigen.|  
|[ReleasedVirtualAddressSpace-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR die Verwendung des angegebenen Speichers beendet hat.|  
|[VirtualAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses reserviert oder übergibt.|  
|[VirtualFree-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Bereich von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses freigibt, decommittet oder freigibt bzw. den Seitenbereich debugübergibt.|  
|[VirtualProtect-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, mit der der Schutz für einen Bereich von zugegebenen Seiten im virtuellen Adressraum des aufrufenden Prozesses geändert wird.|  
|[VirtualQuery-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, die Informationen zu einem Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abruft.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostMemoryManager` bietet auch Methoden für die CLR zum Abrufen eines Zeigers, über den Arbeitsspeicher Anforderungen auf dem Heap gesendet werden, und um die Arbeitsspeicher Auslastung des Prozesses zu erhalten, wie vom Host gemeldet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
