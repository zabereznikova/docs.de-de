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
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788621"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode
Gibt den verwalteten Thread zurück, der die Monitor Sperre für dieses Objekt besitzt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppThread`  
 vorgenommen Der verwaltete Thread, der die Monitor Sperre für dieses Objekt besitzt.  
  
 `pAcquisitionCount`  
 vorgenommen Gibt an, wie oft dieser Thread die Sperre freigeben müsste, bevor die Sperre aufgehoben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde abgeschlossen.|  
|S_FALSE|Kein verwalteter Thread besitzt die Monitor Sperre für dieses Objekt.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein verwalteter Thread die Monitor Sperre für dieses Objekt besitzt:  
  
- Die Methode gibt S_OK zurück.  
  
- Das Thread Objekt ist gültig, bis der Thread beendet wird.  
  
 Wenn kein verwalteter Thread die Monitor Sperre für dieses Objekt besitzt, sind `ppThread` und `pAcquisitionCount` unverändert, und die Methode gibt S_FALSE zurück.  
  
 Wenn `ppThread` oder `pAcquisitionCount` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.  
  
 Wenn ein Fehler auftritt, sodass nicht bestimmt werden kann, welcher Thread, sofern vorhanden, die Monitor Sperre für dieses Objekt besitzt, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
