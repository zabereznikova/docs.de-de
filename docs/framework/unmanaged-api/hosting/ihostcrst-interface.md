---
title: IHostCrst-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 939f100e8ee386642a29c33827a8339caf0467b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193186"
---
# <a name="ihostcrst-interface"></a>IHostCrst-Schnittstelle
Dient als Darstellung des Hosts in einem kritischen Abschnitt für das Threading teilweise.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Enter-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Gibt den kritischen Abschnitt.|  
|[Leave-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Lässt den kritischen Abschnitt.|  
|[SetSpinCount-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Legt die Spin-Anzahl für den kritischen Abschnitt fest.|  
|[TryEnter-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Versucht, den kritischen Abschnitt und Berichte erfolgreich oder fehlerhaft direkt eingeben.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostCrst` bietet die common Language Runtime (CLR), um direkt mit der Darstellung eines kritischen Abschnitts, die Hosts kommunizieren mithilfe von Win32-Funktionen wie z. B. `EnterCriticalSection` oder `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
