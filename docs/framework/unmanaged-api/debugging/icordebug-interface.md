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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74c5036bdc8a4a75e5711c6dc1d34d8f2c21128f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebug-interface"></a>ICorDebug-Schnittstelle
Enthält Methoden, die Entwickler beim Debuggen von Anwendungen in der common Language Runtime (CLR)-Umgebung zu ermöglichen.  
  
> [!NOTE]
>  Debuggen im gemischten Modus (verwalteter und systemeigener Code) wird unter Windows 95, Windows 98 oder Windows ME sowie auf nicht X86-Plattformen (z. B. IA64 und AMD64) nicht unterstützt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanLaunchOrAttach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Bestimmt, ob ein neuer Prozess gestartet oder Anhängen an den angegebenen Prozess innerhalb des Kontexts der aktuellen Konfiguration für Computer und die Common Language Runtime möglich ist.|  
|[CreateProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Startet einen Prozess und seine primäre Thread unter der Kontrolle des Debuggers.|  
|[DebugActiveProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Fügt der Debugger an einen vorhandenen Prozess.|  
|[EnumerateProcesses-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Ruft einen Enumerator für die Prozesse, die gedebuggt werden.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Gibt das Objekt "ICorDebugProcess" mit der angegebenen Prozess-ID.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Initialisiert die `ICorDebug` Objekt.|  
|[SetManagedHandler-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.|  
|[SetUnmanagedHandler-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.|  
|[Terminate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Beendet die `ICorDebug` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebug` Stellt ein Ereignisverarbeitungsschleife für keinen Debuggerprozess dar. Der Debugger muss warten, für die [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf von allen Prozessen, die vor dem Freigeben von dieser Schnittstelle gedebuggt wird.  
  
 Die `ICorDebug` Objekt ist das erste Objekt, das alle weiteren verwalteten Debuggens steuern. In der .NET Framework-Versionen 1.0 und 1.1, dieses Objekt wurde ein `CoClass` erstellte aus COM-Objekt In .NET Framework, Version 2.0, ist dieses Objekt nicht mehr eine `CoClass` Objekt. Es muss erstellt werden, indem die [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) -Funktion, die mehr Version-fähig ist. Diese neue Funktion ermöglicht Clients erhalten eine spezifische Implementierung `ICorDebug`, die auch eine bestimmte Version von der Debug-API emuliert.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
