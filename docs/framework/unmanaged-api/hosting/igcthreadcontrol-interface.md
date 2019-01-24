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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a053dba8f5fb8f4144968e08b6c65412f510193
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727494"
---
# <a name="igcthreadcontrol-interface"></a>IGCThreadControl-Schnittstelle
Stellt Methoden für die Teilnahme an der Planung von Threads, die für eine Garbagecollection andernfalls blockiert würden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SuspensionEnding-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|Benachrichtigt den Host, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.|  
|[SuspensionStarting-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|Benachrichtigt den Host, dass die Laufzeit eine Threadunterbrechung für eine Garbagecollection oder einer anderen Unterbrechung beginnt.|  
|[ThreadIsBlockingForSuspension-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|Benachrichtigt den Host an, dass der Thread, der den Aufruf zu blockieren, z. B. für eine Garbagecollection oder einer anderen Unterbrechung.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
