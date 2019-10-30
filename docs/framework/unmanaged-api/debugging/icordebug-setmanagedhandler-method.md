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
ms.openlocfilehash: 88a007654646ba42ebcaf1b42e002282a1040c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134054"
---
# <a name="icordebugsetmanagedhandler-method"></a>ICorDebug::SetManagedHandler-Methode
Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCallback`  
 in Ein Zeiger auf ein [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) -Objekt, das das Ereignishandlerobjekt ist.  
  
## <a name="remarks"></a>Hinweise  
 `SetManagedHandler` muss zur Erstellungszeit aufgerufen werden.  
  
 Wenn die `ICorDebugManagedCallback`-Implementierung nicht genügend Schnittstellen zum Verarbeiten von Debugereignissen für die zu debuggende Anwendung enthält, gibt `SetManagedHandler` ein HRESULT von E_NOINTERFACE zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
