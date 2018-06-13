---
title: ICorDebug::SetManagedHandler-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcf97f9fffabb9ae9579016517cfc335e6f783a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404572"
---
# <a name="icordebugsetmanagedhandler-method"></a>ICorDebug::SetManagedHandler-Methode
Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCallback`  
 [in] Ein Zeiger auf ein [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) -Objekt, das das Ereignishandlerobjekt fungiert.  
  
## <a name="remarks"></a>Hinweise  
 `SetManagedHandler` muss zum Zeitpunkt der Erstellung aufgerufen werden.  
  
 Wenn die `ICorDebugManagedCallback` Implementierung enthält keine ausreichende Schnittstellen um Debugereignisse für die Anwendung zu behandeln, der debuggt wird, `SetManagedHandler` gibt ein HRESULT E_NOINTERFACE zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
