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
ms.openlocfilehash: 193232ce1006a9cf209db9330343386404948440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168284"
---
# <a name="icordebug-interface"></a>ICorDebug-Schnittstelle
Bietet Methoden, mit die Entwickler Anwendungen in der common Language Runtime (CLR)-Umgebung debuggen können.  
  
> [!NOTE]
>  Debuggen im gemischten Modus (verwalteter und systemeigener Code) wird auf Windows 95, Windows 98 oder Windows ME oder auf nicht-X86-Plattformen (z. B. IA64 und AMD64) nicht unterstützt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanLaunchOrAttach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Bestimmt, ob ein neuer Prozess gestartet oder das Anfügen an den Prozess innerhalb des Kontexts der aktuellen Computer und -Runtime-Konfiguration möglich ist.|  
|[CreateProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Startet einen Prozess und seine primäre Thread unter der Kontrolle des Debuggers.|  
|[DebugActiveProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Wird der Debugger an einen vorhandenen Prozess angefügt.|  
|[EnumerateProcesses-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Ruft einen Enumerator für die Prozesse, die gedebuggt werden.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Gibt das Objekt "ICorDebugProcess" mit dem angegebenen Prozess-ID zurück|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Initialisiert das `ICorDebug`-Objekt.|  
|[SetManagedHandler-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.|  
|[SetUnmanagedHandler-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.|  
|[Terminate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Beendet die `ICorDebug` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebug` Stellt ein Ereignisverarbeitungsschleife für einen Debuggerprozess dar. Der Debugger muss warten, für die [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf von allen Prozessen, die vor dem Freigeben von dieser Schnittstelle gedebuggt wird.  
  
 Die `ICorDebug` Objekt ist das ursprüngliche Objekt zum Steuern der gesamte Weitere Debuggen. In der .NET Framework-Versionen 1.0 und 1.1, dieses Objekt wurde ein `CoClass` erstellte aus COM-Objekt In .NET Framework, Version 2.0, ist dieses Objekt nicht mehr eine `CoClass` Objekt. Es muss erstellt werden, indem die [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) -Funktion, die mehr Version-fähig ist. Diese neue Funktion ermöglicht Clients das Abrufen einer bestimmten Implementierung der `ICorDebug`, die auch emuliert einer bestimmten Version von der Debug-API.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
