---
title: ICorDebugUnmanagedCallback::DebugEvent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback.DebugEvent
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 008ae1bd1a5774604bf2c0f196352dcf07da6ee7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent-Methode
Benachrichtigt den Debugger, dass ein systemeigenes Ereignis ausgelöst wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pDebugEvent`  
 [in] Ein Zeiger auf das systemeigene Ereignis.  
  
 `fOutOfBand`  
 [in] `true`, wenn die Interaktion mit dem verwalteten Prozesszustand nicht möglich ist, nachdem ein nicht verwaltetes Ereignis tritt auf, bis der Debugger ruft [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Thread, der debuggt wird ein Win32-Thread ist, verwenden Sie keine Mitglieder der Win32-Debugschnittstelle. Sie können Aufrufen `ICorDebugController::Continue` nur in einem Win32-Thread und nur, wenn Sie nach einem Out-of-Band-Ereignis zu fortfahren.  
  
 Die `DebugEvent` Rückruf befolgt nicht die Standardregeln für Rückrufe. Beim Aufruf `DebugEvent`, der Prozess werden in den unformatierten, OS-Debug angehaltenen Zustand. Der Prozess wird nicht synchronisiert werden. Es wird automatisch Status "synchronisiert" bei Bedarf informationsanforderungen über verwalteten Code nicht erfüllen, die in anderen geschachtelten möglicherweise geben `DebugEvent` Rückrufe.  
  
 Rufen Sie [ICorDebugProcess:: ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) für den Prozess, ein Ausnahmeereignis ignoriert werden sollen, bevor Sie den Prozess fortsetzen. Beim Aufrufen dieser Methode DBG_CONTINUE anstelle von DBG_EXCEPTION_NOT_HANDLED auf die Continue-Anforderung sendet, und löscht automatisch Out-of-Band-Haltepunkte und einstufiger Ausnahmen. Out-of-Band-Ereignisse können zu einem beliebigen Zeitpunkt stammen, selbst wenn die Anwendung, die gedebuggt wird beendet wird und wenn ein ausstehender in-Band-Ereignis bereits vorhanden ist.  
  
 In .NET Framework, Version 2.0 sollte der Debugger sofort nach einer Out-of-Band-Haltepunktereignis fortgesetzt werden. Verwenden des Debuggers sollte die [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) und [ICorDebugProcess2:: ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) Methoden zum Hinzufügen und Entfernen von Breakpoints. Diese Methoden werden automatisch über die Out-of-Band-Haltepunkte überspringen. Daher muss die nur Out-of-Band-Haltepunkte, die weitergeleitet werden unformatierte Haltepunkte, die bereits in den Anweisungsstream ein, z. B. einen Aufruf der Win32- `DebugBreak` Funktion. Versuchen Sie nicht mit `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), oder ein anderes Element der [Debuggen-API](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugUnmanagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
