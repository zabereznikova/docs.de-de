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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b8ac6751024e64cc866fce1cfe72fb42e41200
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760436"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>ICorDebugManagedCallback::ExitProcess-Methode
Benachrichtigt den Debugger an, dass ein Prozess beendet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pProcess`  
 [in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können nicht fortgesetzt werden, von einem `ExitProcess` Ereignis. Dieses Ereignis kann asynchron mit anderen Ereignissen ausgelöst werden, während der Prozess angezeigt wird, beendet werden soll. Dies kann auftreten, wenn der Prozess beendet wird, während angehalten, in der Regel aufgrund von einigen externen erzwingen.  
  
 Wenn die common Language Runtime (CLR) bereits einen verwalteten Rückruf sendet, wird dieses Ereignis bis verzögert werden, nachdem dieser Rückruf zurückgegeben wurde.  
  
 Die `ExitProcess` Ereignis ist das einzige Beenden/Entladen-Ereignis, die mit Sicherheit beim Herunterfahren aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
