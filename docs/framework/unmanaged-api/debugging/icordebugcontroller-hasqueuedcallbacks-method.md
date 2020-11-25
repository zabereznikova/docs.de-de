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
ms.openlocfilehash: bd623f8bee2feafebe80c0c7513bcfb33d6ad367
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707904"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks-Methode

Ruft einen Wert ab, der angibt, ob verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt.  
  
 `pbQueued`  
 vorgenommen Ein Zeiger auf einen-Wert, der ist, `true` Wenn verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden, andernfalls `false` .  
  
 Wenn NULL für den-Parameter angegeben wird `pThread` , `HasQueuedCallbacks` gibt zurück, `true` Wenn derzeit verwaltete Rückrufe für einen beliebigen Thread in die Warteschlange eingereiht werden.  
  
## <a name="remarks"></a>Hinweise  

 Rückrufe werden einzeln verteilt, jedes Mal, wenn " [icordbugcontroller:: Continue](icordebugcontroller-continue-method.md) " aufgerufen wird. Der Debugger kann dieses Flag überprüfen, wenn mehrere Debugereignisse, die gleichzeitig auftreten, gemeldet werden sollen.  
  
 Wenn Debugereignisse in die Warteschlange eingereiht werden, sind Sie bereits aufgetreten, sodass der Debugger die gesamte Warteschlange entfernen muss, um sicherzustellen, dass der Zustand der zu debuggenden Komponente sicher ist. ( `ICorDebugController::Continue` Zum leeren der Warteschlange aufzurufen.) Wenn die Warteschlange z. b. zwei Debuggingereignisse für Thread *x* enthält und der Debugger Thread *x* nach dem ersten Debugereignis anhält und dann aufruft `ICorDebugController::Continue` , wird das zweite Debugereignis für Thread *x* gesendet, obwohl der Thread angehalten wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
