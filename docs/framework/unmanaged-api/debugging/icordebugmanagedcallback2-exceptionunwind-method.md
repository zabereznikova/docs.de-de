---
title: ICorDebugManagedCallback2::ExceptionUnwind-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
ms.openlocfilehash: fa317e1217ac0a9ca46bfeb312446534b1fca63a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131566"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a>ICorDebugManagedCallback2::ExceptionUnwind-Methode
Stellt während des Entwicklungs Vorgangs der Ausnahme eine Status Benachrichtigung bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread darstellt, für den die Ausnahme ausgelöst wurde.  
  
 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, für den die Ausnahme ausgelöst wurde.  
  
 `dwEventType`  
 in Ein Wert der CorDebugExceptionUnwindCallbackType-Enumeration, der das Ereignis angibt, das während der Entladephase durch den Rückruf signalisiert wird.  
  
 `dwFlags`  
 in Ein Wert der [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) -Enumeration, der zusätzliche Informationen über die Ausnahme angibt.  
  
## <a name="remarks"></a>Hinweise  
 `ExceptionUnwind` wird an verschiedenen Punkten während der Entladephase des Ausnahme Behandlungsprozesses aufgerufen. `ExceptionUnwind` kann mehrmals aufgerufen werden, während eine einzelne Ausnahme entwickelt wird.  
  
 Wenn `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, liegt der Anweisungs Zeiger im blattrahmen des Threads am Sequenz Punkt vor (möglicherweise mehrere Anweisungen vor) der Anweisung, die zur Ausnahme geführt hat.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
