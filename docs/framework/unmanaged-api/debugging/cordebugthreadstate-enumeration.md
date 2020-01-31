---
title: CorDebugThreadState-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 69a8aabd1d79bb9bb4248259c99124ce50677600
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789245"
---
# <a name="cordebugthreadstate-enumeration"></a>CorDebugThreadState-Enumeration
Gibt den Zustand eines Threads zum Debuggen an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`THREAD_RUN`|Der Thread wird frei ausgeführt, es sei denn, ein Debug-Ereignis tritt auf|  
|`THREAD_SUSPEND`|Der Thread kann nicht ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger verwendet die `CorDebugThreadState`-Enumeration, um die Ausführung eines Threads zu steuern. Der Status eines Threads kann mithilfe der [ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) -Methode oder der [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) -Methode festgelegt werden.  
  
 Ein für die Hosting- [API](../../../../docs/framework/unmanaged-api/hosting/index.md) bereitgestellter Rückruf ermöglicht das Senden von Nachrichten, sodass ein unterbrochener Status nicht erforderlich ist.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](debugging-enumerations.md)
