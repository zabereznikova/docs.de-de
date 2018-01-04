---
title: IHostThreadPoolManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager
helpviewer_keywords: IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1cd58c53deec0a895ae6f67cccf26d2c8c2530be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) so konfigurieren Sie den Pool und an die Warteschlange Arbeitsaufgaben an den Threadpool zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAvailableThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Ruft die Anzahl der Threads im Threadpool, der von Arbeitselementen derzeit nicht durchgeführt werden.|  
|[GetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Ruft die maximale Anzahl von Threads, die der Host gleichzeitig im Threadpool.|  
|[GetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Ruft die minimale Anzahl von Threads im Leerlauf, die den Host in Vorwegnahme Ihrer Anforderungen.|  
|[QueueUserWorkItem-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Fügt eine Funktion für die Ausführung der Warteschlange hinzu und stellt ein Objekt mit den Daten, die von der Funktion verwendet werden.|  
|[SetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Legt die maximale Anzahl von Threads, die der Host im Threadpool verwalten kann.|  
|[SetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Legt die Mindestanzahl von Threads im Leerlauf, die der Host zu verwalten, muss in der Erwartung Anforderungen fest.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ist nicht erforderlich, so konfigurieren Sie den Threadpool mithilfe der Werte, angegeben in Aufrufen an die `SetMaxThreads` und `SetMinThreads` Methoden. In diesem Fall sollte der Host einen HRESULT-Wert E_NOTIMPL von diesen Methoden zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
