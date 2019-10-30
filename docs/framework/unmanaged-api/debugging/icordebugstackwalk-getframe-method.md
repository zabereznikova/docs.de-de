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
ms.openlocfilehash: 77210edfdc954f38ff06bc43a8b41a6abe8dc3d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131836"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame-Methode
Ruft den aktuellen Frame im [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) -Objekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>Parameter  
 `pFrame`  
 in Ein Zeiger auf die Adresse des erstellten Frame Objekts, das den aktuellen Frame im Stapel darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Laufzeit hat den aktuellen Frame erfolgreich zurückgegeben.|  
|E_FAIL|Der aktuelle Frame wurde nicht zurückgegeben.|  
|S_FALSE|Der aktuelle Frame ist ein nativer Stapel Rahmen.|  
|E_INVALIDARG|`pFrame` ist NULL.|  
|CORDBG_E_PAST_END_OF_STACK|Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugStackWalk` gibt nur tatsächliche Stapel Rahmen zurück. Verwenden Sie die [ICorDebugThread3:: getactiveingeternalframes](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) -Methode, um interne Frames zurückzugeben. (Interne Frames sind Datenstrukturen, die von der Laufzeit zur Speicherung temporärer Daten auf den Stapel verschoben werden.)  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugStackWalk-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
