---
title: ICorDebugStackWalk::GetFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09a5d44e2f09c0a9ad87d590bb6d7330241143ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666241"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame-Methode
Ruft den aktuellen Frame in der [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pFrame`  
 [in] Ein Zeiger auf die Adresse des erstellten Frame-Objekts, das den aktuellen Frame im Stapel darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Den aktuellen Frame wird von der Common Language Runtime wurde erfolgreich zurückgegeben.|  
|E_FAIL|Der aktuelle Frame wurde nicht zurückgegeben.|  
|S_FALSE|Der aktuelle Frame ist ein systemeigener Stapelrahmen.|  
|E_INVALIDARG|`pFrame` ist NULL.|  
|CORDBG_E_PAST_END_OF_STACK|Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugStackWalk` Gibt nur die tatsächliche Stapelrahmen zurück. Verwenden der [ICorDebugThread3:: GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) Methode, um internen Frames zurückzugeben. (Die internen Frames sind Datenstrukturen, die von der Laufzeit zum Speichern von temporären Daten auf dem Stapel abgelegt.)  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugStackWalk-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
