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
ms.openlocfilehash: dd148d23d6e29f03052d3bbf1fcd5d02fb332a0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729849"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Diese Laufzeit verfügt über ein verwaltetes Debugger-Ereignis, das nicht aufgefangen werden soll. Im Abschnitt "Hinweise" finden Sie Informationen zum Unterschied zwischen catch-up-und Non-catch-up-Ereignissen.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Das ausstehende verwaltete Ereignis ist eine- <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> Anforderung.|  
  
## <a name="remarks"></a>Hinweise  

 Zu den Aufhol Ereignissen zählen Prozess-, Anwendungs Domänen-, Assembly-, Modul-und Thread Erstellungs Benachrichtigungen, mit denen der Debugger nach dem Anfügen an einen Prozess in den aktuellen Zustand versetzt wird. Nicht-catch-Ereignisse, die durch das-Flag angegeben werden `CLR_DEBUGGING_MANAGED_EVENT_PENDING` , schließen alle anderen debuggerereignisse ein, z. b. Ausnahmen und MDA-Benachrichtigungen (Managed Debug Assistant).  
  
 `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`Mit dem-Flag kann die Laufzeit zwischen einer Beendigungs Ausnahme und einer Anforderung zum Anfügen eines verwalteten Debuggers unterscheiden, der abgebrochen werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. idl, MetaHost. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
- [Debuggen](index.md)
