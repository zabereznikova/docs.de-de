---
title: IHostThreadPoolManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122082"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager-Schnittstelle
Stellt Methoden bereit, mit denen der Common Language Runtime (CLR) den Thread Pool konfigurieren und Arbeitselemente in die Warteschlange für den Thread Pool einreihen kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAvailableThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Ruft die Anzahl der Threads im Thread Pool ab, die derzeit keine Arbeitselemente verarbeiten.|  
|[GetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Ruft die maximale Anzahl von Threads ab, die der Host gleichzeitig im Thread Pool verwaltet.|  
|[GetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Ruft die Mindestanzahl von Leerlaufthreads ab, die der Host in Erwartung von Anforderungen verwaltet.|  
|[QueueUserWorkItem-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Fügt eine Funktion zur Ausführung in die Warteschlange ein und stellt ein Objekt bereit, das von der Funktion zu verwendende Daten enthält.|  
|[SetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Legt die maximale Anzahl von Threads fest, die der Host im Thread Pool verwalten kann.|  
|[SetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Legt die Mindestanzahl von Leerlaufthreads fest, die der Host in Erwartung von Anforderungen beibehalten muss.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host muss den Thread Pool nicht mithilfe der Werte konfigurieren, die in Aufrufen der Methoden `SetMaxThreads` und `SetMinThreads` angegeben sind. In diesem Fall sollte der Host einen HRESULT-Wert von E_NOTIMPL aus diesen Methoden zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
