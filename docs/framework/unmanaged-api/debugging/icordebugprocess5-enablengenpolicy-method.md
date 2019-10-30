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
ms.openlocfilehash: 583819e8e7ab16a8ac1ce72892f4353e3043ce3d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129689"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>ICorDebugProcess5::EnableNGENPolicy-Methode
Legt einen Wert fest, der bestimmt, wie eine Anwendung systemeigene Images lädt, während Sie unter einem verwalteten Debugger ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ePolicy`  
 in Eine [cordebugngenpolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) -Konstante, die bestimmt, wie eine Anwendung systemeigene Images lädt, während Sie unter einem verwalteten Debugger ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Richtlinie erfolgreich festgelegt wurde, gibt die Methode `S_OK`zurück. Wenn `ePolicy` außerhalb des Bereichs der durch [cordebugngenpolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)definierten Enumerationswerte liegt, gibt die Methode `E_INVALIDARG` zurück, und der Methodenaufruf hat keine Auswirkungen. Wenn die Richtlinie des Native Image Generator (Ngen. exe) nicht aktualisiert werden kann, gibt die Methode `E_FAIL`zurück.  
  
 Die `ICorDebugProcess5::EnableNGenPolicy`-Methode kann zu einem beliebigen Zeitpunkt während der Lebensdauer des Prozesses aufgerufen werden. Die Richtlinie ist für alle Module wirksam, die geladen werden, nachdem die Richtlinie festgelegt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
