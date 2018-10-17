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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21295268ba5c230062fadddc9c61217f3574551b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49370983"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager-Schnittstelle
Definiert Methoden, die den Host zum Abrufen von Informationen zu den angeforderten Aufgaben und zum Erkennen von Deadlocks in die Synchronisierung-Implementierung zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator-Methode](iclrsyncmanager-createrwlockowneriterator-method.md)|Fordert, dass die common Language Runtime (CLR) erstellt einen Iterator für den Host zu verwenden, um zu bestimmen, den Satz von Aufgaben, die auf eine Reader / Writer-Sperre warten.|  
|[DeleteRWLockOwnerIterator-Methode](iclrsyncmanager-deleterwlockowneriterator-method.md)|Fordert an, dass die CLR zerstört einen Iterator, der durch einen Aufruf von erstellten `CreateRWLockOwnerIterator`.|  
|[GetMonitorOwner-Methode](iclrsyncmanager-getmonitorowner-method.md)|Ruft die Aufgabe ab, die den angegebenen Monitor besitzt.|  
|[GetRWLockOwnerNext-Methode](iclrsyncmanager-getrwlockownernext-method.md)|Ruft die nächste Aufgabe, die auf die aktuelle Reader / Writer-Sperre wartet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread>  
 [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)  
 [Verwaltete und nicht verwaltetes Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))  
 [Hosten von Schnittstellen](hosting-interfaces.md)
