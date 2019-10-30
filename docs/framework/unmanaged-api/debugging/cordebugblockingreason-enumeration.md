---
title: CorDebugBlockingReason-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: bc488e55bf64468eb62e2dc6eaedca62ebde3310
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098987"
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason-Enumeration
Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`BLOCKING_NONE`|Nur zur internen Verwendung.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Ein Thread versucht, den kritischen Abschnitt abzurufen, der der Überwachungs Sperre eines Objekts zugeordnet ist. Dies tritt normalerweise auf, wenn Sie eine der Methoden <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> oder <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> aufgerufen haben.|  
|`BLOCKING_MONITOR_EVENT`|Ein Thread wartet auf das Ereignis, das einer Monitor Sperre für ein Objekt zugeordnet ist. Dies tritt normalerweise auf, wenn Sie eine der <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` Methoden aufzurufen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `BLOCKING_MONITOR_CRITICAL_SECTION` oder `BLOCKING_MONITOR_EVENT` Member in einer [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Struktur verwendet wird, verweist der `pBlockingObject` Member der Struktur auf eine ICorDebug Value-Schnittstelle, die das Objekt darstellt, das eingegeben wird. Außerdem wird sichergestellt, dass die [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) -Schnittstelle implementiert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](debugging-enumerations.md)
- [Debuggen](index.md)
