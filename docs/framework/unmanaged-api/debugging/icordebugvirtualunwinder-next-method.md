---
title: ICorDebugVirtualUnwinder::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4dc0b8bf7915fe579c4764bc06c1f2534eeb759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwindernext-method"></a>ICorDebugVirtualUnwinder::Next-Methode
Wechselt zum Kontext eines Aufrufers.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a>Parameter  
 Keine  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Entladung erfolgreich war, oder `CORDBG_S_AT_END_OF_STACK`, wenn die Entladung nicht abgeschlossen werden kann, da keine Frames mehr vorhanden sind.  
  
 Wenn ein fehlerhaftes HRESULT zurückgegeben wird, geben ICorDebug-APIs `CORDBG_E_DATA_TARGET_ERROR` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Beim Stapeldurchlauf sollte sichergestellt sein, dass er Fortschritte macht, sodass schließlich ein Aufruf von `Next` ein fehlerhaftes HRESULT oder `CORDBG_S_AT_END_OF_STACK` zurückgibt. Zurückgeben von `S_OK` unbegrenzt verursacht eine Endlosschleife.  
  
> [!NOTE]
>  Diese Methode ist nur in Verbindung mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugMemoryBuffer-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
