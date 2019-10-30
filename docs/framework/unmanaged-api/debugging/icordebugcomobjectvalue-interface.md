---
title: ICorDebugComObjectValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 4ff5c0d470e6eb84eb8b526f5e8f74e5e1a8118a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125485"
---
# <a name="icordebugcomobjectvalue-interface"></a>ICorDebugComObjectValue-Schnittstelle
Stellt Methoden bereit, um Informationen abzurufen, die einem Runtime Callable Wrapper (RCW) zugeordnet sind.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetCachedInterfacePointers-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Ruft die unformatierten Schnittstellen Zeiger ab, die im aktuellen RCW zwischengespeichert werden.|  
|[GetCachedInterfaceTypes-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Stellt einen Enumerator für die Schnittstellentypen bereit, in die das aktuelle-Objekt geschrieben oder verwendet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Um zu überprüfen, ob eine Instanz einer ICorDebugValue-Schnittstelle einen RCW darstellt, Ruft ein Debugger `QueryInterface` für "ICorDebugValue" mit `IID_ICorDebugComObjectValue`auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
