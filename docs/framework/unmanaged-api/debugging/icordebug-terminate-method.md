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
ms.openlocfilehash: cf9c9d11c4725908fcf7ff4a0c91882b70a80190
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723375"
---
# <a name="icordebugterminate-method"></a>ICorDebug::Terminate-Methode

Beendet das- `ICorDebug` Objekt.  
  
> [!NOTE]
> `Terminate` sollte erst aufgerufen werden, wenn ein [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) -Rückruf für alle Prozesse empfangen wurde, die gedebuggt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>Hinweise  

 `Terminate` muss aufgerufen werden, wenn das `ICorDebug` Objekt nicht mehr benötigt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebug-Schnittstelle](icordebug-interface.md)
