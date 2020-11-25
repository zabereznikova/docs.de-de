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
ms.openlocfilehash: 75ad8670008242008aa344835143ff9b2add0a6c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719592"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager-Schnittstelle

Stellt Methoden bereit, die dem Common Language Runtime (CLR) die Interaktion mit e/a-Abschlussports ermöglichen, die vom Host bereitgestellt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Bind-Methode](ihostiocompletionmanager-bind-method.md)|Bindet ein Handle an einen e/a-Abschlussport.|  
|[CloseIoCompletionPort-Methode](ihostiocompletionmanager-closeiocompletionport-method.md)|Schließt einen Port, der durch einen früheren-Aufrufsatz erstellt wurde `CreateIoCompletionPort` .|  
|[CreateIoCompletionPort-Methode](ihostiocompletionmanager-createiocompletionport-method.md)|Fordert an, dass der Host einen neuen e/a-Abschlussport erstellt.|  
|[GetAvailableThreads-Methode](ihostiocompletionmanager-getavailablethreads-method.md)|Ruft die Anzahl der e/a-Abschluss Threads ab, die derzeit keine Anforderungen verarbeiten.|  
|[GetHostOverlappedSize-Methode](ihostiocompletionmanager-gethostoverlappedsize-method.md)|Ruft die Größe aller benutzerdefinierten Daten ab, die der Host an e/a-Anforderungen anfügen soll.|  
|[GetMaxThreads-Methode](ihostiocompletionmanager-getmaxthreads-method.md)|Ruft die maximale Anzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen in hohem Maß abrufen kann.|  
|[GetMinThreads-Methode](ihostiocompletionmanager-getminthreads-method.md)|Ruft die Mindestanzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen bereitstellt.|  
|[InitializeHostOverlapped-Methode](ihostiocompletionmanager-initializehostoverlapped-method.md)|Bietet dem Host die Möglichkeit, benutzerdefinierte Daten zu einer e/a-Anforderung zu initialisieren.|  
|[SetCLRIoCompletionManager-Methode](ihostiocompletionmanager-setclriocompletionmanager-method.md)|Stellt dem Host einen Schnittstellen Zeiger auf eine [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) -Instanz bereit, die von der CLR implementiert wird.|  
|[SetMaxThreads-Methode](ihostiocompletionmanager-setmaxthreads-method.md)|Legt die maximale Anzahl von Threads fest, die der Host Dienst-e/a-Anforderungen zugeordnet.|  
|[SetMinThreads-Methode](ihostiocompletionmanager-setminthreads-method.md)|Legt die Mindestanzahl von Threads fest, die der Host für die e/a-Vervollständigung in hohem Maß beachten soll.|  
  
## <a name="remarks"></a>Hinweise  

 `IHostIoCompletionManager` entspricht der `ICLRIoCompletionManager` von der CLR implementierten Schnittstelle. Die CLR ruft die Methoden von `IHostIoCompletionManager` auf, um Handles an die vom Host bereitgestellten Ports zu binden, und der Host ruft die Methoden von `ICLRIoCompletionManager` auf, um den Abschluss von e/a-Anforderungen zu melden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
