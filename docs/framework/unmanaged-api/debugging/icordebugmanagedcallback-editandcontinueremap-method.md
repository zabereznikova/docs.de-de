---
title: ICorDebugManagedCallback::EditAndContinueRemap-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
ms.openlocfilehash: 1d8aa2cca9dbbeaa9e03813b177ca59125770803
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721282"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a>ICorDebugManagedCallback::EditAndContinueRemap-Methode

Diese Methode ist veraltet. Der Debugger wird benachrichtigt, dass ein Umwandlungs-Ereignis an die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) gesendet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a>Hinweise  

 Die- `EditAndContinueRemap` Methode wird aufgerufen, wenn versucht wurde, den Code in einer alten Version einer aktualisierten Funktion auszuführen. Der Common Language Runtime ruft die- `EditAndContinueRemap` Methode auf, um ein Umwandlungs-Ereignis an die IDE zu senden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
