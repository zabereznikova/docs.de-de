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
ms.openlocfilehash: 419efc7f21f4ac2e68657b2a4d69a8690a2938d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722309"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3-Schnittstelle

Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays zu bieten, die größer als 2 GB sind.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetSize64-Methode](icordebugvalue3-getsize64-method.md)|Ruft die Größe des-Objekts in Bytes ab `ICorDebugValue3` .|  
  
## <a name="remarks"></a>Hinweise  

 Die [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) -Methode gibt eine Objektgröße zwischen 0 und 2.147.483.647 Byte zurück. Im .NET Framework 4,5 kann die Größe der Arrays 2 GB überschreiten. Die- `ICorDebugValue3` Schnittstelle ermöglicht es Ihnen, die Größe dieser Arrays zu bestimmen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
