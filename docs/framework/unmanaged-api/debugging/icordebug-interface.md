---
title: ICorDebug-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: ee6bcbc9f3377735ed289d52afddb6efa755b16d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134077"
---
# <a name="icordebug-interface"></a>ICorDebug-Schnittstelle
Stellt Methoden bereit, mit denen Entwickler Anwendungen in der Common Language Runtime-Umgebung (CLR) Debuggen können.  
  
> [!NOTE]
> Das Debuggen im gemischten Modus (verwalteter und nativer Code) wird unter Windows 95, Windows 98 oder Windows Me oder auf nicht-x86-Plattformen (z. b. ia64 und amd64) nicht unterstützt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanLaunchOrAttach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Bestimmt, ob das Starten eines neuen Prozesses oder das Anfügen an den angegebenen Prozess innerhalb des Kontexts der aktuellen Computer-und Laufzeitkonfiguration möglich ist.|  
|[CreateProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Startet einen Prozess und seinen primären Thread unter der Kontrolle des Debuggers.|  
|[DebugActiveProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Fügt den Debugger an einen vorhandenen Prozess an.|  
|[EnumerateProcesses-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Ruft einen Enumerator für die Prozesse ab, die gedeentschlgt werden.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Gibt das "ICorDebugProcess"-Objekt mit der angegebenen Prozess-ID zurück.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Initialisiert das `ICorDebug`-Objekt.|  
|[SetManagedHandler-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.|  
|[SetUnmanagedHandler-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.|  
|[Terminate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Beendet das `ICorDebug`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebug` stellt eine Ereignis Verarbeitungs Schleife für einen Debuggerprozess dar. Der Debugger muss auf den Rückruf für den [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) -Rückruf von allen debuggten Prozessen warten, bevor er diese Schnittstelle freigibt.  
  
 Das `ICorDebug`-Objekt ist das erste Objekt, das alle weiteren verwalteten Debuggen steuert. In den .NET Framework Versionen 1,0 und 1,1 war dieses Objekt ein `CoClass` Objekt, das aus com erstellt wurde. In der .NET Framework Version 2,0 ist dieses Objekt kein `CoClass` Objekt mehr. Sie muss von der Funktion " [dedeedebugginginterfakefromversion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) " erstellt werden, die Versions abhängig ist. Diese neue Erstellungs Funktion ermöglicht es Clients, eine bestimmte Implementierung von `ICorDebug`zu erhalten, wodurch auch eine bestimmte Version der Debug-API emuliert wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
