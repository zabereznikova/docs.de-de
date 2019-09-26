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
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274111"
---
# <a name="clr_debugging_process_flags-enumeration"></a>CLR_DEBUGGING_PROCESS_FLAGS-Enumeration
Stellt Werte bereit, die von der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Diese Laufzeit verfügt über ein verwaltetes Debugger-Ereignis, das nicht aufgefangen werden soll. Im Abschnitt "Hinweise" finden Sie Informationen zum Unterschied zwischen catch-up-und Non-catch-up-Ereignissen.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Das ausstehende verwaltete Ereignis ist eine <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> -Anforderung.|  
  
## <a name="remarks"></a>Hinweise  
 Zu den Aufhol Ereignissen zählen Prozess-, Anwendungs Domänen-, Assembly-, Modul-und Thread Erstellungs Benachrichtigungen, mit denen der Debugger nach dem Anfügen an einen Prozess in den aktuellen Zustand versetzt wird. Nicht-catch-Ereignisse, die durch das `CLR_DEBUGGING_MANAGED_EVENT_PENDING` -Flag angegeben werden, schließen alle anderen debuggerereignisse ein, z. b. Ausnahmen und MDA-Benachrichtigungen (Managed Debug Assistant).  
  
 Mit `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` dem-Flag kann die Laufzeit zwischen einer Beendigungs Ausnahme und einer Anforderung zum Anfügen eines verwalteten Debuggers unterscheiden, der abgebrochen werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. idl, MetaHost. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](debugging-enumerations.md)
- [Debuggen](index.md)
