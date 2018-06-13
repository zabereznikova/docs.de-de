---
title: ICorDebugMutableDataTarget-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 677db647320ff4014b791502b7ac1b261378c8dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419529"
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
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
