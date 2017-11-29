---
title: ICorDebugProcess Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess
helpviewer_keywords: ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee526a79d89a9e4e3483daa07a512b6b7f920e70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
