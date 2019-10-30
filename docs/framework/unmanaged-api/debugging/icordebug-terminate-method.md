---
title: ICorDebug::Terminate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 78838e9002cb3f5263395af9de255c54de47b6ae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134015"
---
# <a name="icordebugterminate-method"></a>ICorDebug::Terminate-Methode
Beendet das `ICorDebug`-Objekt.  
  
> [!NOTE]
> `Terminate` sollte erst aufgerufen werden, wenn ein [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) -Rückruf für alle Prozesse empfangen wurde, die gedebuggt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>Hinweise  
 `Terminate` müssen aufgerufen werden, wenn das `ICorDebug` Objekt nicht mehr benötigt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
