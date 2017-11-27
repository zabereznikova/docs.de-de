---
title: ICorDebugProcess5::EnableNGENPolicy-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5::EnableNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd259308494e1a86f0a6cdec8866bb66a1614b76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>ICorDebugProcess5::EnableNGENPolicy-Methode
Legt einen Wert, der bestimmt, wie eine Anwendung während der Ausführung unter einem verwalteten Debugger systemeigene Abbilder lädt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ePolicy`  
 [in] Ein [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) Konstante, die bestimmt, wie eine Anwendung während der Ausführung unter einem verwalteten Debugger systemeigene Abbilder lädt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Richtlinie erfolgreich festgelegt ist, gibt die Methode `S_OK`. Wenn `ePolicy` liegt außerhalb des Bereichs der Enumerationswerte, die durch definierten [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), der Methodenrückgabe `E_INVALIDARG` und dem Aufruf der Methode hat keine Auswirkungen. Wenn die Richtlinie für die Native Image Generator (Ngen.exe) nicht aktualisiert werden kann, gibt die Methode `E_FAIL`.  
  
 Die `ICorDebugProcess5::EnableNGenPolicy` Methode kann zu einem beliebigen Zeitpunkt während der Lebensdauer des Prozesses aufgerufen werden. Die Richtlinie gilt für Module, die geladen werden, nachdem die Richtlinie festgelegt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
