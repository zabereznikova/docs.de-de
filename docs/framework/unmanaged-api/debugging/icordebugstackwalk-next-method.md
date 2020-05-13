---
title: ICorDebugStackWalk::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b89e968e9b12943c8192af3b280f8bd321a02110
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378787"
---
# <a name="icordebugstackwalknext-method"></a>ICorDebugStackWalk::Next-Methode
Verschiebt das [icorentbugstackwalk](icordebugstackwalk-interface.md) -Objekt in den nächsten Frame.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Laufzeit wurde erfolgreich auf den nächsten Frame aufgelöst (siehe Hinweise).|  
|E_FAIL|Das `ICorDebugStackWalk` Objekt konnte nicht erweitert werden.|  
|CORDBG_S_AT_END_OF_STACK|Das Ende des Stapels wurde als Ergebnis dieser Entladung erreicht.|  
|CORDBG_E_PAST_END_OF_STACK|Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Die- `Next` Methode verschiebt das `ICorDebugStackWalk` Objekt nur dann auf den aufrufenden Frame, wenn die Laufzeit den aktuellen Frame entladen kann. Andernfalls wechselt das Objekt zum nächsten Frame, der von der Laufzeit entladen werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugStackWalk-Schnittstelle](icordebugstackwalk-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
