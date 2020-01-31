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
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791140"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue-Schnittstelle
Stellt einen Wert in dem Prozess dar, der gedebuggt wird. Der Wert kann ein Lese-oder ein Schreib Wert sein.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](icordebugvalue-createbreakpoint-method.md)|Diese Methode ist derzeit nicht implementiert.|  
|[GetAddress-Methode](icordebugvalue-getaddress-method.md)|Ruft die Adresse dieses `ICorDebugValue` Objekts ab, das gerade gedebuggt wird.|  
|[GetSize-Methode](icordebugvalue-getsize-method.md)|Ruft die Größe dieses `ICorDebugValue` Objekts in Bytes ab.|  
|[GetType-Methode](icordebugvalue-gettype-method.md)|Ruft den primitiven Typ dieses `ICorDebugValue` Objekts ab.|  
  
## <a name="remarks"></a>Hinweise  
 Im Allgemeinen wird der Besitz eines Wert Objekts bei der Rückgabe übermittelt. Der Empfänger ist dafür verantwortlich, einen Verweis aus dem-Objekt zu entfernen, wenn er mit dem-Objekt fertig ist.  
  
 Abhängig davon, wo der Wert aus abgerufen wurde, bleibt der Wert möglicherweise nicht gültig, nachdem der Prozess fortgesetzt wurde. Im Allgemeinen sollte der Wert nicht über einen Aufrufen der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode hinweg aufbewahrt werden.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
