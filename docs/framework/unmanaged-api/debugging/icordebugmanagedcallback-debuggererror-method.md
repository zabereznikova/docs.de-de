---
title: ICorDebugManagedCallback::DebuggerError-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: 9b96c0a2eca543b9e01ccf92b271b1aa7003c5c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781947"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError-Methode
Benachrichtigt den Debugger, dass beim Verarbeiten eines Ereignisses aus dem Common Language Runtime (CLR) ein Fehler aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pProcess`  
 in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem das Ereignis aufgetreten ist.  
  
 `errorHR`  
 in Der HRESULT-Wert, der vom Ereignishandler zurückgegeben wurde.  
  
 `errorCode`  
 in Eine ganze Zahl, die den CLR-Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Der Prozess kann je nach Art des Fehlers in den Pass-Through-Modus versetzt werden.  
  
 Der `DebugError` Rückruf gibt an, dass debuggingdienste aufgrund eines Fehlers deaktiviert wurden. Daher sollten Debugger dem Benutzer die Fehlermeldung zur Verfügung stellen. [ICorDebugProcess:: GetId](icordebugprocess-getid-method.md) kann sicher aufgerufen werden, aber alle anderen Methoden, einschließlich [ICorDebug::](icordebug-terminate-method.md)End, dürfen nicht aufgerufen werden. Der Debugger sollte Betriebssystemfunktionen zum Beenden von Prozessen verwenden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
