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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faba9631e85ac84ff1517b64e9a3f5567ee7c9dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995032"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a>ICorDebugManagedCallback2::ExceptionUnwind-Methode
Stellt eine Benachrichtigung zum Status während des endladungsprozesses Ausnahme bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAppDomain`  
 [in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das mit dem Thread, der auf dem die Ausnahme ausgelöst wurde der Anwendungsdomäne darstellt.  
  
 `pThread`  
 [in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die Ausnahme ausgelöst wurde.  
  
 `dwEventType`  
 [in] Der Wert der CorDebugExceptionUnwindCallbackType-Enumeration, der das Ereignis gibt an, das durch den Rückruf während der Entladephase signalisiert wird.  
  
 `dwFlags`  
 [in] Der Wert der [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) -Enumeration, die zusätzliche Informationen über die Ausnahme angibt.  
  
## <a name="remarks"></a>Hinweise  
 `ExceptionUnwind` an verschiedenen Punkten wird während der Entladephase des Prozesses für die Ausnahmebehandlung aufgerufen. `ExceptionUnwind` kann mehrere Male während der stapelentladung einer Ausnahme aufgerufen werden.  
  
 Wenn `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, befindet sich der Anweisungszeiger werden in Endframe des Threads, an dem Sequenzpunkt (Dies kann mehrere Anweisungen vor sein) die Anweisung, die auf die Ausnahme geführt hat.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
