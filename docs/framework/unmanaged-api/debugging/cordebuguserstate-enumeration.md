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
ms.openlocfilehash: 968874a46279b7eac651d45c3890429a326651b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726950"
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState-Enumeration

Gibt den Benutzerzustand eines Threads an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|Die Beendigung des Threads wurde angefordert.|  
|`USER_SUSPEND_REQUESTED`|Es wurde eine Unterbrechung des Threads angefordert.|  
|`USER_BACKGROUND`|Der Thread wird im Hintergrund ausgeführt.|  
|`USER_UNSTARTED`|Der Thread wurde nicht gestartet.|  
|`USER_STOPPED`|Der Thread wurde beendet.|  
|`USER_WAIT_SLEEP_JOIN`|Der Thread wartet auf den Abschluss einer Aufgabe durch einen anderen Thread.|  
|`USER_SUSPENDED`|Der Thread wurde unterbrochen.|  
|`USER_UNSAFE_POINT`|Der Thread befindet sich an einem unsicheren Punkt. Das heißt, der Thread befindet sich an einem Punkt in der Ausführung, an dem er Garbage Collection blockieren kann.<br /><br /> Debugereignisse können von unsicheren Punkten aus verteilt werden, aber das Anhalten eines Threads an einem unsicheren Punkt führt wahrscheinlich zu einem Deadlock, bis der Thread fortgesetzt wird. Die sicheren und unsicheren Punkte werden durch die Just-in-time (JIT)-und Garbage Collection-Implementierung festgelegt.|  
|`USER_THREADPOOL`|Der Thread wird aus dem Thread Pool entfernt.|  
  
## <a name="remarks"></a>Hinweise  

 Der Benutzer Zustand eines Threads ist der Zustand, den der Thread aufweist, wenn er vom Debugger überprüft wird. Ein Thread kann eine Kombination aus Benutzer Zuständen aufweisen.  
  
 Verwenden Sie die [ICorDebugThread:: GetUserState](icordebugthread-getuserstate-method.md) -Methode, um den Benutzer Zustand eines Threads abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
