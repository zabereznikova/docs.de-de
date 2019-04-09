---
title: ICorDebugStackWalk-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e33e9be112a6a10f89b88005496ce2e63dff2d54
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080682"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk-Schnittstelle
Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Gibt den Kontext für den aktuellen Frame in der `ICorDebugStackWalk` Objekt.|  
|[SetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Legt die `ICorDebugStackWalk` aktuellen Kontext des Objekts, auf einen gültigen Kontext für den Thread.|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Verschiebt die `ICorDebugStackWalk` Objekt zum nächsten Frame.|  
|[GetFrame-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Ruft den aktuellen Frame in der `ICorDebugStackWalk` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
