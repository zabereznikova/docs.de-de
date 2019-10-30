---
title: ICorDebugManagedCallback::Exception-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
ms.openlocfilehash: af2dab65629093401219f1016538b912bee4d067
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130827"
---
# <a name="icordebugmanagedcallbackexception-method"></a>ICorDebugManagedCallback::Exception-Methode
Benachrichtigt den Debugger, dass eine Ausnahme von verwaltetem Code ausgelöst wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Ausnahme ausgelöst wurde.  
  
 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Ausnahme ausgelöst wurde.  
  
 `unhandled`  
 in Wenn dieser Wert `false`ist, wurde die Ausnahme noch nicht von der Anwendung verarbeitet. Andernfalls wird die Ausnahme nicht behandelt, und der Prozess wird beendet.  
  
## <a name="remarks"></a>Hinweise  
 Die spezifische Ausnahme kann aus dem Thread Objekt abgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
