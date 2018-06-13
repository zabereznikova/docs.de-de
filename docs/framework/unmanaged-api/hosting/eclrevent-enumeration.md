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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d79b0c1fed0178f8463174fe981f250d6f6fb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430706"
---
# <a name="eclrevent-enumeration"></a>EClrEvent-Enumeration
Beschreibt die common Language Runtime (CLR)-Ereignisse, für die der Host Rückrufe registrieren kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`Event_ClrDisabled`|Gibt einen schwerwiegenden Fehler für die CLR.|  
|`Event_DomainUnload`|Gibt an, das Entladen eines bestimmten <xref:System.AppDomain>.|  
|`Event_MDAFired`|Gibt an, dass eine Nachricht des Assistenten für verwaltetes Debuggen (Managed Debugging Assistant, MDA) generiert wurde.|  
|`Event_StackOverflow`|Gibt an, dass ein Stapelüberlauf auftritt aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host kann Rückrufe für alle Ereignistypen, die durch beschrieben registrieren `EClrEvent` durch Aufrufen der Methoden der [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) Schnittstelle. Der Host Ruft einen Zeiger auf diese Schnittstelle ab, durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.  
  
 Die `Event_CLRDisabled` und `Event_DomainUnload` Ereignisse ausgelöst werden können, mehr als einmal und von anderen Threads um ein Entladen oder das Deaktivieren der CLR zu signalisieren.  
  
 Die `Event_MDAFired` -Ereignis ausgelöst wird die Erstellung einer [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) -Instanz, die die Details der MDA-Meldung enthält. Weitere Informationen über MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
