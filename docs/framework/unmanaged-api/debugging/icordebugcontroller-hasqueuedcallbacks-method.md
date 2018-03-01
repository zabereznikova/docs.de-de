---
title: ICorDebugController::HasQueuedCallbacks-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03d52bb31a81876a00e1af33494b14fb99fee0fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks-Methode
Ruft einen Wert, der angibt, ob die verwalteten Rückrufe zurzeit für den angegebenen Thread in der Warteschlange befinden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pThread`  
 [in] Ein Zeiger auf ein "ICorDebugThread"-Objekt, das den Thread darstellt.  
  
 `pbQueued`  
 [out] Ein Zeiger auf einen Wert, der `true` , wenn die verwalteten Rückrufe derzeit in der Warteschlange für den angegebenen Thread ist, andernfalls werden `false`.  
  
 Wenn Null, für angegeben wird die `pThread` Parameter `HasQueuedCallbacks` zurück `true` falls derzeit verwaltete Rückrufe in der Warteschlange für einen beliebigen Thread.  
  
## <a name="remarks"></a>Hinweise  
 Rückrufe werden verteilter einzeln nacheinander, jedes Mal [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufgerufen wird. Der Debugger kann dieses Flag überprüfen Sie, ob mehrere Debug-Ereignisse gemeldet, die gleichzeitig ausgeführt werden sollen.  
  
 Wenn Debug-Ereignisse in der Warteschlange befinden, sind sie bereits aufgetreten, sodass der Debugger die gesamte Warteschlange, um sicherzustellen, dass des Zustands der zu debuggenden Komponente ausgleichen muss. (Rufen `ICorDebugController::Continue` Ausgleich die Warteschlange.) Wenn die Warteschlange zwei Debugereignisse Thread enthält z. B. *X*, und der Debugger hält den Thread *X* nach der ersten Debug-Ereignis und ruft dann `ICorDebugController::Continue`, das zweite Debugereignis für Thread *X* wird weitergeleitet werden, obwohl der Thread angehalten wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
