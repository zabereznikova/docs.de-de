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
ms.openlocfilehash: 5a4ebf65dfaaa487e87f3fd78e54c468c7e24a89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697232"
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
  
- Wenn ein Debugger an einen Prozess angefügt wird, der Verbindungen enthält. In diesem Fall generiert und versendet die Laufzeit ein `CreateConnection` -Ereignis und ein [ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) -Ereignis für jede Verbindung im Prozess.  
  
- Wenn ein Host [ICLRDebugManager:: BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in der [Hosting-API](../hosting/index.md)aufruft.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
