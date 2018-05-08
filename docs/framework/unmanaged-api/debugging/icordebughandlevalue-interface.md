---
title: ICorDebugHandleValue Schnittstelle1
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
ms.openlocfilehash: ed6ba8a738b4086b9150e0a1c7b300a519fa3092
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebughandlevalue-interface1"></a>ICorDebugHandleValue Schnittstelle1
Eine Unterklasse von ICorDebugReferenceValue, die einen Verweiswert darstellt, zu dem der Debugger einen Handle zur Garbagecollection erstellt hat.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Dispose-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Gibt das Handle verweist diese frei `ICorDebugHandleValue` Objekt nicht explizit freigegeben den Schnittstellenzeiger auf.|  
|[GetHandleType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Ruft einen CorDebugHandleType-Wert, der die Art der verwiesen, die von diesem Handle beschreibt `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugReferenceValue` Objekt wird durch eine Unterbrechung der Ausführung des gedebuggten Codes für ungültig erklärt. Ein `ICorDebugHandleValue` verwaltet seinen Verweis durch Zeilenumbrüche und Fortsetzungen sein, bis sie explizit freigegeben wird.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
