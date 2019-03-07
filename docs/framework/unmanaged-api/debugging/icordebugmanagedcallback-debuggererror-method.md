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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25af2c8fa3e3d49b3c2832a69f14b2691585d775
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489847"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError-Methode
Benachrichtigt den Debugger, dass ein Fehler aufgetreten ist, bei dem Versuch, ein Ereignis von der common Language Runtime (CLR) zu behandeln.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pProcess`  
 [in] Ein Zeiger auf ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, in dem das Ereignis aufgetreten ist.  
  
 `errorHR`  
 [in] Der HRESULT-Wert, der aus dem Ereignishandler zurückgegeben wurde.  
  
 `errorCode`  
 [in] Eine ganze Zahl, die den CLR-Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Der Prozess kann in den Pass-Through-Modus, je nach Art des Fehlers platziert werden.  
  
 Die `DebugError` -Rückruf gibt an, dass das Debuggen von Diensten aufgrund eines Fehlers deaktiviert wurden, sodass der Debugger die Fehlermeldung dem Benutzer verfügbar machen soll. [ICorDebugProcess:: GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) kann sicher aufrufen, aber alle anderen Methoden, einschließlich [ICorDebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), sollte nicht aufgerufen werden. Der Debugger sollte Betriebssystemfunktionen zum Beenden von Prozessen verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
