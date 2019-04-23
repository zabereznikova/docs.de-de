---
title: ICorDebugManagedCallback2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1ecfea208f87f53f15fcc4cdafb58341c293e43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096087"
---
# <a name="icordebugmanagedcallback2-interface"></a>ICorDebugManagedCallback2-Schnittstelle
Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen. `ICorDebugManagedCallback2` ist eine logische Erweiterung von der [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ChangeConnection-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|Benachrichtigt den Debugger an, dass der Satz von Aufgaben im Zusammenhang mit der angegebenen Verbindung geändert wurde.|  
|[CreateConnection-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|Benachrichtigt den Debugger an, dass eine neue Verbindung erstellt wurde.|  
|[DestroyConnection-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|Benachrichtigt den Debugger an, dass die angegebene Verbindung beendet wurde.|  
|[Exception-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.|  
|[ExceptionUnwind-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|Stellt eine Benachrichtigung zum Status während des endladungsprozesses Ausnahme bereit.|  
|[FunctionRemapComplete-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|Benachrichtigt den Debugger, dass die Ausführung von Code auf eine neue Version einer bearbeiteten Funktion gewechselt hat.|  
|[FunctionRemapOpportunity-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|Benachrichtigt den Debugger, dass die codeausführung einen Sequenzpunkt in einer früheren Version einer bearbeiteten Funktion erreicht hat.|  
|[MDANotification-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|Stellt die Benachrichtigung, dass die Ausführung von Code mit eine verwalteten debugging Assistant, Assistent für (verwaltetes Debuggen MDA) Nachricht aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugManagedCallback2` Schnittstelle erweitert die `ICorDebugManagedCallback` -Schnittstelle neue Debug-Ereignisse, die in .NET Framework, Version 2.0 eingeführt wurde.  
  
 Ein Debugger muss implementieren `ICorDebugManagedCallback2` , wenn sie .NET Framework 2.0-Anwendungen Debuggen ist. Eine Instanz von `ICorDebugManagedCallback` oder `ICorDebugManagedCallback2` wird als das Rückrufobjekt zu übergeben, [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
