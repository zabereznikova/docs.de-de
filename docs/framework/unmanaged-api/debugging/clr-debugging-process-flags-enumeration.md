---
title: CLR_DEBUGGING_PROCESS_FLAGS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_PROCESS_FLAGS
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords: CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5040b1e1eb7ec4bd814329de156fcdfeb9c383c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Diese Laufzeit ist ein verwalteter Debugger Catch-nach-oben-Ereignis zu senden. Finden Sie im Abschnitt "Hinweise" für die Unterscheidung zwischen hervorgehobene und Catch-nach-oben-Ereignissen.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Das verwaltete Ereignis aussteht ist eine <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> Anforderung.|  
  
## <a name="remarks"></a>Hinweise  
 Synchronisieren von Ereignissen enthalten Prozess, die Anwendungsdomäne, Assembly, Modul und Thread Erstellung Benachrichtigungen, die den Debugger bis zu den aktuellen Zustand zu bringen, nach dem Anfügen an einen Prozess hat. Nicht-Catch-Up-Ereignisse, die ersichtlich sind die `CLR_DEBUGGING_MANAGED_EVENT_PENDING` kennzeichnen, schließen Sie alle anderen Debugger-Ereignissen, z. B. Ausnahmen und managed debugging Assistant, Assistent für (verwaltetes Debuggen MDA) Benachrichtigungen.  
  
 Die `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` Flag kann die Laufzeit eine abschließende Ausnahme und eine Anforderung an einen verwalteten Debugger anfügen, die abgebrochen werden kann, unterscheiden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Metahost.idl, Metahost.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
