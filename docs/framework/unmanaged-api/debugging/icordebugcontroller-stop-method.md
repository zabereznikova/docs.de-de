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
ms.openlocfilehash: 83bb52f7f2035605914e2fe72ce2daf78de5bc1e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749904"
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop-Methode
Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwTimeoutIgnored`  
 Nicht verwendet.  
  
## <a name="remarks"></a>Hinweise  
 `Stop` Führt einen kooperativen beenden für alle Threads, die ausgeführt wird, die verwaltet Code im Prozess an. Während einer Debugsitzung ausschließlich verwalteten nicht verwaltete Threads können weiterhin ausführen (wird jedoch blockiert, wenn Sie versuchen, verwalteten Code aufrufen). Während einer Interop-Debugsitzung werden auch nicht verwaltete Threads beendet werden. Die `dwTimeoutIgnored` Wert wird gegenwärtig ignoriert und als UNENDLICH (-1) behandelt. Wenn das kooperative Beenden aufgrund eines Deadlocks ein Fehler auftritt, werden alle Threads angehalten und E_TIMEOUT zurückgegeben.  
  
> [!NOTE]
>  `Stop` ist die nur synchrone Methode in der Debug-API. Wenn `Stop` S_OK zurückgibt, wird der Prozess wurde beendet. Benachrichtigt Listener über das Beenden ist kein Rückruf erhält. Der Debugger muss Aufrufen [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , der Prozess fortgesetzt werden kann.  
  
 Der Debugger verwaltet einen Stop-Zähler. Wenn der Zähler auf Null geht, wird der Controller wieder fortgesetzt. Jeder Aufruf von `Stop` oder jedem gesendeten Rückruf wird der Zähler erhöht. Jeder Aufruf von `ICorDebugController::Continue` verringert den Zähler.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
