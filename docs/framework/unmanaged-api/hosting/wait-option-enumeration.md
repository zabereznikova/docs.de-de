---
title: WAIT_OPTION-Enumeration
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb37394799db39baa406ef332066d5ebb2dbf19d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441928"
---
# <a name="waitoption-enumeration"></a>WAIT_OPTION-Enumeration
Enthält Werte, die darauf, dass die Aktion eines Hosts durchführen soll, wenn ein Vorgang hinweisen, durch die common Language Runtime (CLR) Textblöcke angefordert.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Benachrichtigt den Host, dass die Aufgabe aktiviert werden soll, wenn die CLR ruft die [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) Methode.|  
|`WAIT_MSGPUMP`|Benachrichtigt den Host an, dass Nachrichten auf dem aktuellen Betriebssystemthread verteilt werden müssen, wenn der Thread blockiert wird. Die Common Language Runtime gibt diesen Wert nur auf eine <xref:System.Threading.ApartmentState.STA> Thread.|  
|`WAIT_NOTINDEADLOCK`|Benachrichtigt den Host, dass die angegebenen synchronisierungsanforderung von einem Host aufgeteilt werden kann. Der Host kann nicht zurückkehren, d. h. `HOST_E_DEADLOCK`.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) und [IHostTaskManager:: SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) beide Methoden akzeptieren einen Parameter dieses Typs.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
