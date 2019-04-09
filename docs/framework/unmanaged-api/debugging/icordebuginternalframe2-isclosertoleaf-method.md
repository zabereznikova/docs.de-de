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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120899"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf-Methode
Überprüft, ob die `this` Interner Rahmen ist näher an der Blattebene als das angegebene ICorDebugFrame-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parameter  
 `pFrameToCompare`  
 [in] Ein Zeiger auf den Vergleich `ICorDebugFrame` Objekt.  
  
 `pIsCloser`  
 [out] `true` Wenn die `this` Interner Rahmen ist näher an der Blattebene als der Frame gemäß `pFrameToCompare`ist, andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vergleich wurde erfolgreich durchgeführt.|  
|E_FAIL|Der Vergleich konnte nicht ausgeführt werden.|  
|E_INVALIDARG|`pFrameToCompare` oder `pIsCloser` ist null.|  
  
## <a name="remarks"></a>Hinweise  
 `IsCloserToLeaf` kann verwendet werden, um eine Richtlinie für die Überlappung von internen Frames mit anderen Frames im Stapel zu implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugInternalFrame2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
