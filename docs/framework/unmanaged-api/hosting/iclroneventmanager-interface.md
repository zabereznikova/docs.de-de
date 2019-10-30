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
ms.openlocfilehash: a1b22e77fe20d5e2d755efcd7a63c8f2bdc781e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140842"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager-Schnittstelle
Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für Common Language Runtime (CLR)-Ereignisse zu registrieren und die Registrierung aufzuheben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[RegisterActionOnEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|Registriert einen Rückruf Zeiger für das angegebene Ereignis.|  
|[UnregisterActionOnEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|Hebt die Registrierung eines zuvor registrierten Rückruf Zeigers für das angegebene Ereignis auf.|  
  
## <a name="remarks"></a>Hinweise  
 Um Ereignis Rückrufe zu registrieren und die Registrierung aufzuheben, ruft der Host einen Verweis auf `ICLROnEventManager` durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode ab.  
  
> [!NOTE]
> Die von [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) beschriebenen Ereignisse können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um ein Entladen oder das Deaktivieren der CLR zu signalisieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrEvent-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
