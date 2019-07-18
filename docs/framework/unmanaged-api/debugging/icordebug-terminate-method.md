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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3037fc704ffc3aac4d050cef7857261f138f7d35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738071"
---
# <a name="icordebugterminate-method"></a>ICorDebug::Terminate-Methode
Beendet die `ICorDebug` Objekt.  
  
> [!NOTE]
>  `Terminate` sollte nicht aufgerufen werden, bis ein [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf für alle im Debugmodus befindlichen Prozesse empfangen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>Hinweise  
 `Terminate` muss aufgerufen werden, wenn die `ICorDebug` Objekt ist nicht mehr benötigt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
