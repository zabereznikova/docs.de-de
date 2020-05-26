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
ms.openlocfilehash: 4e7e76a4a3ab291ee97ad0912e3d6224cdf96fba
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804487"
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager-Schnittstelle
Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, virtuelle Speicheranforderungen über den Host zu erstellen, statt die standardmäßigen Win32-Funktionen für den virtuellen Arbeitsspeicher zu verwenden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace-Methode](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die Common Language Runtime (CLR) den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen hat.|  
|[CreateMAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](ihostmalloc-interface.md) -Instanz ab, die verwendet wird, um Speicher Belegungen von einem Heap anzufordern, der vom Host erstellt wurde.|  
|[GetMemoryLoad-Methode](ihostmemorymanager-getmemoryload-method.md)|Ruft die Menge an physischem Arbeitsspeicher ab, die derzeit verwendet wird, wie vom Host gemeldet.|  
|[NeedsVirtualAddressSpace-Methode](ihostmemorymanager-needsvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR versucht, den angegebenen Arbeitsspeicher zu verwenden.|  
|[RegisterMemoryNotificationCallback-Methode](ihostmemorymanager-registermemorynotificationcallback-method.md)|Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die CLR über die aktuelle Arbeitsspeicher Auslastung auf dem Computer zu benachrichtigen.|  
|[ReleasedVirtualAddressSpace-Methode](ihostmemorymanager-releasedvirtualaddressspace-method.md)|Benachrichtigt den Host, dass die CLR die Verwendung des angegebenen Speichers beendet hat.|  
|[VirtualAlloc-Methode](ihostmemorymanager-virtualalloc-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses reserviert oder übergibt.|  
|[VirtualFree-Methode](ihostmemorymanager-virtualfree-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Bereich von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses freigibt, decommittet oder freigibt bzw. den Seitenbereich debugübergibt.|  
|[VirtualProtect-Methode](ihostmemorymanager-virtualprotect-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, mit der der Schutz für einen Bereich von zugegebenen Seiten im virtuellen Adressraum des aufrufenden Prozesses geändert wird.|  
|[VirtualQuery-Methode](ihostmemorymanager-virtualquery-method.md)|Dient als logischer Wrapper für die entsprechende Win32-Funktion, die Informationen zu einem Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abruft.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostMemoryManager`stellt außerdem Methoden bereit, mit denen die CLR einen Zeiger abrufen kann, über den Arbeitsspeicher Anforderungen für den Heap und die Arbeitsspeicher Auslastung im Prozess, wie vom Host gemeldet, abgerufen werden können.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMalloc-Schnittstelle](ihostmalloc-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
