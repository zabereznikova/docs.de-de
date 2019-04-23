---
title: ICorDebugValue2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6718bbfdb1825b9f01698d76deec3fab16cb2ac6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091602"
---
# <a name="icordebugvalue2-interface"></a>ICorDebugValue2-Schnittstelle
Erweitert die Schnittstelle "ICorDebugValue", um Unterstützung für "ICorDebugType"-Objekte bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetExactType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|Ruft einen Schnittstellenzeiger auf ein `ICorDebugType` -Objekt, das stellt die <xref:System.Type> dieses Werts.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [ICorDebugValue3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
