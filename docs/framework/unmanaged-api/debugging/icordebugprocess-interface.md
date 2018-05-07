---
title: ICorDebugProcess Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e4e3854a850c9639e93c8db2ec8ccd567b242b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess-interface1"></a>ICorDebugProcess Schnittstelle1
Stellt einen Prozess dar, der verwalteten Code ausführt. Diese Schnittstelle ist eine Unterklasse von ICorDebugController.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Löscht die aktuellen nicht verwalteten Ausnahme für den angegebenen Thread.|  
|[EnableLogMessages-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Aktiviert und deaktiviert das Senden von Meldungen an dem Debugger.|  
|[EnumerateAppDomains-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Listet alle Anwendungsdomänen im Prozess.|  
|[EnumerateObjects-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Nicht implementiert.|  
|[GetHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Ruft ein Handle für den Prozess ab.|  
|[GetHelperThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Ruft die Thread-ID (BS) für interne Hilfsthreads des Debuggers an.|  
|[GetID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Ruft die ID (BS) des Prozesses ab.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Nicht implementiert.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Ruft ICorDebugThread-Instanz, die den angegebenen OS-Thread-ID.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Ruft den Kontext für den angegebenen Thread ab.|  
|[IsOSSuspended-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Bestimmt, ob der Thread als Ergebnis der Debugger, beenden den Prozess angehalten wurde.|  
|[IsTransitionStub-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Bestimmt, ob eine Adresse innerhalb eines Stubs, das einen Übergang zu verwaltetem Code bewirkt.|  
|[ModifyLogSwitch-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Legt den Schweregrad der angegebenen Log-Schalter.|  
|[ReadMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Liest Arbeitsspeicher aus dem Prozess.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Legt den Kontext für den angegebenen Thread fest.|  
|[ThreadForFiberCookie-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Veraltet.|  
|[WriteMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Schreibt Daten in einem Bereich des Arbeitsspeichers im Prozess.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
