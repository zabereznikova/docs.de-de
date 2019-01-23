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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 186f5618cce7a70bc4fab55616a0f8b08025a81f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542534"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) für die Interaktion mit e/a-Abschlussports, die vom Host zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Bind-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Wird ein Handle an einen e/a-Abschlussanschluss gebunden.|  
|[CloseIoCompletionPort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Schließt einen Port, der durch einen früheren Aufruf von erstellten `CreateIoCompletionPort`.|  
|[CreateIoCompletionPort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Fordert an, dass der Host eine neue e/a-Abschlussport zu erstellen.|  
|[GetAvailableThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Ruft die Anzahl der e/a-Abschlussthreads, die derzeit keine Anforderungen verarbeiten.|  
|[GetHostOverlappedSize-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Ruft die Größe der benutzerdefinierten Daten, die der Host möchte an e/a-Anforderungen angefügt werden soll.|  
|[GetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Ruft die maximale Anzahl von Threads, die der Host-Manual kann e/a-Anforderungen ab.|  
|[GetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Ruft die minimale Anzahl von Threads, die vom Host bereitgestellten e/a-Anforderungen ab.|  
|[InitializeHostOverlapped-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Stellt den Host Möglichkeit, benutzerdefinierte Daten über eine e/a-Anforderung zu initialisieren.|  
|[SetCLRIoCompletionManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Bietet einen Schnittstellenzeiger auf den Host ein [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) -Instanz, von der CLR implementiert.|  
|[SetMaxThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Legt die maximale Anzahl von Threads, die der Host-Bereitstellung e/a-Anforderungen fest.|  
|[SetMinThreads-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Legt die minimale Anzahl von Threads, die der Host-Manual sollte auf e/a-Abschluss fest.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostIoCompletionManager` entspricht der `ICLRIoCompletionManager` Schnittstelle, die von der CLR implementiert. Die CLR ruft die Methoden der `IHostIoCompletionManager` Handles an den Ports binden, der der Host und der Host Ruft die Methoden der `ICLRIoCompletionManager` melden den Abschluss von e/a-Anforderungen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
