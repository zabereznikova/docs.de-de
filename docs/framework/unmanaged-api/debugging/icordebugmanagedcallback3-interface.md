---
title: ICorDebugManagedCallback3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: b97f29b94ed4fad6892697ca1c7ed4a20c99c03e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793272"
---
# <a name="icordebugmanagedcallback3-interface"></a>ICorDebugManagedCallback3-Schnittstelle
Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[CustomNotification-Methode](icordebugmanagedcallback3-customnotification-method.md)|Gibt an, dass eine aktivierte benutzerdefinierte Debugger-Benachrichtigung ausgelöst wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle ist eine logische Erweiterung der [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Schnittstelle und der [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Schnittstelle.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
- [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
