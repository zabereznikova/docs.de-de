---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123378"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
[Wird in der .NET Framework 4,6 und höheren Versionen unterstützt]  
  
 Aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert von `enableExceptionsOutsideOfJMC``false` ist:  
  
- Eine DEBUG_EXCEPTION_FIRST_CHANCE-Ausnahme führt nicht zu einem Rückruf an den Debugger.  
  
- Eine DEBUG_EXCEPTION_CATCH_HANDLER_FOUND-Ausnahme führt nicht zu einem Rückruf an den Debugger, wenn die Ausnahme niemals in den Benutzercode Escapezeichen (d. h., der Pfad von einem Exception-Ursprung zu einem Ausnahme Handler hat keine Methoden, die als JustMyCode oder JMC gekennzeichnet sind).  
  
 Der Standardwert von `enableExceptionsOutsideOfJMC` ist `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess8-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
