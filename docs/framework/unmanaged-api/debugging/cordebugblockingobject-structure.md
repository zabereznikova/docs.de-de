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
ms.openlocfilehash: 21f90e06b3b02ebc6c97610b6edc35697601f0ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132285"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject-Struktur
Definiert ein Objekt, das einen Thread blockiert, und den spezifischen Grund, aus dem der Thread blockiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`pBlockingObject`|Das Objekt, für das der Thread blockiert wird. Dieses Objekt ist nur für die Dauer des aktuellen synchronisierten Zustands gültig. Wenn zwei Threads für das gleiche Objekt innerhalb desselben synchronisierten Zustands blockieren, erwarten Sie möglicherweise, dass die [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) -Methode denselben Wert zurückgibt. Allerdings sind die Schnittstellen möglicherweise Zeiger Äquivalent.|  
|`dwTimeout`|Die Anzahl von Millisekunden, bevor ein Timeout auftritt, oder der Wert ist unendlich, was darauf hinweist, dass kein Timeout auftritt. Der Timeout Wert gibt die Gesamtzeit für den blockierenden Vorgang an, nicht die Zeit, die noch übrig ist.|  
|`blockingReason`|Der Grund, warum der Thread für dieses Objekt blockiert ist.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
