---
title: IGCThreadControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134804"
---
# <a name="igcthreadcontrol-interface"></a>IGCThreadControl-Schnittstelle
Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für eine Garbage Collection blockiert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SuspensionEnding-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|Benachrichtigt den Host, dass die Laufzeit Threads nach einem Garbage Collection oder einer anderen Unterbrechung fortsetzt.|  
|[SuspensionStarting-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.|  
|[ThreadIsBlockingForSuspension-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|Benachrichtigt den Host, dass der Thread, der den-anfordert, blockiert wird, möglicherweise für eine Garbage Collection oder eine andere Unterbrechung.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
