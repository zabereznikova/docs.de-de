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
ms.openlocfilehash: 3a107176e48a88a0a04534f7044c1e416caf4091
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788892"
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop-Methode
Führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `dwTimeoutIgnored`  
 Nicht verwendet.  
  
## <a name="remarks"></a>Hinweise  
 `Stop` führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen. Während einer reinen Debugsitzung können nicht verwaltete Threads weiterhin ausgeführt werden (Sie werden jedoch blockiert, wenn verwalteter Code aufgerufen wird). Während einer Interop-Debugsitzung werden auch nicht verwaltete Threads angehalten. Der `dwTimeoutIgnored` Wert wird derzeit ignoriert und als unendlich behandelt (-1). Wenn der Kooperative Vorgang aufgrund eines Deadlocks fehlschlägt, werden alle Threads angehalten, und E_TIMEOUT wird zurückgegeben.  
  
> [!NOTE]
> `Stop` ist die einzige synchrone Methode in der Debug-API. Wenn `Stop` S_OK zurückgibt, wird der Prozess beendet. Es wird kein Rückruf zum Benachrichtigen von Listenern über das Ende angegeben. Der Debugger muss [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) aufrufen, damit der Vorgang fortgesetzt werden kann.  
  
 Der Debugger behält einen Haltepunkt bei. Wenn der Wert NULL ist, wird der Controller fortgesetzt. Jeder Aufrufe von `Stop` oder jeder gesendete Rückruf erhöht den-Wert. Jeder `ICorDebugController::Continue` Aufrufe verringert den Zählers.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
