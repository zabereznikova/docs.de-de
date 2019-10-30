---
title: ICorDebugGuidToTypeEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138529"
---
# <a name="icordebugguidtotypeenum-interface"></a>ICorDebugGuidToTypeEnum-Schnittstelle
Stellt einen Enumerator bereit, der die Zuordnung zwischen einem Satz von GUIDs und den entsprechenden Typen definiert, die von ICorDebugType-Instanzen dargestellt werden. Diese Schnittstelle erbt die Methoden von der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ICorDebug Type:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugGuidToTypeEnum` Interface-Objekt kann durch Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) -Methode abgerufen werden. Ein Debugger kann die [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) -Methode dieser Schnittstelle aufrufen, um [cordebugguidtotypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Objekte abzurufen, die Zuordnungen verwalteter Darstellungen von Windows-Runtime Typen darstellen, die in der Anwendungsdomäne geladen werden, die für den Aufrufen [des ICorDebugAppDomain3:: getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) -Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
