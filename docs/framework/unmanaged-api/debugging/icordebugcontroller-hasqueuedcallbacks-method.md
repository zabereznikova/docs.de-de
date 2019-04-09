---
title: ICorDebugController::HasQueuedCallbacks-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce6ad24e5e670db21d3a6942ab4650a68ae44568
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102692"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks-Methode
Ruft einen Wert, der angibt, ob die verwalteten Rückrufe derzeit für den angegebenen Thread in der Warteschlange befinden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pThread`  
 [in] Ein Zeiger auf ein "ICorDebugThread"-Objekt, das den Thread darstellt.  
  
 `pbQueued`  
 [out] Ein Zeiger auf einen Wert `true` , wenn die verwalteten Rückrufe aktuell, in der Warteschlange für den angegebenen Thread ist, andernfalls sind `false`.  
  
 Wenn Null, für angegeben wird die `pThread` Parameter `HasQueuedCallbacks` zurück `true` Wenn sind verwaltete Rückrufe in der Warteschlange für einen beliebigen Thread.  
  
## <a name="remarks"></a>Hinweise  
 Rückrufe werden verteilten einzeln nacheinander, jedes Mal [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufgerufen wird. Der Debugger kann dieses Flag überprüfen, wenn sie mehrere Debug-Ereignisse melden, die gleichzeitig auftreten will.  
  
 Wenn Debugereignisse in der Warteschlange befinden, haben sie bereits erfolgt, damit der Debugger die gesamte Warteschlange aus, um sicherzustellen, dass des Zustands der zu debuggenden Komponente ausgleichen muss. (Rufen `ICorDebugController::Continue` an die Warteschlange zu leeren.) Wenn die Warteschlange zwei Debugereignisse Thread enthält z. B. *X*, und der Debugger hält die Threads *X* nach dem die erste Debug-Ereignis und ruft dann `ICorDebugController::Continue`, das zweite Debugereignis für Thread *X* wird weitergeleitet werden, auch wenn der Thread angehalten wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
