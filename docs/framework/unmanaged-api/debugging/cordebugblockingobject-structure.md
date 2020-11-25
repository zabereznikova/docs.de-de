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
ms.openlocfilehash: b16feb1af0d4975411876e78940d21096750d2ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726585"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`pBlockingObject`|Das Objekt, für das der Thread blockiert wird. Dieses Objekt ist nur für die Dauer des aktuellen synchronisierten Zustands gültig. Wenn zwei Threads für das gleiche Objekt innerhalb desselben synchronisierten Zustands blockieren, erwarten Sie möglicherweise, dass die [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) -Methode denselben Wert zurückgibt. Allerdings sind die Schnittstellen möglicherweise Zeiger Äquivalent.|  
|`dwTimeout`|Die Anzahl von Millisekunden, bevor ein Timeout auftritt, oder der Wert ist unendlich, was darauf hinweist, dass kein Timeout auftritt. Der Timeout Wert gibt die Gesamtzeit für den blockierenden Vorgang an, nicht die Zeit, die noch übrig ist.|  
|`blockingReason`|Der Grund, warum der Thread für dieses Objekt blockiert ist.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
