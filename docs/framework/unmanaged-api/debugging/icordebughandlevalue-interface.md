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
ms.openlocfilehash: c901e21521e941c51939958175a5316808890e9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208615"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue-Schnittstelle

Eine Unterklasse von ICorDebugReferenceValue, die einen Verweis Wert darstellt, mit dem der Debugger ein Handle für Garbage Collection erstellt hat.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Verwerfen-Methode](icordebughandlevalue-dispose-method.md)|Gibt das Handle frei, auf das dieses-Objekt verweist, `ICorDebugHandleValue` ohne den Schnittstellen Zeiger explizit freizugeben.|  
|[GetHandleType-Methode](icordebughandlevalue-gethandletype-method.md)|Ruft einen CorDebugHandleType-Wert ab, der die Art des Handles beschreibt, auf den von diesem verwiesen wird `ICorDebugHandleValue` .|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugReferenceValue` Objekt wird durch einen Umbruch bei der Ausführung des decodierten Codes ungültig. Ein `ICorDebugHandleValue` behält seinen Verweis durch Unterbrechungen und Fortsetzungen bei, bis er explizit freigegeben wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
