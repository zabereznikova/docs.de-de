---
title: ICorDebugUnmanagedCallback::DebugEvent-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
ms.openlocfilehash: 2d865f837d38894e8449af671e2d12e7676dd040
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129138"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent-Methode
Benachrichtigt den Debugger, dass ein natives Ereignis ausgelöst wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDebugEvent`  
 in Ein Zeiger auf das Native Ereignis.  
  
 `fOutOfBand`  
 [in] `true`, wenn die Interaktion mit dem verwalteten Prozessstatus nach einem nicht verwalteten Ereignis nicht mehr möglich ist, bis der Debugger [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)aufruft. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn es sich bei dem gedebuggten Thread um einen Win32-Thread handelt, dürfen Sie keine Member der Win32-Debugschnittstelle verwenden. Sie können `ICorDebugController::Continue` nur in einem Win32-Thread und nur bei der Fortsetzung eines Out-of-Band-Ereignisses abrufen.  
  
 Der `DebugEvent`-Rückruf befolgt nicht die Standardregeln für Rückrufe. Wenn Sie `DebugEvent`aufgerufen wird, befindet sich der Prozess im unformatierten Zustand "OS-Debug beendet". Der Prozess wird nicht synchronisiert. Wenn dies erforderlich ist, wird automatisch der synchronisierte Status eingegeben, um Anforderungen nach Informationen über verwalteten Code zu erfüllen. Dies kann zu anderen Sch`DebugEvent` Rückrufen führen.  
  
 Aufrufen von [ICorDebugProcess:: cleareption TException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) für den Prozess, um ein Ausnahme Ereignis zu ignorieren, bevor der Prozess fortgesetzt wird. Wenn Sie diese Methode aufrufen, wird DBG_CONTINUE anstelle von DBG_EXCEPTION_NOT_HANDLED für die Continue-Anforderung gesendet, und Out-of-Band-Haltepunkte und einstufige Ausnahmen werden automatisch gelöscht. Out-of-Band-Ereignisse können jederzeit auftreten, auch wenn die zu debuggenden Anwendung beendet wird und ein ausstehendes in-Band-Ereignis bereits vorhanden ist.  
  
 In der .NET Framework Version 2,0 sollte der Debugger unmittelbar hinter einem Out-of-Band-breakpointereignis fortfahren. Der Debugger sollte die Methoden [ICorDebugProcess2:: abtmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) und [ICorDebugProcess2:: ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) verwenden, um Breakpoints hinzuzufügen und zu entfernen. Diese Methoden überspringen alle out-of-Band-Haltepunkte automatisch. Daher sollten die einzigen out-of-Band-Haltepunkte, die verteilt werden, unformatierte Haltepunkte sein, die sich bereits im Anweisungs Datenstrom befinden, z. b. ein aufzurufende Win32-`DebugBreak` Funktion. Versuchen Sie nicht, `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)oder einen anderen Member der Debug- [API](../../../../docs/framework/unmanaged-api/debugging/index.md)zu verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugUnmanagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
