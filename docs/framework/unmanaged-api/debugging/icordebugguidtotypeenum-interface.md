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
ms.openlocfilehash: 2663e5604cdd55472cc148b2d2b38599df81f11e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794439"
---
# <a name="icordebugguidtotypeenum-interface"></a>ICorDebugGuidToTypeEnum-Schnittstelle
Stellt einen Enumerator bereit, der die Zuordnung zwischen einem Satz von GUIDs und den entsprechenden Typen definiert, die von ICorDebugType-Instanzen dargestellt werden. Diese Schnittstelle erbt die Methoden von der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[ICorDebugGuidToTypeEnum::Next](icordebugguidtotypeenum-next-method.md)|Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugGuidToTypeEnum` Interface-Objekt kann durch Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](icordebugappdomain3-getcachedwinrttypes-method.md) -Methode abgerufen werden. Ein Debugger kann die [Next](icordebugguidtotypeenum-next-method.md) -Methode dieser Schnittstelle aufrufen, um [cordebugguidtotypemapping](cordebugguidtotypemapping-structure.md) -Objekte abzurufen, die Zuordnungen verwalteter Darstellungen von Windows-Runtime Typen darstellen, die in der Anwendungsdomäne geladen wurden, die für den Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](icordebugappdomain3-getcachedwinrttypes-method.md) -Methode verwendet wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
