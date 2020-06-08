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
ms.openlocfilehash: 2f83bc5b114b746958f936c311efa823d88441d1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503886"
---
# <a name="wait_option-enumeration"></a>WAIT_OPTION-Enumeration
Enthält Werte, die angeben, welche Aktion ein Host durchführen soll, wenn ein vom Common Language Runtime (CLR)-Block angeforderter Vorgang ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Benachrichtigt den Host, dass die Aufgabe ausgelöst werden soll, wenn die CLR die [IHostTask:: Alert](ihosttask-alert-method.md) -Methode aufruft.|  
|`WAIT_MSGPUMP`|Benachrichtigt den Host, dass er Nachrichten auf dem aktuellen Betriebssystem Thread verschieben muss, wenn der Thread blockiert wird. Die Laufzeit gibt diesen Wert nur in einem <xref:System.Threading.ApartmentState.STA> Thread an.|  
|`WAIT_NOTINDEADLOCK`|Benachrichtigt den Host, dass die angegebene Synchronisierungs Anforderung nicht von einem Host getrennt werden kann. Das heißt, der Host kann nicht zurückgeben `HOST_E_DEADLOCK` .|  
  
## <a name="remarks"></a>Bemerkungen  
 Die [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) -und [IHostTaskManager:: switchdetask](ihosttaskmanager-switchtotask-method.md) -Methoden akzeptieren beide einen Parameter dieses Typs.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Hosten von Enumerationen](hosting-enumerations.md)
