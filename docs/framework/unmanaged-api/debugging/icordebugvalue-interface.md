---
title: ICorDebugValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: 77d28d8eef97a934c15ac29725f856f4bf39e6ce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140158"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue-Schnittstelle
Stellt einen Wert in dem Prozess dar, der gedebuggt wird. Der Wert kann ein Lese-oder ein Schreib Wert sein.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Diese Methode ist zurzeit nicht implementiert.|  
|[GetAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Ruft die Adresse dieses `ICorDebugValue` Objekts ab, das gerade gedebuggt wird.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Ruft die Größe dieses `ICorDebugValue` Objekts in Bytes ab.|  
|[GetType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Ruft den primitiven Typ dieses `ICorDebugValue` Objekts ab.|  
  
## <a name="remarks"></a>Hinweise  
 Im Allgemeinen wird der Besitz eines Wert Objekts bei der Rückgabe übermittelt. Der Empfänger ist dafür verantwortlich, einen Verweis aus dem-Objekt zu entfernen, wenn er mit dem-Objekt fertig ist.  
  
 Abhängig davon, wo der Wert aus abgerufen wurde, bleibt der Wert möglicherweise nicht gültig, nachdem der Prozess fortgesetzt wurde. Im Allgemeinen sollte der Wert nicht über einen Aufrufen der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) -Methode hinweg aufbewahrt werden.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugValue3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
