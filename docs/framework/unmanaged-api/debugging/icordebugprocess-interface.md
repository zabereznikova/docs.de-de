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
ms.openlocfilehash: b2429052173a187297b67c756213e5d27a79298b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792591"
---
# <a name="icordebugprocess-interface"></a>ICorDebugProcess-Schnittstelle
Stellt einen Prozess dar, der verwalteten Code ausführt. Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[ClearCurrentException-Methode](icordebugprocess-clearcurrentexception-method.md)|Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.|  
|[EnableLogMessages-Methode](icordebugprocess-enablelogmessages-method.md)|Aktiviert und deaktiviert das Senden von Protokollmeldungen an den Debugger.|  
|[EnumerateAppDomains-Methode](icordebugprocess-enumerateappdomains-method.md)|Listet alle Anwendungs Domänen im Prozess auf.|  
|[EnumerateObjects-Methode](icordebugprocess-enumerateobjects-method.md)|Nicht implementiert.|  
|[GetHandle-Methode](icordebugprocess-gethandle-method.md)|Ruft ein Handle für den Prozess ab.|  
|[GetHelperThreadID-Methode](icordebugprocess-gethelperthreadid-method.md)|Ruft die Betriebssystem-Thread-ID für den internen Hilfsthread des Debuggers ab.|  
|[GetID-Methode](icordebugprocess-getid-method.md)|Ruft die Betriebssystem-ID des Prozesses ab.|  
|[GetObject-Methode](icordebugprocess-getobject-method.md)|Nicht implementiert.|  
|[GetThread-Methode](icordebugprocess-getthread-method.md)|Ruft die ICorDebugThread-Instanz ab, die über die angegebene Betriebssystem Thread-ID verfügt.|  
|[GetThreadContext-Methode](icordebugprocess-getthreadcontext-method.md)|Ruft den Kontext für den angegebenen Thread ab.|  
|[IsOSSuspended-Methode](icordebugprocess-isossuspended-method.md)|Bestimmt, ob der Thread angehalten wurde, weil der Debugger den Prozess beendet hat.|  
|[IsTransitionStub-Methode](icordebugprocess-istransitionstub-method.md)|Bestimmt, ob sich eine Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht.|  
|[ModifyLogSwitch-Methode](icordebugprocess-modifylogswitch-method.md)|Legt den Schweregrad des angegebenen Protokoll Schalters fest.|  
|[ReadMemory-Methode](icordebugprocess-readmemory-method.md)|Liest Arbeitsspeicher aus dem Prozess.|  
|[SetThreadContext-Methode](icordebugprocess-setthreadcontext-method.md)|Legt den Kontext für den angegebenen Thread fest.|  
|[ThreadForFiberCookie-Methode](icordebugprocess-threadforfibercookie-method.md)|Veraltet.|  
|[WriteMemory-Methode](icordebugprocess-writememory-method.md)|Schreibt Daten in einen Arbeitsspeicher Bereich des Prozesses.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](icordebug-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
