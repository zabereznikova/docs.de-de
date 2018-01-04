---
title: ICLROnEventManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager
helpviewer_keywords: ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a19a3daf72cdfa493b09fa984fe7b50865ed30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager-Schnittstelle
Enthält Methoden, die es dem Host zu registrieren und Aufheben der Rückrufe für common Language Runtime (CLR) Ereignisse ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[RegisterActionOnEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|Registriert einen Rückrufzeiger für das angegebene Ereignis an.|  
|[UnregisterActionOnEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|Hebt die Registrierung eines zuvor registrierten Rückrufzeigers für das angegebene Ereignis.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Registrieren und Aufheben der Registrierung Ereignisrückrufe, ruft der Host einen Verweis auf `ICLROnEventManager` durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.  
  
> [!NOTE]
>  Die Ereignisse, die durch beschrieben [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) kann ausgelöst werden, mehr als einmal und von anderen Threads um ein Entladen oder das Deaktivieren der CLR zu signalisieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [EClrEvent-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
