---
title: IHostAutoEvent-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: a24939ac0b0808546ef3615fae4909c6c3cf8a2e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804994"
---
# <a name="ihostautoevent-interface"></a>IHostAutoEvent-Schnittstelle
Stellt eine Darstellung der Host Implementierung eines automatischen Zurücksetzungs Ereignisses bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Set-Methode](ihostautoevent-set-method.md)|Legt die aktuelle `IHostAutoEvent` Instanz auf einen signalisierten Zustand fest.|  
|[Wait-Methode](ihostautoevent-wait-method.md)|Bewirkt, dass die aktuelle `IHostAutoEvent` Instanz wartet, bis das Ereignis im Besitz des Ereignisses ist oder eine angegebene Zeitspanne abläuft.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostManualEvent-Schnittstelle](ihostmanualevent-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
