---
title: ICorDebugProcess-Schnittstelle1
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
ms.openlocfilehash: ae3f64b466e0d356b540cc9d6f3db881e27ac4aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709818"
---
# <a name="icordebugprocess-interface1"></a>ICorDebugProcess-Schnittstelle1
Stellt einen Prozess dar, der verwalteten Code ausführt. Diese Schnittstelle ist eine Unterklasse von ICorDebugController.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.|  
|[EnableLogMessages-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Aktiviert und deaktiviert das Senden von Meldungen an dem Debugger.|  
|[EnumerateAppDomains-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Listet alle Anwendungsdomänen im Prozess.|  
|[EnumerateObjects-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Nicht implementiert.|  
|[GetHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Ruft ein Handle für den Prozess ab.|  
|[GetHelperThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Ruft das Betriebssystem (OS)-Thread-ID für interne Hilfsthreads des Debuggers ab.|  
|[GetID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Ruft das Betriebssystem (OS)-ID des Prozesses ab.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Nicht implementiert.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Ruft die ICorDebugThread-Instanz, die den angegebene BS-Thread-ID.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Ruft den Kontext für den angegebenen Thread ab.|  
|[IsOSSuspended-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Bestimmt, ob der Thread durch den Debugger Beenden des Prozesses angehalten wurde.|  
|[IsTransitionStub-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Bestimmt, ob eine Adresse in einen Stub, der einen Übergang in verwalteten Code bewirkt.|  
|[ModifyLogSwitch-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Legt den Schweregrad der angegebenen Log-Schalter fest.|  
|[ReadMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Liest Arbeitsspeicher vom Prozess an.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Legt den Kontext für den angegebenen Thread fest.|  
|[ThreadForFiberCookie-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Veraltet.|  
|[WriteMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Schreibt Daten in einem Bereich des Arbeitsspeichers im Prozess.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
