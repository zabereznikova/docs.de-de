---
title: ICorDebugInternalFrame2::IsCloserToLeaf-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
ms.openlocfilehash: 8b9ec94184945c19b77247175e51bd5e8dc1ceee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122664"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf-Methode
Überprüft, ob sich der `this` internen Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parameter  
 `pFrameToCompare`  
 in Ein Zeiger auf den Vergleich `ICorDebugFrame` Objekts.  
  
 `pIsCloser`  
 [out] `true`, wenn der `this` interne Frame näher an dem Blatt liegt als der durch `pFrameToCompare`angegebene Frame. Andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vergleich wurde erfolgreich durchgeführt.|  
|E_FAIL|Der Vergleich konnte nicht durchgeführt werden.|  
|E_INVALIDARG|`pFrameToCompare` oder `pIsCloser` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 `IsCloserToLeaf` kann verwendet werden, um eine Richtlinie für das interbelassen interner Frames mit anderen Frames im Stapel zu implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugInternalFrame2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
