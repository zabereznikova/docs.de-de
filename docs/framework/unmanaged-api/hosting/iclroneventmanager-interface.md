---
title: ICLROnEventManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638579"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager-Schnittstelle
Bietet Methoden, mit denen den Host zu registrieren und Aufheben der Registrierung von Rückrufen für common Language Runtime (CLR)-Ereignisse.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[RegisterActionOnEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|Registriert einen Rückrufzeiger für das angegebene Ereignis.|  
|[UnregisterActionOnEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|Hebt die Registrierung eines bereits registrierten Rückrufzeigers für das angegebene Ereignis.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Registrieren und Aufheben der Registrierung Ereignisrückrufe, ruft der Host einen Verweis auf `ICLROnEventManager` durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.  
  
> [!NOTE]
>  Die beschriebenen Ereignisse [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) kann ausgelöst werden, mehr als einmal und von verschiedenen Threads ein Entladen oder das Deaktivieren der CLR signalisiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrEvent-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
