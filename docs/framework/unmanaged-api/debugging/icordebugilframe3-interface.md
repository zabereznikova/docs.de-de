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
ms.openlocfilehash: dab5329086971b9349deaf84535fa251744f3cf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724987"
---
# <a name="icordebugilframe3-interface"></a>ICorDebugILFrame3-Schnittstelle

Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt. `ICorDebugILFrame3` ist eine logische Erweiterung der ICorDebugILFrame- und ICorDebugILFrame2-Schnittstellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetReturnValueForILOffset-Methode](icordebugilframe3-getreturnvalueforiloffset-method.md)|Ruft ein ICorDebugValue-Objekt ab, das den Rückgabewert einer Funktion kapselt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
