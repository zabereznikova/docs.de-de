---
title: IDebuggerThreadControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
ms.openlocfilehash: 2268fce5d3ca732d852edfdb6f0edf63117df363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684212"
---
# <a name="idebuggerthreadcontrol-interface"></a>IDebuggerThreadControl-Schnittstelle

Stellt Methoden bereit, mit denen der Host über die Blockierung und Aufhebung der Blockierung von Threads durch die Debugdienste benachrichtigt wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ThreadIsBlockingForDebugger-Methode](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|Benachrichtigt den Host, dass der Thread, der diesen Rückruf sendet, innerhalb der Debugdienste blockiert wird.|  
|[ReleaseAllRuntimeThreads-Methode](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|Benachrichtigt den Host, dass die debuggingdienste alle blockierten Threads freigeben.|  
|[StartBlockingForDebugger-Methode](idebuggerthreadcontrol-startblockingfordebugger-method.md)|Benachrichtigt den Host, dass die debuggingdienste damit beginnen, alle Threads zu blockieren.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
