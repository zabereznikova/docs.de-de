---
title: ICorDebugHeapValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5fcd8c17c4006714fa9d11aece5cccc57c97087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700825"
---
# <a name="icordebugheapvalue-interface"></a>ICorDebugHeapValue-Schnittstelle

Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, die von der Garbage Collector der common Language Runtime (CLR) gesammelt wurden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateRelocBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|Nicht implementiert.|  
|[IsValid-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|Ruft einen Wert, der angibt, ob das Objekt von diesem dargestellt `ICorDebugHeapValue` ist ungültig, oder durch den Garbage Collector zurückgefordert wurde. Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
