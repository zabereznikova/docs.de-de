---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 750d2a2d69c74e147c34c9c496079ee48ac04b42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732540"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode

[Wird in der .NET Framework 4,6 und höheren Versionen unterstützt]  
  
 Aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen.  
  
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
  
- Eine DEBUG_EXCEPTION_FIRST_CHANCEAusnahme führt nicht zu einem Rückruf an den Debugger.  
  
- Eine DEBUG_EXCEPTION_CATCH_HANDLER_FOUND-Ausnahme führt nicht zu einem Rückruf an den Debugger, wenn für die Ausnahme kein Escapevorgang in Benutzercode erfolgt (d. h. der Pfad aus einem Ursprung der Ausnahme zu einem Ausnahmehandler über keine Methoden verfügt, die als "JustMyCode" oder "JMC" markiert ist).  
  
 Der Standardwert von `enableExceptionsOutsideOfJMC` ist `true`.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess8-Schnittstelle](icordebugprocess8-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
