---
title: CorDebugBlockingReason-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingReason
helpviewer_keywords: CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 505a83f15d5056b0280af31d372623530d6e66ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason-Enumeration
Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Ein Thread versucht, den kritischen Abschnitt abzurufen, der die Monitorsperre für ein Objekt zugeordnet ist. In der Regel tritt dies auf, wenn eine Aufrufen der <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> oder <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> Methoden.|  
|`BLOCKING_MONITOR_EVENT`|Ein Thread wartet auf das Ereignis, das einen Monitorsperre für ein Objekt zugeordnet ist. In der Regel tritt dies auf, wenn eine Aufrufen der <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` Methoden.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `BLOCKING_MONITOR_CRITICAL_SECTION` oder `BLOCKING_MONITOR_EVENT` Element wird verwendet, eine [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Struktur, die `pBlockingObject` Mitglied der Struktur-verweist auf eine "ICorDebugValue"-Schnittstelle, die das Objekt darstellt, die aufgerufen wird . Es ist auch gewährleistet, dass implementieren die [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
