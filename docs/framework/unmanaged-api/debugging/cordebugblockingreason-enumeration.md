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
ms.openlocfilehash: ddd03d70656ad52fd9d577beedc60b51c7b305d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672850"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`BLOCKING_NONE`|Nur zur internen Verwendung.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Ein Thread versucht, den kritischen Abschnitt abzurufen, der der Überwachungs Sperre eines Objekts zugeordnet ist. Dies tritt normalerweise auf, wenn Sie eine der-oder-Methoden aufzurufen <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> .|  
|`BLOCKING_MONITOR_EVENT`|Ein Thread wartet auf das Ereignis, das einer Monitor Sperre für ein Objekt zugeordnet ist. Dies tritt normalerweise auf, wenn Sie eine der-Methoden aufzurufen <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` .|  
  
## <a name="remarks"></a>Hinweise  

 Wenn das-Element oder das-Element `BLOCKING_MONITOR_CRITICAL_SECTION` `BLOCKING_MONITOR_EVENT` in einer [corunbugblockingobject](cordebugblockingobject-structure.md) -Struktur verwendet wird, verweist der- `pBlockingObject` Member der-Struktur auf eine ICorDebug Value-Schnittstelle, die das Objekt darstellt, das eingegeben wird. Außerdem wird sichergestellt, dass die [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) -Schnittstelle implementiert wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
- [Debuggen](index.md)
