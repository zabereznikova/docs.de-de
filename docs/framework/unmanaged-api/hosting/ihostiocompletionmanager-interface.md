---
title: IHostIoCompletionManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133852"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager-Schnittstelle
Stellt Methoden bereit, die dem Common Language Runtime (CLR) die Interaktion mit e/a-Abschlussports ermöglichen, die vom Host bereitgestellt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Bind-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Bindet ein Handle an einen e/a-Abschlussport.|  
|[CloseIoCompletionPort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Schließt einen Port, der durch einen früheren-`CreateIoCompletionPort`erstellt wurde.|  
|[CreateIoCompletionPort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Fordert an, dass der Host einen neuen e/a-Abschlussport erstellt.|  
|[GetAvailableThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Ruft die Anzahl der e/a-Abschluss Threads ab, die derzeit keine Anforderungen verarbeiten.|  
|[GetHostOverlappedSize-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Ruft die Größe aller benutzerdefinierten Daten ab, die der Host an e/a-Anforderungen anfügen soll.|  
|[GetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Ruft die maximale Anzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen in hohem Maß abrufen kann.|  
|[GetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Ruft die Mindestanzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen bereitstellt.|  
|[InitializeHostOverlapped-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Bietet dem Host die Möglichkeit, benutzerdefinierte Daten zu einer e/a-Anforderung zu initialisieren.|  
|[SetCLRIoCompletionManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Stellt dem Host einen Schnittstellen Zeiger auf eine [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) -Instanz bereit, die von der CLR implementiert wird.|  
|[SetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Legt die maximale Anzahl von Threads fest, die der Host Dienst-e/a-Anforderungen zugeordnet.|  
|[SetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Legt die Mindestanzahl von Threads fest, die der Host für die e/a-Vervollständigung in hohem Maß beachten soll.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostIoCompletionManager` entspricht der von der CLR implementierten `ICLRIoCompletionManager` Schnittstelle. Die CLR ruft die Methoden von `IHostIoCompletionManager` auf, um Handles an die vom Host bereitgestellten Ports zu binden, und der Host ruft die Methoden von `ICLRIoCompletionManager` auf, um den Abschluss von e/a-Anforderungen zu melden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
