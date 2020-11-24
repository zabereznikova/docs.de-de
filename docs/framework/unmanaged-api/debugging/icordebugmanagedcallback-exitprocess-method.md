---
title: ICorDebugManagedCallback::ExitProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 67f3e63b58e08a4b9ccfbd555e6edcdef0d00d90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688938"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>ICorDebugManagedCallback::ExitProcess-Methode

Benachrichtigt den Debugger, dass ein Prozess beendet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pProcess`  
 in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Ein Ereignis kann nicht fortgesetzt werden `ExitProcess` . Dieses Ereignis wird möglicherweise asynchron für andere Ereignisse ausgelöst, während der Prozess scheinbar beendet ist. Dies kann vorkommen, wenn der Prozess beendet wird, in der Regel aufgrund externer Kraft.  
  
 Wenn die Common Language Runtime (CLR) bereits einen verwalteten Rückruf sendet, wird dieses Ereignis verzögert, bis dieser Rückruf zurückgegeben wurde.  
  
 Das `ExitProcess` Ereignis ist das einzige Ereignis zum Beenden/entladen, das beim Herunterfahren garantiert aufgerufen wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
