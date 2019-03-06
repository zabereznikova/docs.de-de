---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 361cc3b897b4c85297b597f80aaffc2a2760f88e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468480"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode
Gibt zurück, den verwalteten Thread, der die Monitorsperre für dieses Objekt besitzt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppThread`  
 [out] Der verwaltete Thread, der die Monitorsperre für dieses Objekt besitzt.  
  
 `pAcquisitionCount`  
 [out] Die Anzahl wie oft dieser Thread die Sperre freizugeben, bevor sie zurückkehrt, ohne Besitzer werden müssten.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|S_FALSE|Kein verwalteter Thread besitzt die Monitorsperre für dieses Objekt.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein verwalteter Thread die Sperre der Überwachung für dieses Objekt besitzt:  
  
-   Die Methode gibt S_OK zurück.  
  
-   Das Threadobjekt ist gültig, bis der Thread beendet wird.  
  
 Wenn kein verwalteter Thread die Sperre der Überwachung für dieses Objekt besitzt `ppThread` und `pAcquisitionCount` bleiben unverändert, und die Methode gibt S_FALSE zurück.  
  
 Wenn `ppThread` oder `pAcquisitionCount` ist kein gültiger Zeiger ist, das Ergebnis nicht definiert ist.  
  
 Wenn ein Fehler auftritt, nicht ermittelt werden kann, die ggf. Thread die Sperre der Überwachung für dieses Objekt besitzt, gibt die Methode ein HRESULT, das Fehler weist darauf hin zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
