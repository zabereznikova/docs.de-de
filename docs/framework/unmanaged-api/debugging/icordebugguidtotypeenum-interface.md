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
ms.openlocfilehash: 149c5b09639c8809e736ade09566e7b1b530e3eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705708"
---
# <a name="icordebugguidtotypeenum-interface"></a>ICorDebugGuidToTypeEnum-Schnittstelle

Stellt einen Enumerator bereit, der die Zuordnung zwischen einem Satz von GUIDs und den entsprechenden Typen definiert, die von ICorDebugType-Instanzen dargestellt werden. Diese Schnittstelle erbt die Methoden von der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ICorDebug Type:: Next](icordebugguidtotypeenum-next-method.md)|Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.|  
  
## <a name="remarks"></a>Hinweise  

 Ein `ICorDebugGuidToTypeEnum` Schnittstellen Objekt kann durch Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](icordebugappdomain3-getcachedwinrttypes-method.md) -Methode abgerufen werden. Ein Debugger kann die [Next](icordebugguidtotypeenum-next-method.md) -Methode dieser Schnittstelle aufrufen, um [cordebugguidtotypemapping](cordebugguidtotypemapping-structure.md) -Objekte abzurufen, die Zuordnungen verwalteter Darstellungen von Windows-Runtime Typen darstellen, die in der Anwendungsdomäne geladen wurden, die für den Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](icordebugappdomain3-getcachedwinrttypes-method.md) -Methode verwendet wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
