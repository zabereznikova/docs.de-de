---
title: ICorDebugManagedCallback::LoadClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 6f1672d40cd495d3ec099abc703639cf52460703
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679662"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>ICorDebugManagedCallback::LoadClass-Methode

Benachrichtigt den Debugger, dass eine Klasse geladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in die die-Klasse geladen wurde.  
  
 `c`  
 in Ein Zeiger auf ein ICorDebugClass-Objekt, das die-Klasse darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Dieser Rückruf tritt nur auf, wenn das Laden von Klassen für das Modul aktiviert wurde, das die-Klasse enthält. Das Laden von Klassen ist für dynamische Module immer aktiviert.  
  
 Der `LoadClass` Rückruf bietet eine angemessene Zeit zum Binden von Breakpoints an neu generierte Klassen in dynamischen Modulen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [UnloadClass-Methode](icordebugmanagedcallback-unloadclass-method.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
