---
title: CorDebugUserState-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1ee5044c2223d3ff90cf10b53cad4e1b353d87c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726509"
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState-Enumeration
Gibt den Benutzerzustand eines Threads an.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>Member  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|Ein Beenden des Threads wurde angefordert.|  
|`USER_SUSPEND_REQUESTED`|Führt zu eine Unterbrechung des Threads wurde angefordert.|  
|`USER_BACKGROUND`|Der Thread wird im Hintergrund ausgeführt.|  
|`USER_UNSTARTED`|Der Thread wurde nicht gestartet, ausgeführt.|  
|`USER_STOPPED`|Der Thread wurde beendet.|  
|`USER_WAIT_SLEEP_JOIN`|Der Thread wartet darauf, dass ein anderer Thread eine Aufgabe auszuführen.|  
|`USER_SUSPENDED`|Der Thread wurde angehalten.|  
|`USER_UNSAFE_POINT`|Der Thread ist an einem unsicheren Punkt. Ist der Thread zu einem Zeitpunkt in der Ausführung, in dem sie die automatische speicherbereinigung blockiert möglicherweise.<br /><br /> Debuggen von Ereignisse von unsicheren Punkten verteilt werden können, aber einen Thread an einem unsicheren Punkt angehalten wird sehr wahrscheinlich einen Deadlock bis der Thread fortgesetzt wird. Die sicheren und unsicheren Punkte werden durch den just-in-Time (JIT) und die Garbage Collection-Implementierung bestimmt.|  
|`USER_THREADPOOL`|Der Thread ist aus dem Threadpool.|  
  
## <a name="remarks"></a>Hinweise  
 Der Benutzerzustand eines Threads ist der Zustand, den der Thread wurde bei der Überprüfung durch den Debugger. Ein Thread möglicherweise eine Kombination von Benutzerstatus.  
  
 Verwenden der [ICorDebugThread:: GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) Methode, um den Benutzerzustand eines Threads abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
