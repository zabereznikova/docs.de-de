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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3c430e18864c0352b43641bce9a7d52af69cc80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718220"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>ICorDebugManagedCallback::LoadClass-Methode
Benachrichtigt den Debugger, dass eine Klasse geladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAppDomain`  
 [in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Klasse geladen wurde.  
  
 `c`  
 [in] Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf erfolgt nur, wenn Laden von Klassen für das Modul aktiviert wurde, die die Klasse enthält. Laden von Klassen ist bei dynamischen Modulen immer aktiviert.  
  
 Die `LoadClass` Rückruf stellt einen geeigneten Zeitpunkt zum Binden von Haltepunkten an neu generierten Klassen in dynamischen Modulen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [UnloadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
