---
title: ICorDebugProcess8-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
ms.openlocfilehash: 00c432374eeb82692492b8e6b10472f13bc44d6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732514"
---
# <a name="icordebugprocess8-interface"></a>ICorDebugProcess8-Schnittstelle

[Wird in der .NET Framework 4,6 und höheren Versionen unterstützt]  
  
 Erweitert die ICorDebugProcess-Schnittstelle logisch, um bestimmte Typen von [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen zu aktivieren oder zu deaktivieren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnableExceptionCallbacksOutsideOfMyCode-Methode](icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|Aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
