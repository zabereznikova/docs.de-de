---
title: ICorDebugManagedCallback2::Exception-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.Exception
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a78900a6e37c3ae136489c35da7b0cd2931f24a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception-Methode
Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAppDomain`  
 [in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread, der der Ausnahme darstellt.  
  
 `pThread`  
 [in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die Ausnahme ausgelöst wurde.  
  
 `pFrame`  
 [in] Ein Zeiger auf ein ICorDebugFrame-Objekt, das einen Frame darstellt, durch die `dwEventType` Parameter. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".  
  
 `nOffset`  
 [in] Eine ganze Zahl, die einen Offset angibt, durch die `dwEventType` Parameter. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".  
  
 `dwEventType`  
 [in] Der Wert CorDebugExceptionCallbackType-Enumeration, die der den von diesem Ausnahmerückruf angibt.  
  
 `dwFlags`  
 [in] Der Wert der [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) Enumeration, die zusätzliche Informationen über die Ausnahme angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `Exception` aufgerufener Rückruf an verschiedenen Punkten während der Suche Phase des Prozesses für die Ausnahmebehandlung. D. h. es kann aufgerufen werden, mehr als einmal während Entladen einer Ausnahme.  
  
 Die Ausnahme, die verarbeitet werden kann abgerufen werden, aus dem ICorDebugThread-Objekt verweist die `pThread` Parameter.  
  
 Der jeweilige Frame und Offset hängen von der `dwEventType` Parameter wie folgt:  
  
|Wert von `dwEventType`|Wert von `pFrame`|Wert von `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Der Frame, der die Ausnahme ausgelöst hat.|Der Anweisungszeiger im Frame.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Der Benutzercode-Frames, die den Punkt der ausgelösten Ausnahme am nächsten.|Der Anweisungszeiger im Frame.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Der Frame, der den Catch-Handler enthält.|Der Microsoft intermediate Language (MSIL)-Offset des Anfangs des Catch-Handler.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Nicht definiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
