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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8a8f84d3dfd8f1e64197078d7e20d2aebef2323
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761227"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection-Methode
Benachrichtigt den Debugger an, dass der Satz von Aufgaben im Zusammenhang mit der angegebenen Verbindung geändert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pProcess`  
 [in] Ein Zeiger auf ein "ICorDebugProcess"-Objekt, das den Prozess mit der die geänderte Verbindung darstellt.  
  
 `dwConnectionId`  
 [in] Die ID der Verbindung, die geändert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Ein `ChangeConnection` Rückruf wird in den folgenden Fällen ausgelöst werden:  
  
- Wenn Fügt einen Debugger an einen Prozess aus, der Verbindungen enthält ein. In diesem Fall die Laufzeit generiert und ein [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) Ereignis und einem `ChangeConnection` Ereignis für jede Verbindung im Prozess. Ein `ChangeConnection` Ereignis wird generiert, für jede vorhandene Verbindung, unabhängig davon, ob die Verbindung der Satz von Aufgaben seit ihrer Erstellung geändert wurde.  
  
- Wenn ein Host ruft [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in die [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
 Der Debugger sollten alle Threads im Prozess übernimmt diese die neuen Änderungen überprüfen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
