---
title: ICorDebugValue3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 1f46866a1b975455acd294221e38ef3b4c358660
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140205"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3-Schnittstelle
Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays zu bieten, die größer als 2 GB sind.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetSize64-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|Ruft die Größe dieses `ICorDebugValue3` Objekts in Bytes ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) -Methode gibt eine Objektgröße zwischen 0 und 2.147.483.647 Byte zurück. Im .NET Framework 4,5 kann die Größe der Arrays 2 GB überschreiten. Die `ICorDebugValue3`-Schnittstelle ermöglicht es Ihnen, die Größe dieser Arrays zu bestimmen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
