---
title: ICorDebugMutableDataTarget-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef1c0b7a56f6bd1f7e87650b72dfe8b1411ef7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatarget-interface"></a>ICorDebugMutableDataTarget-Schnittstelle
Erweitert die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um änderbare Datenziele zu unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ContinueStatusChanged-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|Ändert den Fortsetzungsstatus für das ausstehende Debugereignis für den angegebenen Thread.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|Legt den Kontext (Registerwerte) für einen Thread fest.|  
|[WriteVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|Schreibt Speicher in den Prozessadressraum.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Erweiterung der [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) -Schnittstelle kann durch Debugtools, die den Zielprozess (z. B. zum Ausführen von invasivem Livedebuggen) ändern möchten implementiert werden.  
  
 Alle diese Methoden sind insofern optional, als keine auf einer Untersuchung des Kerns basierende Debugfunktionen verloren geht, wenn diese Schnittstelle nicht implementiert oder wird oder keine Aufrufe dieser Methoden stattfinden.  Jeder Fehler `HRESULT` von diesen Methoden wird als `HRESULT` aus dem ICorDebug-Methodenaufruf verteilt.  
  
 Beachten Sie, dass ein einzelner ICorDebug-Methodenaufruf ggf. zu mehreren Mutationen führt. Es ist kein Mechanismus zum Sicherstellen vorhanden, dass zugehörige Mutationen transaktional angewendet werden (alle oder keine).  Dies bedeutet, dass bei einem Fehler einer Mutation, nachdem andere Mutationen (für den gleichen ICorDebug-Aufruf) erfolgreich ausgeführt wurden, der Zielprozess in einem inkonsistenten Zustand verbleiben kann, und das Debuggen wird ggf. unzuverlässig.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
