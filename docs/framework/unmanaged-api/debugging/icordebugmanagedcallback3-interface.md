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
ms.openlocfilehash: e04f5be6d2612b26bf7d71807753d170e6a5a7a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723297"
---
# <a name="icordebugmanagedcallback3-interface"></a>ICorDebugManagedCallback3-Schnittstelle

Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CustomNotification-Methode](icordebugmanagedcallback3-customnotification-method.md)|Gibt an, dass eine aktivierte benutzerdefinierte Debugger-Benachrichtigung ausgelöst wurde.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Schnittstelle ist eine logische Erweiterung der [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Schnittstelle und der [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Schnittstelle.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
- [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
