---
title: ICorDebugController::Continue-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f448a0383d3ad121cbddb59e13acef46a336261
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485732"
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue-Methode
Setzt die Ausführung von verwalteten Threads nach einem Aufruf von [Methode beenden](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fIsOutOfBand`  
 [in] Legen Sie auf `true` , wenn Sie von einem Out-of-Band-Ereignis, den Vorgang fortsetzen, andernfalls legen Sie auf `false`.  
  
## <a name="remarks"></a>Hinweise  
 `Continue` wird der Prozess fortgesetzt wird, nach einem Aufruf der `ICorDebugController::Stop` Methode.  
  
 Beim Debuggen im gemischten Modus, rufen Sie nicht `Continue` auf die Win32 Ereignis thread, es sei denn, Sie von einem Out-of-Band-Ereignis fortsetzen möchten.  
  
 Ein *in-Band-Ereignis* ist entweder ein verwaltetes Ereignis oder ein normaler nicht verwaltetes Ereignis während der der Debugger die Interaktion mit den verwalteten Zustand des Prozesses unterstützt. In diesem Fall empfängt der Debugger die [ICorDebugUnmanagedCallback:: DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) Rückruffunktion mit der `fOutOfBand` Parametersatz zu `false`.  
  
 Ein *Out-of-Band-Ereignis* ist ein nicht verwaltetes Ereignis während der Interaktion mit den verwalteten Zustand des Prozesses nicht möglich, ist während der Prozess, aufgrund des Ereignisses beendet wird. In diesem Fall empfängt der Debugger die `ICorDebugUnmanagedCallback::DebugEvent` Rückruffunktion mit der `fOutOfBand` Parametersatz zu `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

