---
title: EClrEvent-Enumeration
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 388f0de26983f8bb876f40a527f60d8bc59191a3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616346"
---
# <a name="eclrevent-enumeration"></a>EClrEvent-Enumeration
Beschreibt die Common Language Runtime (CLR)-Ereignisse, für die der Host Rückrufe registrieren kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`Event_ClrDisabled`|Gibt einen schwerwiegenden CLR-Fehler an.|  
|`Event_DomainUnload`|Gibt das Entladen eines bestimmten an <xref:System.AppDomain> .|  
|`Event_MDAFired`|Gibt an, dass eine MDA-Nachricht (Managed Debug Assistant) generiert wurde.|  
|`Event_StackOverflow`|Gibt an, dass ein Stapelüberlauf Fehler aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host kann Rückrufe für jeden der Ereignis Typen registrieren, die durch den `EClrEvent` Aufruf der Methoden der [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) -Schnittstelle beschrieben werden. Der Host erhält einen Zeiger auf diese Schnittstelle, indem er die [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode aufruft.  
  
 Das `Event_CLRDisabled` -Ereignis und das- `Event_DomainUnload` Ereignis können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um eine Entladung oder die Deaktivierung der CLR zu signalisieren.  
  
 Das- `Event_MDAFired` Ereignis löst die Erstellung einer [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) -Instanz aus, die die Details der MDA-Nachricht enthält. Weitere Informationen zu MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IActionOnCLREvent-Schnittstelle](iactiononclrevent-interface.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
