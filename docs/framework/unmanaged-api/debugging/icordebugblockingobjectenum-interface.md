---
title: ICorDebugBlockingObjectEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: bfd61d985eac3ab56d8a5df9474b2b1a9f641f3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122842"
---
# <a name="icordebugblockingobjectenum-interface"></a>ICorDebugBlockingObjectEnum-Schnittstelle
Stellt einen Enumerator für eine Liste von [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Strukturen bereit. Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|Listet die [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Strukturen auf.|  
  
## <a name="remarks"></a>Hinweise  
 Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
