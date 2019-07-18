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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e7976740a79efda8e5ab569f2efb55444012c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796568"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) zum Konfigurieren der Threadpool der Warteschleife hinzu und zum Arbeitsaufgaben an den Threadpool-Warteschlange zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAvailableThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Ruft die Anzahl der Threads im Threadpool der Warteschleife hinzu, die derzeit keine Arbeitsaufgabe verarbeiten.|  
|[GetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Ruft die maximale Anzahl von Threads, die der Host verwaltet, die gleichzeitig im Threadpool ab.|  
|[GetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Ruft die minimale Anzahl von Threads im Leerlauf, die den Host in der Erwartung Anforderungen ab.|  
|[QueueUserWorkItem-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Fügt eine Funktion für die Ausführung und stellt ein Objekt mit Daten, die von der Funktion verwendet werden.|  
|[SetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Legt die maximale Anzahl von Threads, die der Host im Threadpool der Warteschleife hinzu verwalten kann.|  
|[SetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Legt die minimale Anzahl von Threads im Leerlauf, die der Host zu verwalten, muss in der Erwartung Anforderungen fest.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ist nicht erforderlich, so konfigurieren Sie den Threadpool mit den Werten, die in Aufrufen von angegeben die `SetMaxThreads` und `SetMinThreads` Methoden. In diesem Fall sollte der Host einen HRESULT-Wert E_NOTIMPL von diesen Methoden zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
