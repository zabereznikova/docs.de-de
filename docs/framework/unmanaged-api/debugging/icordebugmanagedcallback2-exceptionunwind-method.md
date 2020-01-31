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
ms.openlocfilehash: 482afd09ce370fb1247864b9ac2032ee7e3a1dca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788274"
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
  
## <a name="parameters"></a>Parameters  
 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread darstellt, für den die Ausnahme ausgelöst wurde.  
  
 `pThread`  
 [in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die Ausnahme ausgelöst wurde.  
  
 `dwEventType`  
 in Ein Wert der CorDebugExceptionUnwindCallbackType-Enumeration, der das Ereignis angibt, das während der Entladephase durch den Rückruf signalisiert wird.  
  
 `dwFlags`  
 in Ein Wert der [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) -Enumeration, der zusätzliche Informationen über die Ausnahme angibt.  
  
## <a name="remarks"></a>Hinweise  
 `ExceptionUnwind` wird an verschiedenen Punkten während der Entladephase des Ausnahme Behandlungsprozesses aufgerufen. `ExceptionUnwind` kann mehrmals aufgerufen werden, während eine einzelne Ausnahme entwickelt wird.  
  
 Wenn `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, wird der Anweisungs Zeiger im blattrahmen des Threads am Sequenz Punkt vor (möglicherweise mehrere Anweisungen vor) der Anweisung angezeigt, die zur Ausnahme geführt hat.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
