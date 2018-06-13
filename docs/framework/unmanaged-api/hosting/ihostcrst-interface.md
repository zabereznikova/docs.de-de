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
ms.openlocfilehash: 88f2ef8299911905d651ad5c3076dc9c74f397f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438918"
---
# <a name="ihostcrst-interface"></a>IHostCrst-Schnittstelle
Dient als Host Darstellung eines kritischen Abschnitts für threading.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Enter-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Wechselt in den kritischen Abschnitt aus.|  
|[Leave-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Verlässt die kritischen Abschnitt.|  
|[SetSpinCount-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Legt die Anzahl der Drehfeld für die kritischen Abschnitts.|  
|[TryEnter-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Versucht, den kritischen Abschnitt und berichtet über Erfolg oder Fehler sofort eingeben.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostCrst` ermöglicht die common Language Runtime (CLR) die direkte Kommunikation mit dem Host-Darstellung eines kritischen Abschnitts, anstatt Win32-Funktionen wie z. B. `EnterCriticalSection` oder `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
