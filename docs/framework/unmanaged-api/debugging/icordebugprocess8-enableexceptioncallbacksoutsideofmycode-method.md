---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7de3622498e8417a961e0d4708c53527a833ef2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
#### <a name="parameters"></a>Parameter  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert von `enableExceptionsOutsideOfJMC` `false` ist:  
  
-   Eine Ausnahme DEBUG_EXCEPTION_FIRST_CHANCE führt nicht in einen Rückruf an den Debugger.  
  
-   Eine Ausnahme DEBUG_EXCEPTION_CATCH_HANDLER_FOUND nicht führt einen Rückruf an den Debugger, wenn die Ausnahme kein in Benutzercode Escapevorgang (d. h. der Pfad aus einem Ursprung der Ausnahme zu einem Ausnahmehandler verfügt über keine Methoden als JustMyCode oder "JMC" markiert).  
  
 Der Standardwert von `enableExceptionsOutsideOfJMC` ist `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess8-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
