---
title: CorDebugBlockingObject-Struktur
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12a114ea65aca544d653704cdfb01ed15d19c581
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143220"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject-Struktur
Definiert ein Objekt, das blockiert einen Thread und die spezifische Ursache, dass der Thread blockiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pBlockingObject`|Das Objekt, auf dem der Thread blockiert wird. Dieses Objekt gilt nur für die Dauer des aktuellen Status "synchronisiert". Wenn zwei Threads für dasselbe Objekt innerhalb der gleichen Status "synchronisiert" blockiert werden, erwarten Sie möglicherweise die [ICorDebugValue:: GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) Methode, um den gleichen Wert zurück. Allerdings werden die Schnittstellen können oder möglicherweise keine äquivalente Zeiger.|  
|`dwTimeout`|Die Anzahl der Millisekunden, bevor der blockierende Vorgang wird das Timeout, oder der Wert INFINITE, der angibt, dass es kein Timeout. Der Timeout-Wert gibt die Gesamtlänge der blockierende Vorgang, nicht die Zeit, die noch verbleibenden ist.|  
|`blockingReason`|Der Grund für dieses Objekt der Thread blockiert ist.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
