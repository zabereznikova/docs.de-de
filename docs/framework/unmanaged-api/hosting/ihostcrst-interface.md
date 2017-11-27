---
title: IHostCrst-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 `IHostCrst`ermöglicht die common Language Runtime (CLR) die direkte Kommunikation mit dem Host-Darstellung eines kritischen Abschnitts, anstatt Win32-Funktionen wie z. B. `EnterCriticalSection` oder `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
