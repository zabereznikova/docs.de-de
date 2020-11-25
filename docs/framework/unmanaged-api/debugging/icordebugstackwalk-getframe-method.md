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
ms.openlocfilehash: 452635764794e01858baab10464a03c966a55271
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711936"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame-Methode

Ruft den aktuellen Frame im [ICorDebug](icordebugstackwalk-interface.md) -Objekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>Parameter  

 `pFrame`  
 in Ein Zeiger auf die Adresse des erstellten Frame Objekts, das den aktuellen Frame im Stapel darstellt.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Laufzeit hat den aktuellen Frame erfolgreich zurückgegeben.|  
|E_FAIL|Der aktuelle Frame wurde nicht zurückgegeben.|  
|S_FALSE|Der aktuelle Frame ist ein nativer Stapel Rahmen.|  
|E_INVALIDARG|`pFrame` ist NULL.|  
|CORDBG_E_PAST_END_OF_STACK|Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Bemerkungen  

 `ICorDebugStackWalk` gibt nur tatsächliche Stapel Rahmen zurück. Verwenden Sie die [ICorDebugThread3:: getactiveingeternalframes](icordebugthread3-getactiveinternalframes-method.md) -Methode, um interne Frames zurückzugeben. (Interne Frames sind Datenstrukturen, die von der Laufzeit zur Speicherung temporärer Daten auf den Stapel verschoben werden.)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugStackWalk-Schnittstelle](icordebugstackwalk-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
