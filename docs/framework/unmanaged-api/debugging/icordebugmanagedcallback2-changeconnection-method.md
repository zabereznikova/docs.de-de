---
title: ICorDebugManagedCallback2::ChangeConnection-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 4558074bc23334bd697461a00ccb31db3e3fe397
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130601"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection-Methode
Benachrichtigt den Debugger, dass sich der Satz der Tasks, die der angegebenen Verbindung zugeordnet sind, geändert hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pProcess`  
 in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der die geänderte Verbindung enthält.  
  
 `dwConnectionId`  
 in Die ID der Verbindung, die geändert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Ein `ChangeConnection` Rückruf wird in einem der folgenden Fälle ausgelöst:  
  
- Wenn ein Debugger an einen Prozess angefügt wird, der Verbindungen enthält. In diesem Fall generiert und verteilt die Common Language Runtime ein [ICorDebugManagedCallback2:: forateconnetction](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) -Ereignis und ein `ChangeConnection`-Ereignis für jede Verbindung im Prozess. Ein `ChangeConnection` Ereignis wird für jede vorhandene Verbindung generiert, unabhängig davon, ob der Satz von Tasks der Verbindung seit seiner Erstellung geändert wurde.  
  
- Wenn ein Host [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in der [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md)aufruft.  
  
 Der Debugger sollte alle Threads im Prozess Scannen, um die neuen Änderungen zu überprüfen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
