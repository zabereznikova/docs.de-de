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
ms.openlocfilehash: 83d3eda0f3c4619ec7a5df91d13ab9f3a58e5f01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721347"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf-Methode

Überprüft, ob sich der `this` interne Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parameter  

 `pFrameToCompare`  
 in Ein Zeiger auf das Vergleichs `ICorDebugFrame` Objekt.  
  
 `pIsCloser`  
 [out] `true` , wenn der `this` interne Frame näher an dem Blatt liegt als der durch angegebene Frame, `pFrameToCompare` andernfalls `false` .  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Der Vergleich wurde erfolgreich durchgeführt.|  
|E_FAIL|Der Vergleich konnte nicht durchgeführt werden.|  
|E_INVALIDARG|`pFrameToCompare` oder `pIsCloser` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  

 `IsCloserToLeaf` kann verwendet werden, um eine Richtlinie für das interbelassen interner Frames mit anderen Frames im Stapel zu implementieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugInternalFrame2-Schnittstelle](icordebuginternalframe2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
