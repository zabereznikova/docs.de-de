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
ms.openlocfilehash: 7d3c35ed6cda637e3b885afe089ddfa590d51076
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683601"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue-Schnittstelle

Stellt einen Wert in dem Prozess dar, der gedebuggt wird. Der Wert kann ein Lese-oder ein Schreib Wert sein.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](icordebugvalue-createbreakpoint-method.md)|Diese Methode ist derzeit nicht implementiert.|  
|[GetAddress-Methode](icordebugvalue-getaddress-method.md)|Ruft die Adresse dieses- `ICorDebugValue` Objekts ab, das gerade gedebuggt wird.|  
|[GetSize-Methode](icordebugvalue-getsize-method.md)|Ruft die Größe des-Objekts in Bytes ab `ICorDebugValue` .|  
|[GetType-Methode](icordebugvalue-gettype-method.md)|Ruft den primitiven Typ dieses- `ICorDebugValue` Objekts ab.|  
  
## <a name="remarks"></a>Hinweise  

 Im Allgemeinen wird der Besitz eines Wert Objekts bei der Rückgabe übermittelt. Der Empfänger ist dafür verantwortlich, einen Verweis aus dem-Objekt zu entfernen, wenn er mit dem-Objekt fertig ist.  
  
 Abhängig davon, wo der Wert aus abgerufen wurde, bleibt der Wert möglicherweise nicht gültig, nachdem der Prozess fortgesetzt wurde. Im Allgemeinen sollte der Wert nicht über einen Aufrufen der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode hinweg aufbewahrt werden.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
