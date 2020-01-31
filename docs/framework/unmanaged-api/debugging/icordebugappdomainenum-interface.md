---
title: ICorDebugAppDomainEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 9fb849c78636d5e29f58a70f59aa4cb3cd22df40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784736"
---
# <a name="icordebugappdomainenum-interface"></a>ICorDebugAppDomainEnum-Schnittstelle

Stellt die `Next`-Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomainEnum` Werten zurückgibt, beginnend an der nächsten Position in der-Enumeration. Bei dieser Schnittstelle handelt es sich um eine Unterklasse von "ICorDebugEnum".  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](icordebugappdomainenum-next-method.md)|Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](icordebug-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
