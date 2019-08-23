---
title: ICorDebugController::Stop-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 363d8f7d8cf960fb23210225c4545f73d597d663
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912841"
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop-Methode
Führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwTimeoutIgnored`  
 Wird nicht verwendet.  
  
## <a name="remarks"></a>Hinweise  
 `Stop`führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen. Während einer reinen Debugsitzung können nicht verwaltete Threads weiterhin ausgeführt werden (Sie werden jedoch blockiert, wenn verwalteter Code aufgerufen wird). Während einer Interop-Debugsitzung werden auch nicht verwaltete Threads angehalten. Der `dwTimeoutIgnored` Wert wird derzeit ignoriert und als unendlich behandelt (-1). Wenn der Kooperative Vorgang aufgrund eines Deadlocks fehlschlägt, werden alle Threads angehalten, und E_TIMEOUT wird zurückgegeben.  
  
> [!NOTE]
> `Stop`ist die einzige synchrone Methode in der Debug-API. Wenn `Stop` S_OK zurückgibt, wird der Prozess beendet. Es wird kein Rückruf zum Benachrichtigen von Listenern über das Ende angegeben. Der Debugger muss [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufrufen, damit der Vorgang fortgesetzt werden kann.  
  
 Der Debugger behält einen Haltepunkt bei. Wenn der Wert NULL ist, wird der Controller fortgesetzt. Jeder-Rückruf `Stop` oder jeder verteilte Rückruf erhöht den-Wert. Jeder-aufrufswert `ICorDebugController::Continue` verringert den-Wert.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
