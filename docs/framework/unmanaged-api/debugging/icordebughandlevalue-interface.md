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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3219554cf953b8de31e236b2f484478172673f7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915007"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue-Schnittstelle

Eine Unterklasse von ICorDebugReferenceValue, die einen Verweis Wert darstellt, mit dem der Debugger ein Handle für Garbage Collection erstellt hat.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Dispose-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Gibt das Handle frei, auf `ICorDebugHandleValue` das dieses-Objekt verweist, ohne den Schnittstellen Zeiger explizit freizugeben.|  
|[GetHandleType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Ruft einen CorDebugHandleType-Wert ab, der die Art des Handles beschreibt `ICorDebugHandleValue`, auf den von diesem verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugReferenceValue` Objekt wird durch einen Umbruch bei der Ausführung des decodierten Codes ungültig. Ein `ICorDebugHandleValue` behält seinen Verweis durch Unterbrechungen und Fortsetzungen bei, bis er explizit freigegeben wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
