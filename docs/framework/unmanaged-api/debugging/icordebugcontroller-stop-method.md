---
title: ICorDebugController::Stop-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a8699a54814b37cc03404b72330812f3eb2b2f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop-Methode
Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwTimeoutIgnored`  
 Nicht verwendet.  
  
## <a name="remarks"></a>Hinweise  
 `Stop`Führt einen kooperativen Stop für alle Threads ausführen verwaltet-Code im Prozess an. Während einer Debugsitzung nur verwaltet nicht verwaltete Threads möglicherweise weiterhin ausgeführt (jedoch wird beim Aufrufen von verwalteten Codes blockiert werden). Während einer Debugsitzung Interop werden auch nicht verwaltete Threads beendet werden. Die `dwTimeoutIgnored` Wert wird derzeit ignoriert und als INFINITE (-1) behandelt. Wenn das kooperative Beenden aufgrund eines Deadlocks fehlschlägt, werden alle Threads angehalten, und E_TIMEOUT zurückgegeben.  
  
> [!NOTE]
>  `Stop`ist die einzige synchrone Methode in der Debug-API. Wenn `Stop` S_OK zurückgibt, wird der Prozess beendet wird. Es erfolgt kein Rückruf benachrichtigt Listener über die Beendigung. Der Debugger muss Aufrufen [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , der Prozess fortgesetzt werden kann.  
  
 Der Debugger verwaltet einen Leistungsindikator beenden. Wenn der Zähler auf 0 (null) ist, wird der Controller fortgesetzt. Jeder Aufruf von `Stop` oder jedem gesendeten Rückruf wird der Zähler erhöht. Jeder Aufruf von `ICorDebugController::Continue` dekrementiert den Zähler.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
