---
title: ICorDebugManagedCallback::LoadModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 698a5cb88884febc4dfb3b916c00df20c1a77819
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679649"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a>ICorDebugManagedCallback::LoadModule-Methode

Benachrichtigt den Debugger, dass ein Common Language Runtime (CLR)-Modul erfolgreich geladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in die das Modul geladen wurde.  
  
 `pModule`  
 in Ein Zeiger auf ein ICorDebug Module-Objekt, das das CLR-Modul darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Der `LoadModule` Rückruf bietet eine angemessene Zeit zum Überprüfen der Metadaten für das Modul, zum Festlegen von Just-in-time (JIT)-Compilerflags oder zum Aktivieren oder Deaktivieren von Rückrufe zum Laden von Klassen für das Modul.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [UnloadModule-Methode](icordebugmanagedcallback-unloadmodule-method.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
