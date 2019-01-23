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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eee75bc16f46ba5ea58fc42c570e48b09ab9a2e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553229"
---
# <a name="icordebugstackwalknext-method"></a>ICorDebugStackWalk::Next-Methode
Verschiebt die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt zum nächsten Frame.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Laufzeit Entladevorgang erfolgreich bis zum nächsten Frame (siehe Hinweise).|  
|E_FAIL|Die `ICorDebugStackWalk` Objekt konnte nicht erweitert werden.|  
|CORDBG_S_AT_END_OF_STACK|Das Ende des Stapels wurde als Ergebnis dieser Entladung erreicht.|  
|CORDBG_E_PAST_END_OF_STACK|Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Die `Next` Methode Fortschritte der `ICorDebugStackWalk` Objekt an den aufrufenden Rahmen nur dann, wenn die Laufzeit den aktuellen Rahmen entladen werden kann. Andernfalls setzt sich das Objekt in den nächsten Frame, den die Laufzeit entladen werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugStackWalk-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
