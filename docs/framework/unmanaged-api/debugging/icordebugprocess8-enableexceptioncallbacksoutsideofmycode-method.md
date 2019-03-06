---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fc7f34059660c273055c3ee24fb6722fda1ef3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466556"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
[Unterstützt in [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] und höheren Versionen]  
  
 Aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) ausnahmerückrufen.  
  
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
  
-   Eine Ausnahme DEBUG_EXCEPTION_FIRST_CHANCE führt nicht in einem Rückruf an den Debugger.  
  
-   Eine Ausnahme DEBUG_EXCEPTION_CATCH_HANDLER_FOUND nicht führt einen Rückruf an den Debugger, wenn die Ausnahme in Benutzercode nie zum Abbruch (d. h. der Pfad aus einem Ursprung der Ausnahme zu einem Ausnahmehandler verfügt über keine Methoden als JustMyCode oder "JMC" markiert).  
  
 Der Standardwert von `enableExceptionsOutsideOfJMC` ist `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugProcess8-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
