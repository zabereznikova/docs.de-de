---
title: ICorDebugController::Continue-Methode
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
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6a96145801aa8ef6482e30e9c00b763d2501f36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue-Methode
Setzt die Ausführung des verwalteten Threads nach einem Aufruf von [stoppen Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fIsOutOfBand`  
 [in] Legen Sie auf `true` Wenn von einem Out-of-Band-Ereignis; Sie den Vorgang fortsetzen, andernfalls legen Sie auf `false`.  
  
## <a name="remarks"></a>Hinweise  
 `Continue`wird der Prozess fortgesetzt wird, nach einem Aufruf von der `ICorDebugController::Stop` Methode.  
  
 Rufen Sie beim Debuggen im gemischten Modus verwenden führen, `Continue` auf die Win32-Ereignis thread auf, wenn Sie von einem Out-of-Band-Ereignis fortsetzen möchten.  
  
 Ein *in-Band-Ereignis* ist ein verwaltetes Ereignis oder ein normaler nicht verwaltetes Ereignis während der der Debugger die Interaktion mit dem verwalteten Zustand des Prozesses unterstützt. In diesem Fall empfängt der Debugger die [ICorDebugUnmanagedCallback:: DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) Rückruf mit seiner `fOutOfBand` Parametersatz auf `false`.  
  
 Ein *Out-of-Band-Ereignis* ist ein nicht verwaltetes Ereignis bei der Interaktion mit dem verwalteten Zustand des Prozesses ist nicht möglich, während der Prozess aufgrund des Ereignisses beendet wird. In diesem Fall empfängt der Debugger die `ICorDebugUnmanagedCallback::DebugEvent` Rückruf mit seiner `fOutOfBand` Parametersatz auf `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
