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
ms.openlocfilehash: 9a9eb63e681b47f058901b0ff002015baffe6048
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117442"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue-Schnittstelle

Eine Unterklasse von ICorDebugReferenceValue, die einen Verweiswert darstellt, den der Debugger einen Handle zur Garbagecollection erstellt hat.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Dispose-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Gibt das Handle, das auf die dieses frei `ICorDebugHandleValue` Objekt ohne den Schnittstellenzeiger explizit freizugeben.|  
|[GetHandleType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Ruft einen CorDebugHandleType-Wert, der den Typ des Handles, die auf die dieses beschreibt `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugReferenceValue` Objekt durch eine Unterbrechung der Ausführung des debuggten Codes ungültig ist. Ein `ICorDebugHandleValue` seinen Verweis über Unterbrechungen und Fortsetzungen, verwaltet, bis er explizit freigegeben wird.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
