---
title: ICorDebugProcess-Schnittstelle
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
ms.openlocfilehash: b99630ba60cd84254024b91dba9ef9922fd7e041
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943306"
---
# <a name="icordebugprocess-interface"></a>ICorDebugProcess-Schnittstelle
Stellt einen Prozess dar, der verwalteten Code ausführt. Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.|  
|[EnableLogMessages-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Aktiviert und deaktiviert das Senden von Protokollmeldungen an den Debugger.|  
|[EnumerateAppDomains-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Listet alle Anwendungs Domänen im Prozess auf.|  
|[EnumerateObjects-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Nicht implementiert.|  
|[GetHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Ruft ein Handle für den Prozess ab.|  
|[GetHelperThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Ruft die Betriebssystem-Thread-ID für den internen Hilfsthread des Debuggers ab.|  
|[GetID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Ruft die Betriebssystem-ID des Prozesses ab.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Nicht implementiert.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Ruft die ICorDebugThread-Instanz ab, die über die angegebene Betriebssystem Thread-ID verfügt.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Ruft den Kontext für den angegebenen Thread ab.|  
|[IsOSSuspended-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Bestimmt, ob der Thread angehalten wurde, weil der Debugger den Prozess beendet hat.|  
|[IsTransitionStub-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Bestimmt, ob sich eine Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht.|  
|[ModifyLogSwitch-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Legt den Schweregrad des angegebenen Protokoll Schalters fest.|  
|[ReadMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Liest Arbeitsspeicher aus dem Prozess.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Legt den Kontext für den angegebenen Thread fest.|  
|[ThreadForFiberCookie-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Veraltet.|  
|[WriteMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Schreibt Daten in einen Arbeitsspeicher Bereich des Prozesses.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
