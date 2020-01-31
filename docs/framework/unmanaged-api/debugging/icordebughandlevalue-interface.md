---
title: ICorDebugHandleValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 406468fc6e2b68e8c8e1dfbd0f0f18cce3f013ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794459"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue-Schnittstelle

Eine Unterklasse von ICorDebugReferenceValue, die einen Verweis Wert darstellt, mit dem der Debugger ein Handle für Garbage Collection erstellt hat.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Dispose-Methode](icordebughandlevalue-dispose-method.md)|Gibt das Handle frei, auf das von diesem `ICorDebugHandleValue` Objekt verwiesen wird, ohne den Schnittstellen Zeiger explizit freizugeben.|  
|[GetHandleType-Methode](icordebughandlevalue-gethandletype-method.md)|Ruft einen CorDebugHandleType-Wert ab, der die Art des Handles beschreibt, auf das von diesem `ICorDebugHandleValue`verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugReferenceValue`-Objekt wird durch einen Umbruch bei der Ausführung des decodierten Codes ungültig. Ein `ICorDebugHandleValue` behält seinen Verweis durch Unterbrechungen und Fortsetzungen bei, bis es explizit freigegeben wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
