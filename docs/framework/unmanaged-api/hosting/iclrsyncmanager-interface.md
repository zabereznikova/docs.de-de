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
ms.openlocfilehash: 3593e4d68058a1820f575c92ff9571d43560316a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133935"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager-Schnittstelle
Definiert Methoden, die es dem Host ermöglichen, Informationen zu angeforderten Tasks zu erhalten und Deadlocks in der Synchronisierungs Implementierung zu erkennen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator-Methode](iclrsyncmanager-createrwlockowneriterator-method.md)|Fordert an, dass die Common Language Runtime (CLR) einen Iterator erstellt, mit dem der Host den Satz von Tasks bestimmt, die auf eine Lese-/Schreibsperre warten.|  
|[DeleteRWLockOwnerIterator-Methode](iclrsyncmanager-deleterwlockowneriterator-method.md)|Fordert an, dass die CLR einen Iterator zerstört, der durch einen `CreateRWLockOwnerIterator`aufgerufen wurde.|  
|[GetMonitorOwner-Methode](iclrsyncmanager-getmonitorowner-method.md)|Ruft die Aufgabe ab, die den angegebenen Monitor besitzt.|  
|[GetRWLockOwnerNext-Methode](iclrsyncmanager-getrwlockownernext-method.md)|Ruft die nächste Aufgabe ab, die auf die aktuelle Lese-/Schreibsperre wartet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Thread>
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
- [Verwaltetes und nicht verwaltetes Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Hosten von Schnittstellen](hosting-interfaces.md)
