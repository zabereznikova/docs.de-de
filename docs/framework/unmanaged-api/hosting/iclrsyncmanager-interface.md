---
title: ICLRSyncManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
ms.openlocfilehash: 5bfab21a36becf943b1813f266cf70c4b5e5b1d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690992"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager-Schnittstelle

Definiert Methoden, die es dem Host ermöglichen, Informationen zu angeforderten Tasks zu erhalten und Deadlocks in der Synchronisierungs Implementierung zu erkennen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator-Methode](iclrsyncmanager-createrwlockowneriterator-method.md)|Fordert an, dass die Common Language Runtime (CLR) einen Iterator erstellt, mit dem der Host den Satz von Tasks bestimmt, die auf eine Lese-/Schreibsperre warten.|  
|[DeleteRWLockOwnerIterator-Methode](iclrsyncmanager-deleterwlockowneriterator-method.md)|Fordert an, dass die CLR einen Iterator zerstört, der durch einen-Rückruf erstellt wurde `CreateRWLockOwnerIterator` .|  
|[GetMonitorOwner-Methode](iclrsyncmanager-getmonitorowner-method.md)|Ruft die Aufgabe ab, die den angegebenen Monitor besitzt.|  
|[GetRWLockOwnerNext-Methode](iclrsyncmanager-getrwlockownernext-method.md)|Ruft die nächste Aufgabe ab, die auf die aktuelle Lese-/Schreibsperre wartet.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Thread>
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
- [Managed and Unmanaged Threading (Verwaltetes und nicht verwaltetes Threading)](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Hosten von Schnittstellen](hosting-interfaces.md)
