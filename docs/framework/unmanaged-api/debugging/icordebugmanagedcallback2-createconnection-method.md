---
title: ICorDebugManagedCallback2::CreateConnection-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: d83ad530c8a61c2bfc38fb46ad2a33ef8d5077d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130590"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a>ICorDebugManagedCallback2::CreateConnection-Methode
Benachrichtigt den Debugger, dass eine neue Verbindung erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pProcess`  
 in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem die Verbindung erstellt wurde.  
  
 `dwConnectionId`  
 in Die ID der neuen Verbindung.  
  
 `pConnName`  
 in Ein Zeiger auf den Namen der neuen Verbindung.  
  
## <a name="remarks"></a>Hinweise  
 Ein `CreateConnection` Rückruf wird in einem der folgenden Fälle ausgelöst:  
  
- Wenn ein Debugger an einen Prozess angefügt wird, der Verbindungen enthält. In diesem Fall generiert und versendet die Common Language Runtime für jede Verbindung im Prozess ein `CreateConnection` Ereignis und ein [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) -Ereignis.  
  
- Wenn ein Host [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in der [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md)aufruft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
