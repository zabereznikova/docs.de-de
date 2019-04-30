---
title: CLR_DEBUGGING_PROCESS_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8321e5aeba435ca5f1398a9cb827a93ae821d686
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996358"
---
# <a name="clrdebuggingprocessflags-enumeration"></a>CLR_DEBUGGING_PROCESS_FLAGS-Enumeration
Enthält Werte, mit denen, die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Diese Laufzeit ist ein verwalteter Debugger Catch-nach-oben-Ereignis senden. Finden Sie im Abschnitt "Hinweise" für die Unterscheidung zwischen sich und nicht-Catch-Up-Ereignissen.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Das verwaltete Ereignis aussteht ist eine <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> Anforderung.|  
  
## <a name="remarks"></a>Hinweise  
 Synchronisieren von Ereignissen enthalten Prozess, die Anwendungsdomäne, Assembly, Modul und Thread Erstellung Benachrichtigungen, die den Debugger bis zu den aktuellen Zustand zu bringen, nach dem Anfügen an einen Prozess hat. Nicht-Catch-Up-Ereignisse, die angegeben wurden die `CLR_DEBUGGING_MANAGED_EVENT_PENDING` kennzeichnen, umfassen alle anderen Debugger-Ereignisse, z. B. Ausnahmen und managed debugging Assistant, Assistent für (verwaltetes Debuggen MDA) Benachrichtigungen.  
  
 Die `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` Flag kann die Laufzeit unterscheiden, der eine abschließende Ausnahme und Sie werden aufgefordert, einen verwalteten Debugger anzufügen, die abgebrochen werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Metahost.idl, Metahost.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
