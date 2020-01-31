---
title: ICorDebugILFrame3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: 739c648173d45a9c147ea2a4e469a3a4b518e893
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794334"
---
# <a name="icordebugilframe3-interface"></a>ICorDebugILFrame3-Schnittstelle
Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt. `ICorDebugILFrame3` ist eine logische Erweiterung der ICorDebugILFrame-Schnittstelle und der ICorDebugILFrame2-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetReturnValueForILOffset-Methode](icordebugilframe3-getreturnvalueforiloffset-method.md)|Ruft ein ICorDebugValue-Objekt ab, das den Rückgabewert einer Funktion kapselt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
