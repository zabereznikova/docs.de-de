---
title: ICorDebugHandleValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue
helpviewer_keywords: ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b56c23caaaed2bc63c724769db1198fd088f7f1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
