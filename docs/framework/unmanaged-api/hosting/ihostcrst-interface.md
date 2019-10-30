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
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130526"
---
# <a name="ihostcrst-interface"></a>IHostCrst-Schnittstelle
Dient als Host Darstellung eines kritischen Abschnitts zum Threading.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Enter-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Wechselt in den kritischen Abschnitt.|  
|[Leave-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Verlässt den kritischen Abschnitt.|  
|[SetSpinCount-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Legt die drehanzahl für den kritischen Abschnitt fest.|  
|[TryEnter-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Versucht, den kritischen Abschnitt einzugeben, und meldet einen Erfolg oder Fehler sofort.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostCrst` ermöglicht es dem Common Language Runtime (CLR), direkt mit der Darstellung eines kritischen Abschnitts des Hosts zu kommunizieren, anstatt Win32-Funktionen wie `EnterCriticalSection` oder `LeaveCriticalSection`zu verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
