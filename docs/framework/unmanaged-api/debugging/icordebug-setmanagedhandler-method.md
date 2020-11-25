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
ms.openlocfilehash: 97a4a464d3dfb7b333f44ac4206bd880fd171e16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723414"
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
 in Ein Zeiger auf ein [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Objekt, das das Ereignishandlerobjekt ist.  
  
## <a name="remarks"></a>Hinweise  

 `SetManagedHandler` muss zur Erstellungszeit aufgerufen werden.  
  
 Wenn die- `ICorDebugManagedCallback` Implementierung keine ausreichenden Schnittstellen zur Behandlung von debuggingereignissen für die zu debuggende Anwendung enthält, wird `SetManagedHandler` ein HRESULT E_NOINTERFACE zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebug-Schnittstelle](icordebug-interface.md)
