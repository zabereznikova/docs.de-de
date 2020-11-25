---
title: ICorDebugMutableDataTarget-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
ms.openlocfilehash: cd22707832504ca2f08299872bc39bca2af782bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709348"
---
# <a name="icordebugmutabledatatarget-interface"></a>ICorDebugMutableDataTarget-Schnittstelle

Erweitert die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um änderbare Datenziele zu unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ContinueStatusChanged-Methode](icordebugmutabledatatarget-continuestatuschanged-method.md)|Ändert den Fortsetzungsstatus für das ausstehende Debugereignis für den angegebenen Thread.|  
|[SetThreadContext-Methode](icordebugmutabledatatarget-setthreadcontext-method.md)|Legt den Kontext (Registerwerte) für einen Thread fest.|  
|[WriteVirtual-Methode](icordebugmutabledatatarget-writevirtual-method.md)|Schreibt Speicher in den Prozessadressraum.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Erweiterung der [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle kann durch Debuggingtools implementiert werden, die den Ziel Prozess ändern möchten (z. b. zum Ausführen von Live-invasivem Debugging).  
  
 Alle diese Methoden sind insofern optional, als keine auf einer Untersuchung des Kerns basierende Debugfunktionen verloren geht, wenn diese Schnittstelle nicht implementiert oder wird oder keine Aufrufe dieser Methoden stattfinden.  Jeder Fehler `HRESULT` von diesen Methoden wird als `HRESULT` aus dem ICorDebug-Methodenaufruf verteilt.  
  
 Beachten Sie, dass ein einzelner ICorDebug-Methodenaufruf ggf. zu mehreren Mutationen führt. Es ist kein Mechanismus zum Sicherstellen vorhanden, dass zugehörige Mutationen transaktional angewendet werden (alle oder keine).  Dies bedeutet, dass bei einem Fehler einer Mutation, nachdem andere Mutationen (für den gleichen ICorDebug-Aufruf) erfolgreich ausgeführt wurden, der Zielprozess in einem inkonsistenten Zustand verbleiben kann, und das Debuggen wird ggf. unzuverlässig.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
