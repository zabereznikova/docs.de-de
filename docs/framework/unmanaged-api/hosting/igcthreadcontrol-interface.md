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
ms.openlocfilehash: 9296aedf24979624c3d7357a4d51be835716a16f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438027"
---
# <a name="igcthreadcontrol-interface"></a>IGCThreadControl-Schnittstelle
Stellt Methoden für die Einbeziehung in die Planung von Threads, die ansonsten für eine Garbagecollection blockiert werden würde.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SuspensionEnding-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|Benachrichtigt den Host an, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.|  
|[SuspensionStarting-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|Benachrichtigt den Host, dass die Common Language Runtime einen Thread anhalten für eine Garbagecollection oder eine andere Unterbrechung beginnt.|  
|[ThreadIsBlockingForSuspension-Methode](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|Benachrichtigt den Host, der Thread, die den Aufruf zu blockieren, möglicherweise für eine Garbagecollection oder eine andere Unterbrechung ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
