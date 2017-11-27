---
title: ICorDebugHeapValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue
helpviewer_keywords: ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868fc84ba3003909992334d1a66e1ed243eca18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue-interface1"></a>ICorDebugHeapValue Schnittstelle1
Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, die von der Garbage Collector der common Language Runtime (CLR) gesammelt wurden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateRelocBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|Nicht implementiert.|  
|[IsValid-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|Ruft einen Wert, der angibt, ob das Objekt von diesem dargestellt `ICorDebugHeapValue` ist ungültig oder wurde durch den Garbage Collector freigegeben wurde. Diese Methode ist in .NET Framework, Version 2.0 veraltet.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
    
    
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
