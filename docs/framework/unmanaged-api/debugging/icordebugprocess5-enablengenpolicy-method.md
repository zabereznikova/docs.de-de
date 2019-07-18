---
title: ICorDebugProcess5::EnableNGENPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38ff08fa7e7db986006c4e0e09b1ac9cf1be801e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767147"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>ICorDebugProcess5::EnableNGENPolicy-Methode
Legt einen Wert, der bestimmt, wie eine Anwendung für systemeigene Images während der Ausführung unter einem verwalteten Debugger geladen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ePolicy`  
 [in] Ein [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) Konstante, die bestimmt, wie eine Anwendung für systemeigene Images während der Ausführung unter einem verwalteten Debugger geladen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Richtlinie erfolgreich festgelegt wurde, gibt die Methode `S_OK`. Wenn `ePolicy` liegt außerhalb des Bereichs, der durch definierten Enumerationswerte [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), gibt die Methode zurück `E_INVALIDARG` und Aufruf der Methode hat keine Auswirkungen. Die Methode gibt zurück, wenn die Richtlinie das Native Image Generator (Ngen.exe) kann nicht aktualisiert werden, `E_FAIL`.  
  
 Die `ICorDebugProcess5::EnableNGenPolicy` Methode kann zu einem beliebigen Zeitpunkt während der Lebensdauer des Prozesses aufgerufen werden. Die Richtlinie gilt für alle Module, die geladen werden, nachdem die Richtlinie festgelegt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
