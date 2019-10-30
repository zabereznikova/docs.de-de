---
title: ICorDebugManagedCallback2::Exception-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: f40030a2034057e83de51a21655a686f30b9ee88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137453"
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception-Methode
Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread darstellt, für den die Ausnahme ausgelöst wurde.  
  
 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, für den die Ausnahme ausgelöst wurde.  
  
 `pFrame`  
 in Ein Zeiger auf ein ICorDebug Frame-Objekt, das einen Frame darstellt, wie vom `dwEventType`-Parameter festgelegt. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".  
  
 `nOffset`  
 in Eine ganze Zahl, die einen Offset angibt, der vom `dwEventType`-Parameter bestimmt wird. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".  
  
 `dwEventType`  
 in Ein Wert der CorDebugExceptionCallbackType-Enumeration, der den Typ dieses Ausnahme Rückrufs angibt.  
  
 `dwFlags`  
 in Ein Wert der [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) -Enumeration, der zusätzliche Informationen über die Ausnahme angibt.  
  
## <a name="remarks"></a>Hinweise  
 Der `Exception` Rückruf wird an verschiedenen Punkten während der Suchphase des Ausnahme Behandlungsprozesses aufgerufen. Das heißt, dass Sie mehrmals aufgerufen werden kann, während Sie eine Ausnahme entwickeln.  
  
 Die zu verarbeitende Ausnahme kann aus dem ICorDebugThread-Objekt abgerufen werden, auf das durch den `pThread`-Parameter verwiesen wird.  
  
 Der jeweilige Frame und der Offset werden vom `dwEventType`-Parameter wie folgt bestimmt:  
  
|Wert von `dwEventType`|Wert von `pFrame`|Wert von `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Der Frame, der die Ausnahme ausgelöst hat.|Der Anweisungs Zeiger im Frame.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Der Benutzercode Rahmen, der dem Punkt der ausgelösten Ausnahme am nächsten ist.|Der Anweisungs Zeiger im Frame.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Der Frame, der den catch-Handler enthält.|Der MSIL-Offset (Microsoft Intermediate Language) am Anfang des catch-Handlers.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Definiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
