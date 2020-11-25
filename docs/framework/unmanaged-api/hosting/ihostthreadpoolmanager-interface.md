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
ms.openlocfilehash: b6625b0ef4dc3de4067514a0b39849c7a958d5c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730759"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager-Schnittstelle

Stellt Methoden bereit, mit denen der Common Language Runtime (CLR) den Thread Pool konfigurieren und Arbeitselemente in die Warteschlange für den Thread Pool einreihen kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetAvailableThreads-Methode](ihostthreadpoolmanager-getavailablethreads-method.md)|Ruft die Anzahl der Threads im Thread Pool ab, die derzeit keine Arbeitselemente verarbeiten.|  
|[GetMaxThreads-Methode](ihostthreadpoolmanager-getmaxthreads-method.md)|Ruft die maximale Anzahl von Threads ab, die der Host gleichzeitig im Thread Pool verwaltet.|  
|[GetMinThreads-Methode](ihostthreadpoolmanager-getminthreads-method.md)|Ruft die Mindestanzahl von Leerlaufthreads ab, die der Host in Erwartung von Anforderungen verwaltet.|  
|[QueueUserWorkItem-Methode](ihostthreadpoolmanager-queueuserworkitem-method.md)|Fügt eine Funktion zur Ausführung in die Warteschlange ein und stellt ein Objekt bereit, das von der Funktion zu verwendende Daten enthält.|  
|[SetMaxThreads-Methode](ihostthreadpoolmanager-setmaxthreads-method.md)|Legt die maximale Anzahl von Threads fest, die der Host im Thread Pool verwalten kann.|  
|[SetMinThreads-Methode](ihostthreadpoolmanager-setminthreads-method.md)|Legt die Mindestanzahl von Leerlaufthreads fest, die der Host in Erwartung von Anforderungen beibehalten muss.|  
  
## <a name="remarks"></a>Hinweise  

 Der Host muss den Thread Pool nicht mit den Werten konfigurieren, die in Aufrufen der `SetMaxThreads` -Methode und der-Methode angegeben sind `SetMinThreads` . In diesem Fall sollte der Host den HRESULT-Wert E_NOTIMPL aus diesen Methoden zurückgeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Hosten von Schnittstellen](hosting-interfaces.md)
