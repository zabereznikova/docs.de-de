---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68dae3839cfb4d04797d81bca41ee212a64cca51
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751565"
---
# <a name="icordebugprocess6processstatechanged-method"></a>ICorDebugProcess6::ProcessStateChanged-Methode
Benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a>Parameter  
 `change`  
 [in] Ein Mitglied der [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) Enumeration  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger ruft diese Methode benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess6-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
